---
layout: page
#
# Content
#
subheadline: "Exercise 01"
title: "Message in console"
date:   2016-11-19 16:11:47 +0100
teaser: "In this first lesson we will show how to write a message in the console."
categories:
  - exercises
tags:
  - exercises
  - mc.postToChat
  - console
show_meta: true
#
# Styling
#
header:
  image_fullwidth: flat-grass-header.png
image:
  header: "test header"
  thumb: "01-console-thumb.png"
---


Message can be shown in the console using the *mc.postToChat* function.


{% highlight python %}
import mcpi.minecraft as minecraft

mc = minecraft.Minecraft()
mc.postToChat("Hello ArboKraft")
{% endhighlight %}

This should render as :

![Console Message]({{ site.urlimg }}/01-HelloArboKraft.png)