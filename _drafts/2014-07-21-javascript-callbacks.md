---
layout: post
title: "Using Javascript Callbacks"
description: "Synchronicity is for suckers"
date: 2014-07-21
comments: true
share: true
---

One thing you need to understand about JavaScript to understand in order to use callback
functions is JavaScript’s lexical scope.

We can think of the “return” keyword like a synchronous callback.
```javascript
function add(x, y) {
  return x + y;
}
var x = 5;
var y = x + add(3, 2);
console.log(y); // 10
```

When we write functions that use “return” we step into the function (a new frame is created on the stack), do some processing, and step
back out (returning execution to the stack frame that called the function) by returning a value from the function.

This is a synchronous programing style, the logic runs top to bottom and has to wait for the
return before it can continue (the above code waits until add() has returned the result of its calculation
before adding that to x).

In asynchronous programing, instead of passing the computational results out, you pass the computational
logic IN. You do this by passing a function (that holds the next set of computational logic) into another
function so it can be called once that process has finished. Take the following:
```javascript
Client.prototype.purchase = function(symbol, qty, callBack){
  var that = this;
  qty = parseInt(qty);
  Stock.getQuote(symbol, function(quote) {
    if(that.cash >= quote * qty){
      that.cash -= quote * qty;
      that.portfolio.add(symbol, qty);
      var index = findStock(that.portfolio.stocks, symbol);
      that.portfolio.stocks[index].price = quote;
      callBack(that);
    }
  });
};
```
Stock.getQuote is an asynchronous function, so all the logic that we need to implement once we know
the stock price has to go INSIDE its callback function.

Stock.getQuote() calls the anonymous function once the web API has returned the stock price, but at
that level of execution (inside Stock.getQuote) “this” no longer points to the object that called the
.purchase() method.

This is solved by creating the variable “that” INSIDE the .purchase() function. Because of JavaScript’s
function scope, even though the anonymous function being passed to .getQuote is being executed by code
in an entirely different file, it still has access to the “that” variable, and therefore a reference to
the object that called the original method .purchase().

Another method would be to use .bind() or .call(), but that is a different blog post.

Asynchronous programing passes logic IN, synchronous programing passes results OUT.
