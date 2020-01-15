---
layout: post
title: "How To Solve It"
description: "A Book Review"
date: 2020-01-14
comments: true
share: true
---

---
One of the primary responsibilities of a software developer is to be a problem solver. It's our responsibility to take
business requirements and figure out how to deliver a system that can support those needs. The rub is that there is no 
single pattern or process that can delivery results every time, each situation is slightly different. If you misunderstand 
either the requirements or the underlying context of the feature you will very likely make mistakes or incorrect assumptions.  

One approach to tackling this problem is outlined in G. Polya's book "How To Solve It", where Polya lays out a four step process for
thinking about novel problems and provides a list of helpful heuristics to make solving problems easier.  

## 1. Understand The Problem
> It is foolish to answer a question you do not understand. It is sad to work for an end that you do not desire.  
> \- G. Polya

The first step, which seems obvious in theory but can be easily missed in practice, is to understand the problem you are trying to solve. In
a software engineering context this means one thing: ASK QUESTIONS.
* Ask for definitions of terms, even the basic ones you think you already know
* Articulate as many assumptions as you can think of, confirm with stakeholders they are correct
* What are the unknowns, what information is missing
* Restate the desired functionality in your own words, ask for confirmation
* Describe how the system would behave in hypothetical scenarios
* Describe the things you can think of the system CAN'T or DOESN'T do, uncover assumptions stakeholders are making

## 2. Devising A Plan
> We have a plan when we know, or know at least in outline, which calculations, computations, or constructions we have to perform in order to obtain the unknown.  
> \- G. Polya

The second step is to come up with a plan, or in other words, its time to think. Not only is it time to think, it's time to research! The odds that
you're solving a completely novel problem, the likes of which no one has seen before, are very low. Google is our friend, and it's very likely someone has solved a problem similar to ours and talked about it somewhere on the internet. We score no points for reinventing wheels, and we can't
invent better ones if we don't understand the current designs. In addition to research, Polya provides a couple useful strategies for devising a plan:
* Draw pictures. Flow diagrams, class diagrams, anything that can help subdivide the problem and define relationships between the parts
* Solve a simpler problem. Identify the core features of the system and try to design that

## 3. Carrying Out The Plan
This is the step where we actually start writing code. For this step we break a bit from Polya to a concept from "The Pragmatic Programmer: From Journeyman to Master" called tracer code. The idea is similar to prototyping with one major difference: you are not writing this code to be thrown
away (sorry Brooks). If the application is a reporting web app, the first thing we build is a simple app that pulls all the data from the database and
displays it in the browser. The next thing we build are the filters that allow us to not dump the entire DB into the browser.

This approach allows you to validate that the architecture is feasible, as well as providing a demo-able app you can share with stakeholders
early on in the development process.

## 4. Looking Back
> By looking back at the completed solution, by reconsidering and reexamining the result and the path that led to it, they [the student] could consolidate their knowledge and develop their ability to solve problems.  
> \- G. Polya

Reflecting on the solution is part of the process. Like red, green, refactor in TDD or the adage to "First make it work, then make it right, then make it fast", reflection is a vital part of creating good code. Writing software is simultaneously an act of creation and discovery. The odds that
we'll truly understand a problem until we're deep in the middle of it are very low. Reflection gives us the opportunity to ask "What would I have
done then, knowing what I know now?".

The beauty of software development is that isn't a rhetorical question. Unlike physical construction, we can often take those learnings and apply them
directly to the systems that generated them.
