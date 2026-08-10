# Find largest number
Given an array arr of numbers, return the largest number in the array. If the array is empty, return null.


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

### Examples
 ```js 
Input: arr = [3, 1, 2]
Output: 3
```
```js 
Input: arr = [-5, 2, -3, 4]
Output: 4
```
```js 
Input: arr = [0, 2, 3]
Output: 3
```
```js 
Input: arr = []
Output: null
```
## Solution

```js
function findLargest(arr) {
  // your solution here
  if (!Array.isArray(arr)) return false;
  if (arr.length == 0) return null;
  let max;
  for (let i = 0; i < arr.length; i++) {
    if (typeof arr[i] == 'number' && Number.isFinite(arr[i])) {
      if (max === undefined || max < arr[i]) max = arr[i];
    } else {
      return false
    }
  }
  return max;
}

module.exports = { findLargest };

```
