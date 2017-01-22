---
layout: post
title: "Custom Data Attributes"
description: "Injecting data straight into your HTML"
date: 2014-08-19
comments: true
share: true
---

One of the fundamental building blocks for dynamic websites is data.
If you want the user to be able to click on an image, and have a pop-up appear with more detailed
information about whatever they clicked on, that “more detailed information” has to be stored somewhere.


Prior to HTML5, that data would have either been stored in hidden input elements, stuffed into arbitrary
class/rel attributes, or required an ajax call to query a database.


Custom data attributes in HTML5 give us a clean way to store information on the client side that may
be required by our JavaScript but doesn’t necessarily need to be displayed to the user. This can massivly
improve page performance since no additional database queries are necessary after the initial page load.


How exactly does one get on this custom data gravy train you ask? Per the HTML5 spec (link):
>3.2.5.9 Embedding custom non-visible data with the data-* attributes
>A custom data attribute is an attribute in no namespace whose name starts with the string “data-”, has at least one character after the hyphen, is XML-compatible, and contains no uppercase ASCII letters.


What does the above mean? It means that you can add an attribute to ANY HTML element that begins with
“data-” and doesn’t include any capital letters or invalid XML characters.


Invalid XML characters are mostly control characters used by lower level programing languages to mark
things like the beginning and end of files. More plainly, valid XML characters are valid Unicode Characters,
which are defined by the Unicode Glossary as:
>Character. (1) The smallest component of written language that has semantic value; refers to the abstract meaning and/or shape, rather than a specific shape (see also glyph), though in code tables some form of visual representation is essential for the reader’s understanding. (2) Synonym for abstract character. (3) The basic unit of encoding for the Unicode character encoding. (4) The English name for the ideographic written elements of Chinese origin. [See ideograph (2).]


Google them if you want a deeper understanding, but the basic gist is that if you can type it on a standard english keyboard without hitting the shift key and would use it if you were writing an essay for an English class, it’s safe to use.


You can add as many “data-” attributes to your elements as you want, and they will be effectively ignored by the browser as it parses the HTML (unlike a dummy class or id added to simplify targeting the element in javascript).


The key feature of the data attribute is that it allows you to truly separate data from styling information in the markup while avoiding the performance overhead of making additional ajax calls to supply data to your client side JavaScript.
