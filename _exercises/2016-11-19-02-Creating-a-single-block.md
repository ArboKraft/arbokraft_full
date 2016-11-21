---
layout: page
#
# Content
#
subheadline: "Exercise 02"
title: "Creating a Single Block"
date:   2016-11-19 16:11:47 +0100
teaser: "In this exercise we'll learn coordinates and how to spawn unique simple blocks"
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
  image_fullwidth: console-hello-arbocraft.png
image:
  header: "test header"
  thumb: "minecraft-coordinates.png"
---


Before spawning blocks we first need to understand how they disposed in Minecraft world.
These images are explicites :

![Coordinates in Minecraft]({{ site.urlimg }}/minecraft-coordinates.png)
*Coordinates in Minecraft by [MacFreek34570]*

and:

![Coordinates in Minecraft 2]({{ site.urlimg }}/minecraft-coordinates-2.jpg)
*Coordinates in Minecraft*

Using this coordinate system you can then spawn a block using the function *mc.setBlock*.
You must give the coordinate and ID of the block.
(you'll find the list of Block ID here : TODO: Link to ressources)

Most of the time you'll want to spawn the block near the position of the player.
So you'll need to get the Player coordinates and use it as origin.

{% highlight python %}
import mcpi.minecraft as minecraft
import mcpi.block as block
mc = minecraft.Minecraft()
#Here we get the player position
x,y,z = mc.player.getPos()
#The Grass block ID is 2 :
mc.setBlock(x+1,y,z+1,2)
{% endhighlight %}

In this example we'll put it just below the player :

{% highlight python %}
import mcpi.minecraft as minecraft
import mcpi.block as block
mc = minecraft.Minecraft()
#Here we get the player position
x,y,z = mc.player.getPos()
#Here we will use the block ID name but we could have used 
#57 instead of BLOCK.Diamond_block
mc.setBlock(x,y-1,z,BLOCK.diamond_block)
{% endhighlight %}

And now above the ground a purple wool block

{% highlight python %}
import mcpi.minecraft as minecraft
import mcpi.block as block
mc = minecraft.Minecraft()
#Here we get the player position
x,y,z = mc.player.getPos()
#Some blocks have subid, like Wool. Instead of 35 you can use
# 35,10 to get purple wool for instance or 35,14 for Red . 
# 35,0  or 35 will be white Wool
mc.setBlock(x,y-1,z,35,10)
{% endhighlight %}

[MacFreek34570]: <http://minecraft.gamepedia.com/User:MacFreek34570>