---
layout: post
title: "I Made a Thing"
description: "Deal with It gif emoji"
date: 2016-09-25
comments: true
share: true
---

After failing to find an animated "Deal with It" emoji I used it as an excuse to learn how to gifs work 
and how to make them. In then end all you need to create a gif emoji is patience, source images, and GIMP.

GIMP made the process very easy, with the only caveat being you need to be sure and either not have transparency in your images
or make sure you set the frame disposal option to to only show the current frame instead of stacking them.

Starting with:

![Smirk face]({{ site.baseurl }}/assets/img/deal_with_it/smirk_face_emoji.png "Smirk face")
![Sunglasses face]({{ site.url }}/assets/img/deal_with_it/smiling-face-with-sunglasses.png "Sunglasses face")


And following [this tutorial](https://www.gimp.org/tutorials/Simple_Animations/) we get

![deal with it]({{ site.url }}/assets/img/deal_with_it/deal_with_it.gif "deal with it")

Source .xcf file for reference if you want to play around with timing on the frames and see
how that affects the final animation
[deal_with_it.xcf]({{ site.url }}/assets/img/deal_with_it/deal_with_it.xcf)
