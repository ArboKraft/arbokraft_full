---
layout: page
#
# Content
#
subheadline: "Exercise 04"
date:   2016-11-19 00:04:47 +0100
title: "Spawning a line of blocks - While Loop - Modulo"
teaser: "Spawning a line of blocks -  using a while loop - playing with modulo"
categories:
  - exercises
tags:
  - exercises
show_meta: true
#
# Styling
#
header:
  image_fullwidth: line-header.png
image:
  thumb: "exercises/04-thumb.png"
---


* Note : We already saw the "setBlocks" function in Exercice 3. It allows line creation in an easier (yet less modular) way *

>The while construct consists of a block of code and a condition/expression. The condition/expression is evaluated, and if the condition/expression is true, the code within the block is executed. This repeats until the condition/expression becomes false. Because the while loop checks the condition/expression before the block is executed, the control structure is often also known as a pre-test loop. Compare this with the do while loop, which tests the condition/expression after the loop has executed. [^1]

First let's create a line made of say 10 blocks of Spruce Wood Plank (id : 5:1)


{% highlight python %}
import mcpi.minecraft as minecraft
import mcpi.block as block
mc = minecraft.Minecraft()

#Here we get the player position
x,y,z = mc.player.getPos()

#We will set the number of blocks we want in a variable
size = 10
#We will use a counter to store the number we already built.
counter = 0

#And here is the while loop. 
while counter < size:
#We create our block and at each iteration we will set new one next to previous one
  mc.setBlock(x+counter,y,z,5,1)
#We need to increment our counter each time we set a block to get the expected result
  counter = counter+1
#The Loop will stop when counter will be equal to size
{% endhighlight %}

And here is what you should get :
![10 blocks line of Spruce Wood Plank]({{ site.urlimg }}exercises/04-line-wood.png)
*10 blocks line of Spruce Wood Plank*

You can play with size to see this line growing.
We can also play with the subid of the wood at each iteration using a modulo.

>In computing, the modulo operation finds the remainder after division of one number by another (sometimes called modulus). [^2]

So for instance for modulo 6

| Source | 0 | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9 | 10 | 11 | 12 | 13 | etc.|
| Modulo 6 | 0 | 1 | 2 | 3 | 4 | 5 | 0 | 1 | 2 | 3 | 4 | 5 | 0 | 1 | etc. |

We'll use this to alternate on the kind of wood.
5 modulo 6 in python will be written 5 % 6

{% highlight python %}
import mcpi.minecraft as minecraft
import mcpi.block as block
mc = minecraft.Minecraft()

#Here we get the player position
x,y,z = mc.player.getPos()

#We will set the number of blocks we want in a variable
size = 10
#We will use a counter to store the number we already built.
counter = 0

#And here is the while loop. 
while counter < size:
#We create our block and at each iteration we will set new one next to previous one and the kind of wood will move to next subid
  mc.setBlock(x+counter,y,z,5,counter%6)
#We need to increment our counter each time we set a block to get the expected result
  counter = counter+1
#The Loop will stop when counter will be equal to size
{% endhighlight %}

You should get something like:
![10 blocks line of alternating Wood Plank]({{ site.urlimg }}exercises/04-line-wood-modulo.png)
*10 blocks line of alternating Wood Plank*

We can do the same with Wool (35) and a module 16 (as there are 16 color of wool). We'll also make a diagonal playing with the z coordinate as well


{% highlight python %}
import mcpi.minecraft as minecraft
import mcpi.block as block
mc = minecraft.Minecraft()

#Here we get the player position
x,y,z = mc.player.getPos()

#We will set the number of blocks we want in a variable
size = 32
#We will use a counter to store the number we already built.
counter = 0

#And here is the while loop. 
while counter < size:
#We create our block and at each iteration we will move x and z from 1 so we'll get a diagonal
  mc.setBlock(x+counter,y,z+counter,35,counter%16)
#We need to increment our counter each time we set a block to get the expected result
  counter = counter+1
#The Loop will stop when counter will be equal to size
{% endhighlight %}

And voila !
![32 blocks diagonal line of wool alternating colors]({{ site.urlimg }}exercises/04-line-diag-wool.png)
*32 blocks diagonal line of wool alternating colors*
04-line-diag-wool.png


[^1]: <i class="fa fa-wikipedia-w" aria-hidden="true"></i>[While Loop]
[^2]: <i class="fa fa-wikipedia-w" aria-hidden="true"></i>[Modulo]


[While Loop]: <https://en.wikipedia.org/wiki/While_loop>
[Modulo]: <https://en.wikipedia.org/wiki/Modulo_operation>