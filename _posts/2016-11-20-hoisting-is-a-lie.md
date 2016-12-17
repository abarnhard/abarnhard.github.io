---
layout: post
title: "Hoisting is a lie"
description: "Lessons from Advanced JS Foundations with Kyle Simpson"
date: 2016-11-20
comments: true
share: true
---

---

At some point when learning JavaScript, you've probably been taught that JS engines "hoist" variables;
with the idea that this
```javascript
var a = 1;
a = a + b;
var b = 2;
```
becomes this
```javascript
var a;
var b;
a = 1;
a = a + b;
b = 2;
```
at run time.

As it turns out, this isn't actually the way JavaScript works. Hoisting is a teaching lie, an over-simplification
of the full behavior of JavaScript engines into a single pass model. The truth of the matter is that running a JavaScript program
is a two phase process; first compilation, then execution.

In the first phase, compilation, the engine will find and associate all declarations with their appropriate scopes. Then, in the second phase,
your code is executed.

The important bit of information that gets lost when using the hoisting analogy is that, because it's a two phase process:
```javascript
var a = 1;
```
is actually two separate statements in a single line. The compiler processes
```javascript
var a;
```
and the execution engine processes
```javascript
a = 1;
```
The concept of hoisting obfuscates the fact that as you write a program you are actually creating
instructions for two distinct processing engines, sometimes with a single line of code.
