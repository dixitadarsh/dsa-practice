# Count Negative
Given an array arr of numbers, return the count of elements strictly less than 0.

### Constraints
- If input is not an array, return false.
- If the array contains any non-number values or non-finite numbers (NaN, Infinity, -Infinity), return false.
- An empty array is valid and should return 0.

### Examples
```js
Input: arr = [-1, 0, 1]
Output: 1
```
```js
Input: arr = [-2, -5, -7]
Output: 3
```
```js
Input: arr = [0, 2, 3]
Output: 0
```
```js 
Input: arr = []
Output: 0
```
```js 
Input: arr = []
Output: 0
```
```js 
countNegatives([-1, 0, 1]) // 1
countNegatives([-2, -5, -7]) // 3
countNegatives([0, 2, 3]) // 0
countNegatives([]) // 0
countNegatives(null)        // false
countNegatives(undefined)   // false
countNegatives(42)          // false
countNegatives("8")         // false
countNegatives({})          // false
countNegatives(() => {})    // false
```

## Solution
```js
function countNegatives(arr) {  
    if(!Array.isArray(arr)) return false;
    if(arr.length == 0) return 0;
    return arr.reduce((count,curr) => {
        if(typeof curr !== 'number' || !Number.isFinite(curr)) return false;
        
        if(curr < 0) count++;
        
        return count;
    },0)
}

module.exports = { countNegatives };
```
