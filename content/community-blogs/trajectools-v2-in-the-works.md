---
source: "blog"
title: "anitagraser.com: QGIS Processing Trajectools v2 in the works"
image: "trajectools-v2-in-the-works."
date: "2024-01-12"
link: "https://anitagraser.com/2024/01/12/trajectools-v2-in-the-works/"
draft: "true"
showcase: "planet"
---

<p>Trajectools development started <a href="https://anitagraser.com/2019/02/02/movement-data-in-gis-20-trajectools-v1-released/">back in 2018</a> but has been on hold since 2020 when I realized that it would be necessary to first develop a solid trajectory analysis library. With the <a href="https://movingpandas.org">MovingPandas</a> library in place, I&#8217;ve now started to reboot Trajectools. </p>



<p>Trajectools v2 builds on MovingPandas and exposes its trajectory analysis algorithms in the QGIS Processing Toolbox. So far, I have integrated the basic steps of </p>



<ol>
<li>Building trajectories including speed and direction information from timestamped points and </li>



<li>Splitting trajectories at observation gaps, stops, or regular time intervals.</li>
</ol>



<figure class="wp-block-image size-large"><img width="288" height="121" data-attachment-id="8755" data-permalink="https://anitagraser.com/2024/01/12/trajectools-v2-in-the-works/image-3-10/" data-orig-file="https://underdark.files.wordpress.com/2024/01/image-3.png" data-orig-size="288,121" data-comments-opened="1" data-image-meta="{&quot;aperture&quot;:&quot;0&quot;,&quot;credit&quot;:&quot;&quot;,&quot;camera&quot;:&quot;&quot;,&quot;caption&quot;:&quot;&quot;,&quot;created_timestamp&quot;:&quot;0&quot;,&quot;copyright&quot;:&quot;&quot;,&quot;focal_length&quot;:&quot;0&quot;,&quot;iso&quot;:&quot;0&quot;,&quot;shutter_speed&quot;:&quot;0&quot;,&quot;title&quot;:&quot;&quot;,&quot;orientation&quot;:&quot;0&quot;}" data-image-title="image-3" data-image-description="" data-image-caption="" data-medium-file="https://underdark.files.wordpress.com/2024/01/image-3.png?w=288" data-large-file="https://underdark.files.wordpress.com/2024/01/image-3.png?w=288" src="https://underdark.files.wordpress.com/2024/01/image-3.png?w=288" alt="" class="wp-image-8755" srcset="https://underdark.files.wordpress.com/2024/01/image-3.png 288w, https://underdark.files.wordpress.com/2024/01/image-3.png?w=150 150w" sizes="(max-width: 288px) 100vw, 288px" /></figure>



<p>The algorithms create two output layers: </p>



<ul>
<li>Trajectory points with speed and direction information that are styled using arrow markers </li>



<li>Trajectories as LineStringMs which makes it straightforward to count the number of trajectories and to visualize where one trajectory ends and another starts.</li>
</ul>



