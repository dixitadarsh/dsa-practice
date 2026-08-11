# Custom Sort

### Solution

```js
function customSort(arr) {
    if(arr.length == 0) return [];
    function quickSort(sortArr,low,high){
        if(low >= high) return sortArr;//if single element in array
        
        const pivot = sortArr[Math.floor((low+high)/2)];
        
        let i = low;
        let j = high;
        
        while(i <= j){
            while(sortArr[i] < pivot) {
                i++;
            }
            
            while(sortArr[j] > pivot){
                j--;
            }
            
            if(i<= j){
                [sortArr[i],sortArr[j]] = [sortArr[j],sortArr[i]];
                
                i++;
                j--;
            }
        }
        
        if(low < j){
            quickSort(sortArr,low,j)
        }
        
        if(i < high) {
            quickSort(sortArr,i,high)
        }
        
        return sortArr;
    }
    let nums = [];
    let chars = [];
    for(let i = 0;i<arr.length;i++){
        if(typeof arr[i] === 'number' && Number.isFinite(arr[i])) nums.push(arr[i])
        else if(typeof arr[i] === 'string') chars.push(arr[i]);
    }
   const sortedNums = quickSort(nums,0,nums.length-1);
const sortedChars = quickSort(chars,0,chars.length-1);
    
    return [...sortedChars,...sortedNums]
}

const input = ["g", "s", 5, 2, "c", "e", 6, 1, "a","A","Z"];
console.log(customSort(input));
```
