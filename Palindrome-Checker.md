# Palindrome Checker 

### Problem Statement: 

A palindrome is a word or sentence that's spelled the same way both forward and backward, ignoring punctuation, case, and spacing.

- Return `true` if the given string is a palindrome. Otherwise, return `false`.

- We'll pass strings with varying formats, such as **racecar**, **RaceCar**, and **raceCAR** among others.

- We'll also pass strings with special symbols, such as `2A3*3a2`, `2A3 3a2`, and `2_A3*3#A2`. 

**Note**: You'll need to remove **all non-alphanumeric characters** (punctuation, spaces and symbols) and turn everything into the same case (lower or upper case) in order to check for palindromes. 

-------

### Solution: 

```js
function palindrome(str) {
    // remove non alpha-mumeric and make lower case
    let clean_str = str.replace(/[^A-Za-z0-9]/g, '').toLowerCase(); 
    // reverse clean string 
    let reverse_str = clean_str.split("").reverse().join("");
    return clean_str === reverse_str;
}
```
