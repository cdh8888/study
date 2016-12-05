# Vasya - Clerk

### Instructions

The new "Avengers" movie has just been released! There are a lot of people at the cinema box office standing in a huge line. Each of them has a single 100, 50 or 25 dollars bill. A "Avengers" ticket costs 25 dollars.

Vasya is currently working as a clerk. He wants to sell a ticket to every single person in this line.

Can Vasya sell a ticket to each person and give the change if he initially has no money and sells the tickets strictly in the order people follow in the line?

Return YES, if Vasya can sell a ticket to each person and give the change. Otherwise return NO.

#### Examples:

```js
tickets([25, 25, 50]) // => YES 
tickets([25, 100])    // => NO. Vasya will not have enough money to give change to 100 dollars
```

### My Solution

<details>
  <summary>**Details**</summary>
  <p>
```js
function tickets(peopleInLine){
  let result = "YES";

  let retention50DollarsCount = 0; 
  let retention25DollarsCount = 0; 
  const ticketDollars = 25;
    
  peopleInLine.map((peopleIndollars)=>{

    let changeDollars = peopleIndollars-ticketDollars;

    while(true){
    
      // 50
      if(retention50DollarsCount > 0 && changeDollars >= 50) {
        changeDollars -= 50;
        retention50DollarsCount--;
        continue;
      }
      
      // 25
      if(retention25DollarsCount > 0 && changeDollars >= 25) {
        changeDollars -= 25;
        retention25DollarsCount--;
        continue;
      }
      
      break;
    }
    
    if(changeDollars > 0){
      return result = "NO";
    }

    peopleIndollars === 50 && retention50DollarsCount++;
    peopleIndollars === 25 && retention25DollarsCount++;  
  });

  return result;
}
```
  </p>
</details>
