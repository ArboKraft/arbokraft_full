---
layout: page
#
# Content
#
subheadline: "Exercise 03"
date:   2016-11-19 00:03:47 +0100
title: "Using setBlocks to create lines, surfaces, volumes"
teaser: "Here we'll use setBlocks and play with coordinates"
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
image:
  thumb: "exercises/03-thumb.png"
---

We will now look at the setBlocks command which allow the creation of a volume of blocks between two coordinates

First well draw a 10 blocks line

{% highlight python %}
import mcpi.minecraft as minecraft
import mcpi.block as block
mc = minecraft.Minecraft()

#Here we get the player position
x,y,z = mc.player.getPos()

#We will set the number of blocks we want in a variable
lenght = 10

#We create our line between x and x+10
mc.setBlocks(x,y,z,x+lenght,y,z,5)
{% endhighlight %}

And here is what you should get :
![10 blocks line of Spruce Wood Plank]({{ site.urlimg }}exercises/03-01-line-wood.png)
*10 blocks line of Wood Plank via setBlocks*


We can create a surface the same way


{% highlight python %}
import mcpi.minecraft as minecraft
import mcpi.block as block
mc = minecraft.Minecraft()

#Here we get the player position
x,y,z = mc.player.getPos()

#We will set the size we want to reach
xsize = 10
zsize = 5

#We create our surface
mc.setBlocks(x,y,z,x+xsize,y,z+zsize,5)
{% endhighlight %}

And here is what you should get :
![10 blocks line of Spruce Wood Plank]({{ site.urlimg }}exercises/03-02-surface-wood.png)
*10x5 blocks surface of Wood Plank via setBlocks*


And modifying y as well we'll get a 3 dimension volume

{% highlight python %}
import mcpi.minecraft as minecraft
import mcpi.block as block
mc = minecraft.Minecraft()

#Here we get the player position
x,y,z = mc.player.getPos()

#We will set the size we want to reach
xsize = 10
zsize = 5
height = 4

#We create our volume
mc.setBlocks(x,y,z,x+xsize,y+height,z+zsize,5)
{% endhighlight %}

And here is what you should get :
![10 blocks line of Spruce Wood Plank]({{ site.urlimg }}exercises/03-03-volume-wood.png)
*10x5x4 blocks volume of Wood Plank via setBlocks*

To "delete" a block you just have to fill it with air (0)

So we can create a volume with a "tunnel" inside this way :

{% highlight python %}
import mcpi.minecraft as minecraft
import mcpi.block as block
mc = minecraft.Minecraft()

#Here we get the player position
x,y,z = mc.player.getPos()

#We will set the size we want to reach
xsize = 10
zsize = 10
height = 8

#We create our volume
mc.setBlocks(x,y,z,x+xsize,y+height,z+zsize,4)
#We create inside a volume of "air"
mc.setBlocks(x+xsize/2-1,y,z,x+xsize/2+1,y+2,z+zsize,0)
{% endhighlight %}

And here is what you should get :
![10 blocks line of Spruce Wood Plank]({{ site.urlimg }}exercises/03-04-tunnel.png)
*10x10x8 blocks volume of cobblestone with 2x2x10 tunnel (of air) via setBlocks*