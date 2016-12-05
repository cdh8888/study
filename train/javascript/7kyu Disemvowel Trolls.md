# Disemvowel Trolls

### Instructions

Trolls are attacking your comment section!

A common way to deal with this situation is to remove all of the vowels from the trolls' comments, neutralizing the threat.

Your task is to write a function that takes a string and return a new string with all vowels removed.

For example, the string "This website is for losers LOL!" would become "Ths wbst s fr lsrs LL!".

### My Solution

<details>
  <summary>**Details**</summary>
  <p>
```js
function disemvowel(str) {
    
  // first case
  function firstCase(str){
   ['a', 'i', 'e', 'u', 'o'].map((char)=>{
      str = str.replace(new RegExp(char,'gi'),'');
    });
    
    return str;
  }
  
  // two case
  function secondCase(str){
   return Array.from(str).filter((char)=>{
      return ['a', 'i', 'e', 'u', 'o'].indexOf(char.toLowerCase()) <= -1;
    }).join('');
  }

  return firstCase(str);
}
```
  </p>
</details>
