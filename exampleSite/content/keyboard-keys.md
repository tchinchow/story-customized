---
title: Keyboard's Keys Feature
url: /keyboard-keys
date: "2018-08-18"
description: "This article shows how to display neat keyboard keys if you need to emphasis on keyboard shortcuts for instance."
author: Lionel VICTOR
image: "img/unsplash-photos-_UeY8aTI6d0.jpg"
credit: "https://unsplash.com/photos/_UeY8aTI6d0"
thumbnail: "img/unsplash-photos-_UeY8aTI6d0.tn-500x500.jpg"
classes:
- feature-kbd-keys
categories:
- Demo
---
You might have found that when you explain a procedure that requires typing
keyboard shortcuts then it is difficult to make those shortcut stand out.

Story has a shortcode for you that will sort you out.
<!--more-->
### Keyboard Keys that stand out:
Let's consider the following shortcode sequence in your markdown article:
```go
{{</* kbd-key keyCode="ctrl" /*/>}} + {{</* kbd-key keyCode="a" /*/>}}
```

If you enable keyboard-keys rendering with the `feature-[no]kbd-keys` flag _(see "[features](/features)")_, then the required CSS
will be loaded and the result will be displayed as follows:

{{< kbd-key keyCode="ctrl" />}} + {{< kbd-key keyCode="a" />}}

Now keyboard shortcut really stand out in your text.

### More about specific keys:

Key "names" that you can use with the "`kbd-key`" shortcode include:

- Function Keys:

  From _"f1"_ to _"f12"_ in lower case:

  {{< kbd-key keyCode="f1" />}} {{< kbd-key keyCode="f2" />}}...{{< kbd-key keyCode="f12" />}}

- Numbers:

  From _"zero"_ to _"nine"_ in text:

  {{< kbd-key keyCode="one" />}} {{< kbd-key keyCode="two" />}}...{{< kbd-key keyCode="zero" />}}

- Alphabetical Keys:

  From _"a"_ to _"z"_ in lower case:

  {{< kbd-key keyCode="a" />}} ... {{< kbd-key keyCode="z" />}}

- Media Keys:

  Like _"eject"_...

  {{< kbd-key keyCode="eject" />}}

- Misc Control Keys:

  Like _"tab"_, _"shift"_, _"ctrl"_, _"alt"_, _"space"_, _"return"_, _"delete"_...

  {{< kbd-key keyCode="tab" />}}
  {{< kbd-key keyCode="shift" />}}
  {{< kbd-key keyCode="ctrl" />}}
  {{< kbd-key keyCode="alt" />}}
  {{< kbd-key keyCode="space" />}}
  {{< kbd-key keyCode="return" />}}
  {{< kbd-key keyCode="delete" />}}

- OS Specific Keys:

  Like _"option"_, _"win"_, _"cmd"_...

  {{< kbd-key keyCode="option" />}}
  {{< kbd-key keyCode="win" />}}
  {{< kbd-key keyCode="cmd" />}}

Read next: [Story's MailChimp subscribe forms and RSS feeds](/mailchimp-features).
