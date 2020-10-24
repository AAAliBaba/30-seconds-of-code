---
title: getNeighbors
tags: array,beginner
---

Generates an array containing the immediate neighbors of an element in a 2D array (in clockwise order).

- Helper array neighborRows contains neighbors' row index relative to element.
- Helper array neighborColumns contains neighbors' column index relative to element.
- Iterate 8 times (for 8 possible neighbors).
- Use Array.prototype.push() if nextRow and nextColumn are not out-of-bounds.

```js
const getNeighbors = (row, column, array2D) => {
  let neighbors = [];

  const neighborRows = [-1, -1, -1, 0, 1, 1, 1, 0];
  const neighborColumns = [-1, 0, 1, 1, 1, 0, -1, -1];

  for(let i = 0; i < 8; ++i) {
    let nextRow = row + neighborRows[i];
    let nextColumn = column + neighborColumns[i];

    if(nextRow >= 0 && nextRow < array2D[row].length && nextColumn >= 0 && nextColumn < array2D.length)
      neighbors.push(array2D[nextRow][nextColumn]);
  }
  return neighbors;
}
```

```js
let array = [
  [1, 2, 3],
  [4, 5, 6],
  [7, 8, 9]
];

getNeighbors(1, 1, array); // [1, 2, 3, 6, 9, 8, 7, 4]
getNeighbors(0, 2, array); // [6, 5, 2]
```
