# Validate Palindrome
Write a function that determines whether a given string is a valid palindrome. A palindrome is a word, phrase, or sequence that reads the same backward as forward. Ignore cases and all non-alphanumeric characters.

**Input:** A single string str.

**Output:** Return true if the string is a valid palindrome, false otherwise.

### Example Inputs & Outputs
```js
// Example 1:
Input: "A man, a plan, a canal: Panama"
Output: true
```
```js
// Example 2:
Input: "race a car"
Output: false
```
```js
// Example 3:
Input: " "
Output: true
```
```js
// Example 4:
Input: "1234"
Output: false
```
```js
// Example 5:
Input: "!!!@@@###"
Output: true. // ignores all the non alphanumeric characters
```
### Constraints & Edge Cases
- The input string may contain letters, numbers, spaces, and special characters.
- Ignore cases (treat uppercase and lowercase the same).
- Ignore all non-alphanumeric characters.
- An empty string or a string with only non-alphanumeric characters is considered a valid palindrome.

## Solution
```js
function validatePalindrome(str) {
    // Your implementation
    const normalizedStr = str.trim().toLowerCase(str).replace(/[^a-zA-Z0-9]/g, "");
    let reversedStr = '';
    for (let i = normalizedStr.length - 1; i >= 0; i--) {
        reversedStr += normalizedStr[i];
    }
    if (normalizedStr === reversedStr) return true
    else return false
}

//For the purpose of user debugging.
validatePalindrome("race a car");

module.exports = validatePalindrome
```