<p>So far, the default style for the trajectory points is hard-coded to apply the Turbo color ramp on the speed column with values from 0 to 50 (since I&#8217;m simply loading a ready-made QML). By default, the speed is calculated as km/h but that can be customized: </p>



<figure class="wp-block-image size-large"><a href="https://underdark.files.wordpress.com/2024/01/image-1.png"><img width="1024" height="619" data-attachment-id="8742" data-permalink="https://anitagraser.com/2024/01/12/trajectools-v2-in-the-works/image-1-12/" data-orig-file="https://underdark.files.wordpress.com/2024/01/image-1.png" data-orig-size="1480,895" data-comments-opened="1" data-image-meta="{&quot;aperture&quot;:&quot;0&quot;,&quot;credit&quot;:&quot;&quot;,&quot;camera&quot;:&quot;&quot;,&quot;caption&quot;:&quot;&quot;,&quot;created_timestamp&quot;:&quot;0&quot;,&quot;copyright&quot;:&quot;&quot;,&quot;focal_length&quot;:&quot;0&quot;,&quot;iso&quot;:&quot;0&quot;,&quot;shutter_speed&quot;:&quot;0&quot;,&quot;title&quot;:&quot;&quot;,&quot;orientation&quot;:&quot;0&quot;}" data-image-title="image-1" data-image-description="" data-image-caption="" data-medium-file="https://underdark.files.wordpress.com/2024/01/image-1.png?w=300" data-large-file="https://underdark.files.wordpress.com/2024/01/image-1.png?w=545" src="https://underdark.files.wordpress.com/2024/01/image-1.png?w=1024" alt="" class="wp-image-8742" srcset="https://underdark.files.wordpress.com/2024/01/image-1.png?w=1024 1024w, https://underdark.files.wordpress.com/2024/01/image-1.png?w=150 150w, https://underdark.files.wordpress.com/2024/01/image-1.png?w=300 300w, https://underdark.files.wordpress.com/2024/01/image-1.png?w=768 768w, https://underdark.files.wordpress.com/2024/01/image-1.png 1480w" sizes="(max-width: 1024px) 100vw, 1024px" /></a></figure>



<p>I don&#8217;t have a solution yet to automatically create a style for the trajectory lines layer. Ideally, the style should be a categorized renderer that assigns random colors based on the trajectory id column. But in this case, it&#8217;s not enough to just load a QML. </p>



<p>In the meantime, I might instead include an Interpolated Line style. What do you think? </p>



<figure class="wp-block-image size-large"><a href="https://underdark.files.wordpress.com/2024/01/image-2.png"><img width="1024" height="750" data-attachment-id="8749" data-permalink="https://anitagraser.com/2024/01/12/trajectools-v2-in-the-works/image-2-11/" data-orig-file="https://underdark.files.wordpress.com/2024/01/image-2.png" data-orig-size="1338,980" data-comments-opened="1" data-image-meta="{&quot;aperture&quot;:&quot;0&quot;,&quot;credit&quot;:&quot;&quot;,&quot;camera&quot;:&quot;&quot;,&quot;caption&quot;:&quot;&quot;,&quot;created_timestamp&quot;:&quot;0&quot;,&quot;copyright&quot;:&quot;&quot;,&quot;focal_length&quot;:&quot;0&quot;,&quot;iso&quot;:&quot;0&quot;,&quot;shutter_speed&quot;:&quot;0&quot;,&quot;title&quot;:&quot;&quot;,&quot;orientation&quot;:&quot;0&quot;}" data-image-title="image-2" data-image-description="" data-image-caption="" data-medium-file="https://underdark.files.wordpress.com/2024/01/image-2.png?w=300" data-large-file="https://underdark.files.wordpress.com/2024/01/image-2.png?w=545" src="https://underdark.files.wordpress.com/2024/01/image-2.png?w=1024" alt="" class="wp-image-8749" srcset="https://underdark.files.wordpress.com/2024/01/image-2.png?w=1024 1024w, https://underdark.files.wordpress.com/2024/01/image-2.png?w=150 150w, https://underdark.files.wordpress.com/2024/01/image-2.png?w=300 300w, https://underdark.files.wordpress.com/2024/01/image-2.png?w=768 768w, https://underdark.files.wordpress.com/2024/01/image-2.png 1338w" sizes="(max-width: 1024px) 100vw, 1024px" /></a></figure>



<p>Of course, the goal is to make Trajectools interoperable with as many existing QGIS Processing Toolbox algorithms as possible to enable efficient Mobility Data Science workflows. </p>



<figure class="wp-block-image size-large"><a href="https://underdark.files.wordpress.com/2024/01/image-4.png"><img loading="lazy" width="1024" height="895" data-attachment-id="8757" data-permalink="https://anitagraser.com/2024/01/12/trajectools-v2-in-the-works/image-4-10/" data-orig-file="https://underdark.files.wordpress.com/2024/01/image-4.png" data-orig-size="1247,1091" data-comments-opened="1" data-image-meta="{&quot;aperture&quot;:&quot;0&quot;,&quot;credit&quot;:&quot;&quot;,&quot;camera&quot;:&quot;&quot;,&quot;caption&quot;:&quot;&quot;,&quot;created_timestamp&quot;:&quot;0&quot;,&quot;copyright&quot;:&quot;&quot;,&quot;focal_length&quot;:&quot;0&quot;,&quot;iso&quot;:&quot;0&quot;,&quot;shutter_speed&quot;:&quot;0&quot;,&quot;title&quot;:&quot;&quot;,&quot;orientation&quot;:&quot;0&quot;}" data-image-title="image-4" data-image-description="" data-image-caption="" data-medium-file="https://underdark.files.wordpress.com/2024/01/image-4.png?w=300" data-large-file="https://underdark.files.wordpress.com/2024/01/image-4.png?w=545" src="https://underdark.files.wordpress.com/2024/01/image-4.png?w=1024" alt="" class="wp-image-8757" srcset="https://underdark.files.wordpress.com/2024/01/image-4.png?w=1024 1024w, https://underdark.files.wordpress.com/2024/01/image-4.png?w=150 150w, https://underdark.files.wordpress.com/2024/01/image-4.png?w=300 300w, https://underdark.files.wordpress.com/2024/01/image-4.png?w=768 768w, https://underdark.files.wordpress.com/2024/01/image-4.png 1247w" sizes="(max-width: 1024px) 100vw, 1024px" /></a></figure>



<p>The easiest way to set up QGIS with MovingPandas Python environment is to install both from conda. You can find the instructions together with the latest Trajectools development version at: <a href="https://github.com/movingpandas/qgis-processing-trajectory">https://github.com/movingpandas/qgis-processing-trajectory</a></p>



<hr class="wp-block-separator has-alpha-channel-opacity" />



<p>This post is part of a series. Read more about&nbsp;<a href="https://anitagraser.com/movement-data-in-gis/">movement data in GIS.</a></p>
