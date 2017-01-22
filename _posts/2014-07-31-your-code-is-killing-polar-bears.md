---
layout: post
title: "Your code is killing polar bears"
description: "Not cool, man. Not cool"
date: 2014-08-19
comments: true
share: true
---

If you've never been introduced to the concept of transistors and boolean algebra, code execution can
seem mysterious and potentially magical. The truth, however, is that executing a line of code is fundamentally
a physical process that requires energy (or the tiny wizard under the keyboard has to eat, whatever
works for you).


Inefficient code not only slows down your application, it heats up your CPU, increases your electricity bill,
and increases your carbon footprint as well.


When writing code purely in JavaScript, efficiency is relatively straight forward. As a general rule,
you can optimize the logical flow and decrease your total lines of code at the expense of readability,
but not much else.


That equation changes when you begin working with Express and adding HTML template engines like Jade
and EJS into the mix. Since now JavaScript can be run in two different places (either your routes or
in the template itself) the trade offs become a bit more complicated.


On the one hand, you want to perform as much processing to user input in your routes, as that is pure
JavaScript and where it really belongs. On the other hand, some logic can only be executed inside the
template itself in order for everything to work.


Sadly, I don’t yet have a real handle on the best methodology to handle this issue. In my defense,
I only learned it was an issue this morning.


In the future I plan to write a post that will lay out the basic logic behind choosing to add
computations in one file vs. another, but in the meantime if you want to limit the number of polar
bears suffering from your inefficient code, write it so you use as few loops as possible.
