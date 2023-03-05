# Caesars Cipher 

### Problem Statement 

One of the simplest and most widely known ciphers is a Caesar cipher, also known as a shift cipher. In a shift cipher the meanings of the letters are shifted by some set amount.

A common modern use is the ROT13 cipher, where the values of the letters are shifted by 13 places. Thus `A ↔ N`, `B ↔ O` and so on.

Write a function which takes a ROT13 encoded string as input and returns a decoded string.

All letters will be uppercase. Do not transform any non-alphabetic character (i.e. spaces, punctuation), but do pass them on. 

-------

## Solution 

```js 
function rot13(str) {
  const A_CODE = 65;
  const Z_CODE = 90;
  let result = '';

  for (let i = 0; i < str.length; i++) {
    let letterCode = str.charCodeAt(i);

    if (letterCode >= A_CODE && letterCode <= Z_CODE) {
      letterCode = ((letterCode - A_CODE + 13) % 26) + A_CODE;
      result += String.fromCharCode(letterCode);
    }
    else if (letterCode >= A_CODE + 13 && letterCode <= Z_CODE + 13) {
      letterCode = ((letterCode - A_CODE - 13) % 26) + A_CODE;
      result += String.fromCharCode(letterCode);
    }
    else {
      result += str[i];
    }
  }
  return result;
}
```


------


## Test Cases

- `rot13("SERR PBQR PNZC")` should decode to the string `FREE CODE CAMP`
- `rot13("SERR CVMMN!")` should decode to the string F`REE PIZZA!`
- `rot13("SERR YBIR?")` should decode to the string `FREE LOVE?`
- `rot13("GUR DHVPX OEBJA SBK WHZCF BIRE GUR YNML QBT.")` should decode to the string `THE QUICK BROWN FOX JUMPS OVER THE LAZY DOG.`
