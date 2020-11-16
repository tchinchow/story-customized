---
title: Story's Image Slideshows
date: "2018-08-21"
url: "/flexslider"
description: "Story now also let you include nice images slideshows with FlexSlider"
author: Lionel VICTOR
image: "img/unsplash-photos-WQ69GW2vZNs.jpg"
credit: "https://unsplash.com/photos/WQ69GW2vZNs"
thumbnail: img/unsplash-photos-WQ69GW2vZNs.tn-500x500.jpg
classes:
- feature-figcaption
- feature-figcaption-hidden
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

From there the `flexslider` shortcode can be used with a list of images as
illustrated below:

```go
{{</* flexslider */>}}
- ![](kitchen_adventurer_cheesecake_brownie.jpg)
- ![](kitchen_adventurer_donut.jpg)
{{</* /flexslider */>}}
```

This will be rendered into the following slideshow:

{{< flexslider >}}
- ![](kitchen_adventurer_cheesecake_brownie.jpg)
- ![](kitchen_adventurer_donut.jpg)
{{< /flexslider >}}

### Images With Captions

The `flexslider` shortcode is compatible with [Story's `fig-caption` feature](/figures)
and will render the caption as you would expect.

The code below exhibits this behaviour:

```go
{{</* flexslider */>}}
- ![Cheesecake Brownie](kitchen_adventurer_cheesecake_brownie.jpg)
- ![Lemon](kitchen_adventurer_lemon.jpg)
- ![Donut](kitchen_adventurer_donut.jpg)
- ![](kitchen_adventurer_caramel.jpg)
  _The "Caramel" cup cake advertised with flexslider_
{{</* /flexslider */>}}
```

The above snippet will be rendered as shown below. It will also advertise
`flexslider` shortcode's ability of rendering multiple slideshows in a
single page: you can use the as many times as needed.

{{< flexslider >}}
- ![Cheesecake Brownie](kitchen_adventurer_cheesecake_brownie.jpg)
- ![Lemon](kitchen_adventurer_lemon.jpg)
- ![Donut](kitchen_adventurer_donut.jpg)
- ![](kitchen_adventurer_caramel.jpg)
  _The "Caramel" cup cake advertised with flexslider_
{{< /flexslider >}}

Read next: [Story's image formatting features](/images/).
