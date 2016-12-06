# Roman Numerals Decoder

### Instructions

Create a function that takes a Roman numeral as its argument and returns its value as a numeric decimal integer. You don't need to validate the form of the Roman numeral.

Modern Roman numerals are written by expressing each decimal digit of the number to be encoded separately, starting with the leftmost digit and skipping any 0s. So 1990 is rendered "MCMXC" (1000 = M, 900 = CM, 90 = XC) and 2008 is rendered "MMVIII" (2000 = MM, 8 = VIII). The Roman numeral for 1666, "MDCLXVI", uses each letter in descending order.

#### Example:

```
solution('XXI'); // should return 21

C# RomanDecode.Solution("XXI") -- should return 21
```

### My Solution

<details>
  <summary>**Details**</summary>
  <p>
```js
function solution(roman){
  const convertValue = {IV:4,I:1,V:5,XL:40,XC:90,X:10,L:50,CD:400,CM:900,C:100,D:500,M:1000};
  let result = 0;
  
  do {
    for (key in convertValue) {
      if(roman.indexOf(key) === -1){
        continue;
      }
      
      result += convertValue[key];
      roman=roman.replace(key, '');
      break;
    }
  
  } while(roman.length !== 0);
  
 return result;
}
```
  </p>
</details>
