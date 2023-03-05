# Roman Numeral Converter 

## Problem Statement: 

Convert the given number into a roman numeral.



| Roman numerals| Arabic numerals |
| -| - | 
| M	| 1000 |
| CM | 	900 | 
| D	| 500 | 
| CD | 	400 | 
| C	| 100 | 
| XC | 	90 | 
| L | 50 | 
| XL | 	40 | 
| X	| 10 | 
| IX | 	9 | 
| V | 5 | 
| IV | 	4 | 
| I	| 1 | 


All roman numerals answers should be provided in upper-case. 

------- 

## Solution: 

```js 
function convertToRoman(num) {
  const romanNumerals = [
    { value: 1000, symbol: 'M' },
    { value: 900, symbol: 'CM' },
    { value: 500, symbol: 'D' },
    { value: 400, symbol: 'CD' },
    { value: 100, symbol: 'C' },
    { value: 90, symbol: 'XC' },
    { value: 50, symbol: 'L' },
    { value: 40, symbol: 'XL' },
    { value: 10, symbol: 'X' },
    { value: 9, symbol: 'IX' },
    { value: 5, symbol: 'V' },
    { value: 4, symbol: 'IV' },
    { value: 1, symbol: 'I' }
  ];
  let romanNum = '';

  for (let i = 0; i < romanNumerals.length; i++) {
    while (num >= romanNumerals[i].value) {
      romanNum += romanNumerals[i].symbol;
      num -= romanNumerals[i].value;
    }
  }
  return romanNum;
}
``` 

--------

## Test Cases: 

- `convertToRoman(2)` should return the string `II`.
- `convertToRoman(3)` should return the string `III`.
- `convertToRoman(4)` should return the string `IV`.
- `convertToRoman(5)` should return the string `V`.
- `convertToRoman(9)` should return the string `IX`.
- `convertToRoman(12)` should return the string `XII`.
- `convertToRoman(16)` should return the string `XVI`.
- `convertToRoman(29)` should return the string `XXIX`.
- `convertToRoman(44)` should return the string `XLIV`.
- `convertToRoman(45)` should return the string `XLV`.
- `convertToRoman(68)` should return the string `LXVIII`
- `convertToRoman(83)` should return the string `LXXXIII`
- `convertToRoman(97)` should return the string `XCVII`
- `convertToRoman(99)` should return the string `XCIX`
- `convertToRoman(400)` should return the string `CD`
- `convertToRoman(500)` should return the string `D`
- `convertToRoman(501)` should return the string `DI`
- `convertToRoman(649)` should return the string `DCXLIX`
- `convertToRoman(798)` should return the string `DCCXCVIII`
- `convertToRoman(891)` should return the string `DCCCXCI`
- `convertToRoman(1000)` should return the string `M`
- `convertToRoman(1004)` should return the string `MIV`
- `convertToRoman(1006)` should return the string `MVI`
- `convertToRoman(1023)` should return the string `MXXIII`
- `convertToRoman(3999)` should return the string `MMMCMXCIX`
