# Loop A to Z

## Solution

```js
function generateAtoZ() {
  // your solution here
  let characters = [];
  while(characters.length < 26) {
      characters.push(String.fromCodePoint(65 + characters.length))
  }
  return characters;
}
console.log(generateAtoZ());

```
