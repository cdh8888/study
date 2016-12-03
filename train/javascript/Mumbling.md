# Mumbling

### Instructions

This time no story, no theory. The examples below show you how to write function accum:

Examples:

```js
accum("abcd");    // "A-Bb-Ccc-Dddd"
accum("RqaEzty"); // "R-Qq-Aaa-Eeee-Zzzzz-Tttttt-Yyyyyyy"
accum("cwAt");    // "C-Ww-Aaa-Tttt"
```

### My Solution

```js
function accum(s) {
  // your code
  let arr = Array.from(s.toUpperCase());
  return arr.map(function(char, index){
    return char.concat(char.repeat(index).toLowerCase());
  }).join('-');
}
```
