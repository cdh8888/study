# Valid Parentheses

### Instructions

Write a function called validParentheses that takes a string of parentheses, and determines if the order of the parentheses is valid. validParentheses should return true if the string is valid, and false if it's invalid.

#### Examples: 

```js
validParentheses( "()" ) => returns true 
validParentheses( ")(()))" ) => returns false 
validParentheses( "(" ) => returns false 
validParentheses( "(())((()())())" ) => returns true 
```

All input strings will be nonempty, and will only consist of open parentheses '(' and/or closed parentheses ')'

### My Solution

<details>
  <summary>**Details**</summary>
  <p>
```js
function validParentheses(parens){
 
  let previous = "";
  while (parens.length !== previous.length){
    previous = parens;
    parens = parens.replace("()", "")             
  }

  return parens.length === 0;
}
```
  </p>
</details>
