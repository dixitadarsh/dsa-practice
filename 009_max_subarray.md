# Max SubArray
Given an integer array nums, find the contiguous subarray which has the largest sum and return its sum.

This is known as Kadane's Algorithm. You must solve it in O(n) time.

### Example Inputs & Outputs
```js
// Example 1:
Input: [-2,1,-3,4,-1,2,1,-5,4]
Output: 6
Explanation: [4,-1,2,1] has the largest sum = 6.
```
```js
// Example 2:
Input: [1]
Output: 1
```
```js
// Example 3:
Input: [5,4,-1,7,8]
Output: 23
```
### Constraints & Edge Cases

- Array may contain both positive and negative numbers
- Single element array should return that element
- If all numbers are negative, return the largest among them
- Empty array should return -Infinity

## Solution

```js
function maxSubArray(nums) {

    /* kadanes algorithm says that the max sub array must be done in O(n) 
   
   So the appraoch will be that we will start with first element and take  variables one will be sum and another will be maxsum
  1. Sum = 0
  2. maxsum = -Infinity

    and there will be 3 main things 
    i) add current item to sum so that we can add as the function is to get the max sum 
    ii) max sum will be the original Math.max(sum+current item , maxsum)
    iii) if sum is less than 0
  */
    let sum = 0;
    let maxSum = Number.NEGATIVE_INFINITY;
    for (let i = 0; i < nums.length; i++) {
        sum  = sum+nums[i];
        maxSum = Math.max(sum,maxSum);

        if(sum < 0) sum = 0
    }
    
    return maxSum
}

maxSubArray([-2, 1, -3, 4, -1, 2, 1, -5, 4]);

module.exports = maxSubArray;

```
