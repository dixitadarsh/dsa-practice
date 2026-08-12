# Voting Eligibility
You are given an integer age representing the age of a person. Your task is to determine whether the person is eligible to vote or not. 
A person is eligible to vote if their age is 18 years or older. Write a program that checks this condition and returns:

"Eligible to vote" if the age is 18 or above. "Not eligible to vote" if the age is below 18.

### Constraints
```js
0 ≤ age ≤ 150
```

### Examples
```js
Example 1:
Input: 20
Output: Eligible to vote
```
- Explanation: Since the person’s age is 20, which is greater than 18, they are eligible to vote.
```js
Example 2:
Input: 17
Output: Not eligible to vote
```
- Explanation: The age is below 18, so the person cannot vote yet.
```js
Example 3:
Input: 18
Output: Eligible to vote
```
- Explanation: The minimum eligible age is 18, so the person can vote.

## Solution
```js
function checkVotingEligibility(age) {
  if (age <= 0 || age >= 150) return 'Not eligible to vote'
  else if (age > 0 && age < 18) return 'Not eligible to vote'
  else if (age >= 18) return 'Eligible to vote'
}

module.exports = { checkVotingEligibility };
```
