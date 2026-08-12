# Remove Duplicates from Array

Given an array, your task is to return a new array with all duplicate elements removed.
You should preserve the order of the first occurrence of each element.

### Input
- An array of any primitive values: number, string, boolean, null, or undefined.

### Output
- A new array containing only unique elements, in the order they first appear.

### Edge Cases
- Empty array should return an empty array.
- Duplicates can be of different types (e.g., 1 and "1" are not the same).
- Object and array references are considered unique even if they look identical.

### Examples
```js
removeDuplicates([1, 2, 2, 3, 4, 4]);
// Output: [1, 2, 3, 4]
```
```js
removeDuplicates(["a", "b", "a", "c"]);
// Output: ["a", "b", "c"]
```
```js
removeDuplicates([1, "1", 1]);
// Output: [1, "1"]
```
```js
removeDuplicates([]);
// Output: []
```
```js
removeDuplicates([true, false, true]);
// Output: [true, false]
```
## Solution
```js
function removeDuplicates(arr) {
  // your code here
  if(arr.length==0) return [];
  const seen = new Set();
  const result = [];
  for(let i = 0;i<arr.length;i++){
    if(!seen.has(arr[i])){
        seen.add(arr[i]);
        result.push(arr[i])
    }
  }
  console.log(result)
  return result
}

removeDuplicates([1, 2, 2, 3, 4, 4])
module.exports = removeDuplicates;

```
