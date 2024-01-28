---
source: "blog"
title: "anitagraser.com: Trajectools update: stop detection & trajectory styling"
image: "trajectools-update-stop-detection-trajectory-styling."
date: "2024-01-27"
link: "https://anitagraser.com/2024/01/27/trajectools-update-stop-detection-trajectory-styling/"
draft: "true"
showcase: "planet"
---

<p>The Trajectools toolbox has continued growing: </p>



<figure class="wp-block-image size-large"><img width="282" height="210" data-attachment-id="8767" data-permalink="https://anitagraser.com/2024/01/27/trajectools-update-stop-detection-trajectory-styling/image-6-9/" data-orig-file="https://underdark.files.wordpress.com/2024/01/image-6.png" data-orig-size="282,210" data-comments-opened="1" data-image-meta="{&quot;aperture&quot;:&quot;0&quot;,&quot;credit&quot;:&quot;&quot;,&quot;camera&quot;:&quot;&quot;,&quot;caption&quot;:&quot;&quot;,&quot;created_timestamp&quot;:&quot;0&quot;,&quot;copyright&quot;:&quot;&quot;,&quot;focal_length&quot;:&quot;0&quot;,&quot;iso&quot;:&quot;0&quot;,&quot;shutter_speed&quot;:&quot;0&quot;,&quot;title&quot;:&quot;&quot;,&quot;orientation&quot;:&quot;0&quot;}" data-image-title="image-6" data-image-description="" data-image-caption="" data-medium-file="https://underdark.files.wordpress.com/2024/01/image-6.png?w=282" data-large-file="https://underdark.files.wordpress.com/2024/01/image-6.png?w=282" src="https://underdark.files.wordpress.com/2024/01/image-6.png?w=282" alt="" class="wp-image-8767" srcset="https://underdark.files.wordpress.com/2024/01/image-6.png 282w, https://underdark.files.wordpress.com/2024/01/image-6.png?w=150 150w" sizes="(max-width: 282px) 100vw, 282px" /></figure>



<p>I&#8217;m continuously testing the algorithms integrated so far to see if they work as GIS users would expect and can to ensure that they can be integrated in Processing model seamlessly. </p>



<p>Because naming things is tricky, I&#8217;m currently struggling with how to best group the toolbox algorithms into meaningful categories. I looked into the categories mentioned in <a href="https://docs.ogc.org/is/16-120r3/16-120r3.html#11">OGC Moving Features Access</a> but honestly found them kind of lacking:</p>



<figure class="wp-block-image size-large"><a href="https://docs.ogc.org/is/16-120r3/16-120r3.html#10"><img width="600" height="263" data-attachment-id="8771" data-permalink="https://anitagraser.com/2024/01/27/trajectools-update-stop-detection-trajectory-styling/image-8-7/" data-orig-file="https://underdark.files.wordpress.com/2024/01/image-8.png" data-orig-size="600,263" data-comments-opened="1" data-image-meta="{&quot;aperture&quot;:&quot;0&quot;,&quot;credit&quot;:&quot;&quot;,&quot;camera&quot;:&quot;&quot;,&quot;caption&quot;:&quot;&quot;,&quot;created_timestamp&quot;:&quot;0&quot;,&quot;copyright&quot;:&quot;&quot;,&quot;focal_length&quot;:&quot;0&quot;,&quot;iso&quot;:&quot;0&quot;,&quot;shutter_speed&quot;:&quot;0&quot;,&quot;title&quot;:&quot;&quot;,&quot;orientation&quot;:&quot;0&quot;}" data-image-title="image-8" data-image-description="" data-image-caption="" data-medium-file="https://underdark.files.wordpress.com/2024/01/image-8.png?w=300" data-large-file="https://underdark.files.wordpress.com/2024/01/image-8.png?w=545" src="https://underdark.files.wordpress.com/2024/01/image-8.png?w=600" alt="" class="wp-image-8771" srcset="https://underdark.files.wordpress.com/2024/01/image-8.png 600w, https://underdark.files.wordpress.com/2024/01/image-8.png?w=150 150w, https://underdark.files.wordpress.com/2024/01/image-8.png?w=300 300w" sizes="(max-width: 600px) 100vw, 600px" /></a></figure>



<p><a href="https://books.google.at/books?id=r_28BAAAQBAJ&amp;printsec=frontcover#v=onepage&amp;q&amp;f=false">Andrienko et al.&#8217;s book &#8220;Visual Analytics of Movement&#8221;</a> comes closer to what I&#8217;m looking for:</p>



