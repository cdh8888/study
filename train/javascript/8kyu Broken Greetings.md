# Broken Greetings

### Instructions

Correct this code so that the greet function returns the expected value.

### My Solution

<details>
  <summary>**Details**</summary>
  <p>
```js
function Person(name){
  this.name = name;
}

Person.prototype.greet = function(otherName){
  return "Hi " + otherName + ", my name is " + this.name;
}
```
  </p>
</details>
