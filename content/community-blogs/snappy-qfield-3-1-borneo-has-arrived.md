---
source: "blog"
title: "OPENGIS.ch blog: Snappy QField 3.1 “Borneo” has arrived"
image: "snappy-qfield-3-1-borneo-has-arrived."
date: "2024-01-10"
link: "https://www.opengis.ch/2024/01/10/snappy-qfield-3-1-borneo-has-arrived/"
draft: "true"
showcase: "planet"
---

<p>The launch of QField 3.0 was a big deal, but now we&#8217;re back to focusing on smaller, more frequent updates. Don&#8217;t let the shorter change log for 3.1 trick you – there are lots of cool new features in this update!</p>



<h2 class="wp-block-heading">Main highlights</h2>



<figure class="wp-block-image size-full"><img fetchpriority="high" decoding="async" width="750" height="471" data-attachment-id="14070" data-permalink="https://www.opengis.ch/2024/01/10/snappy-qfield-3-1-borneo-has-arrived/287987844-8d7c6540-c32c-4d62-bf6e-1636a011567f/" data-orig-file="https://i0.wp.com/www.opengis.ch/wp-content/uploads/2023/12/287987844-8d7c6540-c32c-4d62-bf6e-1636a011567f.png?fit=950%2C597&amp;ssl=1" data-orig-size="950,597" data-comments-opened="1" data-image-meta="{&quot;aperture&quot;:&quot;0&quot;,&quot;credit&quot;:&quot;&quot;,&quot;camera&quot;:&quot;&quot;,&quot;caption&quot;:&quot;&quot;,&quot;created_timestamp&quot;:&quot;0&quot;,&quot;copyright&quot;:&quot;&quot;,&quot;focal_length&quot;:&quot;0&quot;,&quot;iso&quot;:&quot;0&quot;,&quot;shutter_speed&quot;:&quot;0&quot;,&quot;title&quot;:&quot;&quot;,&quot;orientation&quot;:&quot;0&quot;}" data-image-title="287987844-8d7c6540-c32c-4d62-bf6e-1636a011567f" data-image-description="" data-image-caption="" data-medium-file="https://i0.wp.com/www.opengis.ch/wp-content/uploads/2023/12/287987844-8d7c6540-c32c-4d62-bf6e-1636a011567f.png?fit=300%2C189&amp;ssl=1" data-large-file="https://i0.wp.com/www.opengis.ch/wp-content/uploads/2023/12/287987844-8d7c6540-c32c-4d62-bf6e-1636a011567f.png?fit=750%2C471&amp;ssl=1" src="https://i0.wp.com/www.opengis.ch/wp-content/uploads/2023/12/287987844-8d7c6540-c32c-4d62-bf6e-1636a011567f.png?resize=750%2C471&#038;ssl=1" alt="" class="wp-image-14070" srcset="https://i0.wp.com/www.opengis.ch/wp-content/uploads/2023/12/287987844-8d7c6540-c32c-4d62-bf6e-1636a011567f.png?w=950&amp;ssl=1 950w, https://i0.wp.com/www.opengis.ch/wp-content/uploads/2023/12/287987844-8d7c6540-c32c-4d62-bf6e-1636a011567f.png?resize=300%2C189&amp;ssl=1 300w, https://i0.wp.com/www.opengis.ch/wp-content/uploads/2023/12/287987844-8d7c6540-c32c-4d62-bf6e-1636a011567f.png?resize=768%2C483&amp;ssl=1 768w" sizes="(max-width: 750px) 100vw, 750px" data-recalc-dims="1" /></figure>



<p>One of the main improvements in this release is the brand-new functionality to enable <strong>snapping to common angles</strong> while digitizing. When enabled, the coordinate cursor will snap to configured angles alongside a visual guideline. This comes in handy when adding new geometries while surveying features with regular angles (e.g. buildings, parking lots, etc.). As QField gets more digitizing functionalities, we’ve taken the time to implement a nifty UI that collapses digitizing toggle buttons into a drawer,<strong> leaving extra space for the map canvas</strong> to shine through.</p>



<p>In addition, the vertex editor &#8211; one of QField’s most advanced geometry tools &#8211; received tons of love during this development cycle, focusing on improving its usability. Changes worth mentioning include:</p>



<ul>
<li>A <strong>new undo button allows users to revert individual vertex manipulations</strong> in case of mistaken adjustment, which can save you from having to cancel a large set of ongoing manipulations;</li>



<li>The possibility to <strong>select vertices using finger tapping on the screen</strong>, dramatically improving the user experience;</li>



<li>Clearer on-screen markers to represent vertices and</li>



<li>Tons of bug fixes to the vertex editor itself, as well as the broader set of geometry tools.</li>
</ul>



<p>It is now possible to <strong>lock the </strong>geometry of individual features within a single vector layer. While QField has long supported the concept of a locked geometry state for vector layers, that was until now a layer-wide toggle. With the new version of QField, a data-defined property can dictate whether a given feature geometry can be edited. Interested in <strong>geofenced geometry editing</strong>? We’ve got you covered <img src="https://s.w.org/images/core/emoji/14.0.0/72x72/1f609.png" alt="😉" class="wp-smiley" style="height: 1em; max-height: 1em;" /> This functionality requires the latest version of QFieldSync, which is available through QGIS’ plugin manager.</p>



<h2 class="wp-block-heading">Noticeably improvements</h2>



<p><strong>Permission handling has been improved</strong> across all platforms. On Android, QField now delays the permission request for camera, microphone, location, and Bluetooth access until needed. This makes for a much friendlier user experience.</p>



<p>QField 3.0 was one of the largest releases, with major changes in its underlying libraries, including a migration to Qt 6. With the community&#8217;s help, we have spent countless hours testing before release. However, it is never a bulletproof process, and that version came with a few noticeable regressions. In particular, camera handling on Android suffered from upstream issues with Qt. We’ve tracked as many of those as possible, making this new version much more stable. One lingering camera issue remains and will be fixed upstream in the next three weeks; we’ll update as soon as it is available.</p>



<p>Finally, long-time users of QField will notice improvements in how geometry highlights and digitizing rubber bands are drawn. We’ve doubled down on efforts to ensure that the digitized geometries and the coordinate cursor itself are always clearly visible, whether overlaid against the canvas&#8217;s light or dark parts.</p>



<p>We want to extend a heartfelt thank you to our sponsors for their generous support. If you&#8217;re inspired by the developments in QField and want to contribute, please consider <a href="https://qfield.org/donate" target="_blank" rel="noreferrer noopener">donating</a>. Your support will help us continue to innovate and improve this tool for everyone&#8217;s benefit.</p>



<p></p>
