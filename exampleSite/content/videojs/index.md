---
title: Story's Embedded Screencasts and Videos
date: "2018-08-19 03:00:00"
url: "/videojs"
author: Lionel VICTOR
description: "Illustrate your work with embedded videos and screencasts"
image: "img/unsplash-photos-wSkfttEaBw8.jpg"
credit: "https://unsplash.com/photos/wSkfttEaBw8"
thumbnail: img/unsplash-photos-wSkfttEaBw8.tn-500x500.jpg
classes:
- feature-justify
categories:
- Demo
---

Story provides [Video Js](https://videojs.com/) integration through a
shortcode.

You can now showcase your screencasts and videos no matter where they
are stored and this article will show you how.
<!--more-->

### Easily integate a video
You can easily integrate screencasts or videos `videojs` shortcode.

Story is smart enough to recognize that you are using a `videojs` shortcode
in your page and will automatically load the required javascript libraries
for you.

The following code is all you need to display your video. It's so
simple that it speaks for itself:

```plaintext
{{</* videojs videoPath="file_example_MP4_640_3MG.mp4" */>}}
```

{{< videojs videoPath="https://ia800701.us.archive.org/26/items/SampleVideo1280x7205mb/SampleVideo_1280x720_5mb.mp4" >}}

Read next: [Story's beautiful typography](/typography/).
