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

### Easily integate a slideshow
You can easily integrate pictures slideshow with the `flexslider` shortcode.

Before you begin, make sure you enable the flexslider [feature](/features) by
adding the following class to your article's front matter:

```yaml
---
classes:
- feature-flexslider
---
```

From there the `flexslider` shortcode can be used in one of two ways, either:

1. Just use a list of images inside the `flexslider` shortcode as demonstrated
   below:

   ```go
   {{</* flexslider */>}}
   - ![](kitchen_adventurer_cheesecake_brownie.jpg)
   - ![](kitchen_adventurer_donut.jpg)
   {{</* /flexslider */>}}
   ```

or,

2. Pass the list of images as parameters to the `flexslider` shortcode as
   illustrated here:

   ```go
   {{</* flexslider
   "kitchen_adventurer_cheesecake_brownie.jpg"
   "kitchen_adventurer_donut.jpg"
   */>}}{{</* /flexslider */>}}
   ```

> **IMPORTANT**:
> 
> Please note that while you *can "technically"* use both techniques within
> the same invocation of the `flexslider` shortcode, both images lists will
> be treated separately.
>
> As a consequence, two different slideshows will be generated : The
> `flexslider` shortcode **will not merge** its parameters and/with the
> inner content.

In both cases this will be rendered into the following slideshow:

{{< flexslider >}}
- ![](kitchen_adventurer_cheesecake_brownie.jpg)
- ![](kitchen_adventurer_donut.jpg)
{{< /flexslider >}}

### Images With Captions

While the former technique is clearer and simpler, the latter more heavily
relies on the shortcode to process the images. This unlocks access to an extra
feature that let you provide "captions" to your images:

In order to use this feature, just postfix your caption text to the image
filename and separate the two items with the "`|`" character, as demonstrated
below:

```go
{{</* flexslider
"kitchen_adventurer_cheesecake_brownie.jpg|Cheesecake Brownie"
"kitchen_adventurer_lemon.jpg|Lemon"
"kitchen_adventurer_donut.jpg|Donut"
"kitchen_adventurer_caramel.jpg|Caramel"
*/>}}{{</* /flexslider */>}}
```

The above snippet will render as shown below. You'll notice that,
of course, you are not limited to a single slideshow par article:
you can use the `flexslider` shortcode as many times as needed.

{{< flexslider
"kitchen_adventurer_cheesecake_brownie.jpg|Cheesecake Brownie"
"kitchen_adventurer_lemon.jpg|Lemon"
"kitchen_adventurer_donut.jpg|Donut"
"kitchen_adventurer_caramel.jpg|Caramel"
>}}{{< /flexslider >}}

Read next: [Story's built-in search features](/search-page/).