<figure class="wp-block-image size-large"><a href="https://books.google.at/books?id=r_28BAAAQBAJ&amp;printsec=frontcover#v=onepage&amp;q&amp;f=false"><img width="543" height="298" data-attachment-id="8769" data-permalink="https://anitagraser.com/2024/01/27/trajectools-update-stop-detection-trajectory-styling/image-7-8/" data-orig-file="https://underdark.files.wordpress.com/2024/01/image-7.png" data-orig-size="543,298" data-comments-opened="1" data-image-meta="{&quot;aperture&quot;:&quot;0&quot;,&quot;credit&quot;:&quot;&quot;,&quot;camera&quot;:&quot;&quot;,&quot;caption&quot;:&quot;&quot;,&quot;created_timestamp&quot;:&quot;0&quot;,&quot;copyright&quot;:&quot;&quot;,&quot;focal_length&quot;:&quot;0&quot;,&quot;iso&quot;:&quot;0&quot;,&quot;shutter_speed&quot;:&quot;0&quot;,&quot;title&quot;:&quot;&quot;,&quot;orientation&quot;:&quot;0&quot;}" data-image-title="image-7" data-image-description="" data-image-caption="" data-medium-file="https://underdark.files.wordpress.com/2024/01/image-7.png?w=300" data-large-file="https://underdark.files.wordpress.com/2024/01/image-7.png?w=543" src="https://underdark.files.wordpress.com/2024/01/image-7.png?w=543" alt="" class="wp-image-8769" srcset="https://underdark.files.wordpress.com/2024/01/image-7.png 543w, https://underdark.files.wordpress.com/2024/01/image-7.png?w=150 150w, https://underdark.files.wordpress.com/2024/01/image-7.png?w=300 300w" sizes="(max-width: 543px) 100vw, 543px" /></a></figure>



<p>&#8230; but I&#8217;m not convinced yet. So take the above listed three  categories with a grain of salt. Those may change before the release. (Any inputs / feedback / recommendation welcome!) </p>



<p>Anyway, here&#8217;s a screencast showcasing stop detection in AIS data, featuring the recently added trajectory styling using interpolated lines:</p>



<figure class="wp-block-image size-large"><a href="https://underdark.files.wordpress.com/2024/01/trajectools1.gif"><img loading="lazy" width="1024" height="617" data-attachment-id="8762" data-permalink="https://anitagraser.com/2024/01/27/trajectools-update-stop-detection-trajectory-styling/trajectools1/" data-orig-file="https://underdark.files.wordpress.com/2024/01/trajectools1.gif" data-orig-size="1200,724" data-comments-opened="1" data-image-meta="{&quot;aperture&quot;:&quot;0&quot;,&quot;credit&quot;:&quot;&quot;,&quot;camera&quot;:&quot;&quot;,&quot;caption&quot;:&quot;&quot;,&quot;created_timestamp&quot;:&quot;0&quot;,&quot;copyright&quot;:&quot;&quot;,&quot;focal_length&quot;:&quot;0&quot;,&quot;iso&quot;:&quot;0&quot;,&quot;shutter_speed&quot;:&quot;0&quot;,&quot;title&quot;:&quot;&quot;,&quot;orientation&quot;:&quot;0&quot;}" data-image-title="trajectools1" data-image-description="" data-image-caption="" data-medium-file="https://underdark.files.wordpress.com/2024/01/trajectools1.gif?w=300" data-large-file="https://underdark.files.wordpress.com/2024/01/trajectools1.gif?w=545" src="https://underdark.files.wordpress.com/2024/01/trajectools1.gif?w=1024" alt="" class="wp-image-8762" srcset="https://underdark.files.wordpress.com/2024/01/trajectools1.gif?w=1024 1024w, https://underdark.files.wordpress.com/2024/01/trajectools1.gif?w=150 150w, https://underdark.files.wordpress.com/2024/01/trajectools1.gif?w=300 300w, https://underdark.files.wordpress.com/2024/01/trajectools1.gif?w=768 768w, https://underdark.files.wordpress.com/2024/01/trajectools1.gif 1200w" sizes="(max-width: 1024px) 100vw, 1024px" /></a></figure>



<p>While Trajectools is getting ready for its 2.0 release, you can get the current development version directly from <a href="https://github.com/movingpandas/qgis-processing-trajectory">https://github.com/movingpandas/qgis-processing-trajectory</a>. </p>
