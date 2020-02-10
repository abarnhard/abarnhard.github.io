---
layout: post
title: "Multidimensional Array Traversal"
description: "Big O optimization"
date: 2020-01-24
comments: true
share: true
---

---
Sometimes a problem requires us to traverse every element in a multidimensional arrays. Conceptually this is relatively straight forward.

```javascript
const matrix = [
    [1, 2, 3],
    [4, 5, 6],
    [7, 8, 9]
];

for (let row = 0; row < matrix.length; row++) {
    for (let col = 0; col < matrix[row].length; col++) {
        console.log(matrix[row][col]);
    }
}
```

First we loop over the outer array, then loop over each sub-array with a nested loop. The problem with this approach is performance. Quadratic time of nested loops is not ideal.

Fortunately, if we can make the assumption that all sub-arrays are the same length, there's a solution to our problem that doesn't require nested loops.  

```javascript
const matrix = [
    [1, 2, 3],
    [4, 5, 6],
    [7, 8, 9]
];

// First, we get the width of our matrix
let width = garden[0].length;

// Second, we calculate a maximum range based on the total size of the matrix
let maxIndex = garden.length * width;

for (let i = 0; i < maxIndex; i++) {
  let row = Math.floor(i / width);
  let col = i % width;

  console.log(matrix[row][col]);
}
```

And thats it, we now now visit every location in linear instead of quadratic time. 

The row is calculated by dividing the index by the width and flooring the result. Since the width of the sub-arrays is 3:

    if the index is 0, the row index is 0.
    if the index is 6, the row index is 2.
    if the index is 7, the row index is 2.33 (still 2)
    if the index is 9, the row index is 3

The column is determined by modular arithmetic. Since the width of the sub-arrays is 3:

    if the index is 0, the column index is 0.
    if the index is 1, the column index is 1.
    if the index is 2, the column index is 2.
    if the index is 3, the column index is 0.
