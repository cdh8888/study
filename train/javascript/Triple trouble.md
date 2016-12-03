# Triple trouble

### Instructions

Write a function

```js
tripledouble(num1,num2)
```

which takes in numbers num1 and num2 and returns 1 if there is a straight triple of a number at any place in num1 and also a straight double of the same number in num2.

#### For example:

```js
tripledouble(451999277, 41177722899) == 1 // num1 has straight triple 999s and 
                                          // num2 has straight double 99s

tripledouble(1222345, 12345) == 0 // num1 has straight triple 2s but num2 has only a single 2

tripledouble(12345, 12345) == 0

tripledouble(666789, 12345667) == 1
```

### My Solution

```js
function tripledouble(num1, num2) {
  const num1Exist = [000,111,222,333,444,555,666,777,888,999].filter((number)=>{ return num1.toString().indexOf(number) !== -1; });
  const num2Exist = [00,11,22,33,44,55,66,77,88,99].filter((number)=>{ return num2.toString().indexOf(number) !== -1; });
  
  return num2Exist.filter((number)=>{ return num1Exist.toString().indexOf(number) !== -1; }).length ? 1 : 0;
}
```
