---
layout: default
#
# Content
#
subheadline: "0n"
title: "Creating a chess board"
teaser: "Using loops and modulo to create a chess board"
categories:
  - exercices
tags:
  - exercices block mc.setBlock while loop modulo
#
# Styling
#
image:
  header: ""
  thumb: "you-can-delete-me-thumb.png"
  homepage: "you-can-delete-me-homepage.png"
  caption: "Caption?"
  url: "http://phlow.de/"
---

,,, python
import mcpi.minecraft as minecraft
import mcpi.block as block
import server
import sys
import time
import random
mc = minecraft.Minecraft()
mc.postToChat("Echec et Mat ! ")
#Here i get the player position
a,b,c = mc.player.getPos()
a = a+1
b= b
c = c+1

    
size = 6
i= j = k = 0
color = 0
while i < size:
    j=0
    while j < size:
        k = 0
        while k < size:
            if (i%2 == j%2):
                if (k%2 == 0):
                    color = 155
                else:
                    color = 49
            else:
                if (k%2 == 0):
                    color = 49
                else:
                    color = 155
            mc.setBlock(a+i,b+k,c+j,color)
            k = k+1
        j = j+1 
    i = i+1     
,,,

 [1]: #
 [2]: #
 [3]: #
 [4]: #
 [5]: #
 [6]: #
 [7]: #
 [8]: #
 [9]: #
 [10]: #