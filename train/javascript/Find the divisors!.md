# Find the divisors!

### Instructions

Create a function named divisors that takes an integer and returns an array with all of the integer's divisors(except for 1 and the number itself). If the number is prime return the string '(integer) is prime' (use Either String a in Haskell).

#### Example:

```js
divisors(12); //should return [2,3,4,6]
divisors(25); //should return [5]
divisors(13); //should return "13 is prime"
```

You can assume that you will only get positive integers as inputs.

### My Solution

<details>
  <summary>**Details**</summary>
  <p>
```js
function divisors(integer) {
  const result = [];
  for(i=2; i<integer; i++){
    integer % i === 0 && result.indexOf(i) === -1 && result.push(i);
  }
    
  return result.length === 0 ? `${integer} is prime` : result;
};
```
  </p>
</details>
