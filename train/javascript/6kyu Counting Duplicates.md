# Counting Duplicates

### Instructions

#### Count the number of Duplicates

Write a function that will return the count of distinct case-insensitive alphabetic characters and numeric digits that occur more than once in the input string. The input string can be assumed to contain only alphanumeric characters, including digits, uppercase and lowercase alphabets.

#### Example

```
"abcde" -> 0 # no characters repeats more than once
"aabbcde" -> 2 # 'a' and 'b'
"aabbcdeB" -> 2 # 'a' and 'b'
"indivisibility" -> 1 # 'i'
"Indivisibilities" -> 2 # 'i' and 's'
"aa11" -> 2 # 'a' and '1'
```

### My Solution

<details>
  <summary>**Details**</summary>
  <p>
```js
function duplicateCount(text){

  const textUpperCase = text.toUpperCase();
  const overlap = [];
  for(char of textUpperCase){
    overlap.indexOf(char) === -1 && textUpperCase.split(char).length > 2 && overlap.push(char);
  }
  return overlap.length;
}
```
  </p>
</details>
