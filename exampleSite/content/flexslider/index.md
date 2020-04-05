---
title: Flexslider
date: "2018-08-21"
url: "/flexslider"
description: "Story now also let you include nice images slideshows with FlexSlider"
author: Lionel VICTOR
image: "img/unsplash-photos-WQ69GW2vZNs.jpg"
credit: "https://unsplash.com/photos/WQ69GW2vZNs"
thumbnail: img/unsplash-photos-WQ69GW2vZNs.tn-500x500.jpg
classes:
- feature-justify
- feature-flexslider
categories:
- Demo
---
This article is a demo of Story's image slideshows feature based on
[FlexSlider2](http://flexslider.woothemes.com/).
<!--more-->

### Integate a slideshow
You can easily integrate pictures slideshow with the `flexslider` shortcode:
Just use the list of images as the `flexslider` shortcode parameters as
demonstrated below:

```go
{{</* flexslider
"kitchen_adventurer_cheesecake_brownie.jpg"
"kitchen_adventurer_donut.jpg"
*/>}}{{</* /flexslider */>}}
```

> **Important**:
> Do not forget to enable the flexslider [feature flag](/features) by
> setting the `feature-flexslider` class in your article's front matter.

This will be rendered into the following slideshow:

{{< flexslider
"kitchen_adventurer_cheesecake_brownie.jpg"
"kitchen_adventurer_donut.jpg"
>}}{{< /flexslider >}}

>**Note**: You can also add captions to your images: Just postfix
> your caption to the image filenamt and use the "`|`" character
> to separate the two items within the same parameter string, as
> demonstrated below:
> ```go
> {{</* flexslider
> "kitchen_adventurer_cheesecake_brownie.jpg|Cheesecake Brownie"
> "kitchen_adventurer_lemon.jpg|Lemon"
> "kitchen_adventurer_donut.jpg|Donut"
> "kitchen_adventurer_caramel.jpg|Caramel"
> */>}}{{</* /flexslider */>}}
> ```

Of course you are not limited to a single slideshow par article.

Here follows another slideshow based on the above snippet with "captions":

{{< flexslider
"kitchen_adventurer_cheesecake_brownie.jpg|Cheesecake Brownie"
"kitchen_adventurer_lemon.jpg|Lemon"
"kitchen_adventurer_donut.jpg|Donut"
"kitchen_adventurer_caramel.jpg|Caramel"
>}}{{< /flexslider >}}

Read next: [Story's built-in search features](/search-page/).
