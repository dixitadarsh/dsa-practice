# Find smallest number

Given an array arr of numbers, return the smallest number in the array. If the array is empty, return null.

### Constraints
- Input must be an array of finite numbers
- Return false for non-array inputs
- Return false for arrays containing non-number values
- Return false for arrays containing NaN, Infinity, or -Infinity
- For an empty array, return null

### Test Cases
- Base cases: empty array [] -> null, single [ x ] -> x
- Mixed arrays: [ 3, 1, 2 ], [ -5, 2, -3, 4 ]
- All negatives: [ -1, -2, -3 ]
- All positives: [ 1, 2, 3 ]
- Decimals: [ -1.5, -0.1, 0, 2.2 ]
- Invalid inputs: null, undefined, 42, '8', {}, () => {}, [1, 'a'], [NaN], [Infinity]

## Solution

```js
function findSmallest(arr) {
  if (!Array.isArray(arr)) return false;
  // your solution here
  if (arr.length <= 0) return null;
  if (arr.some(a => (typeof a != 'number'))) { return false };
  if (!arr.every(Number.isFinite)) { return false; }
  // You can use number swap or Math.min also
  return arr.reduce((min, curr) => {
    if (min > curr) min = curr;
    return min
  })
}

module.exports = { findSmallest };

```
