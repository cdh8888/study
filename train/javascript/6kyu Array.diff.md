# Array.diff

### Instructions

Your goal in this kata is to implement an difference function, which subtracts one list from another.

It should remove all values from list a, which are present in list b.

```js
difference([1,2],[1]) == [2]
```

If a value is present in b, all of its occurrences must be removed from the other:

```js
difference([1,2,2,2,3],[2]) == [1,3]
```

### My Solution

<details>
  <summary>**Details**</summary>
  <p>
```js
function array_diff(a, b) {

  let result = a;
  b.map((remove)=>{
    result = result.filter(function(num) {
    	return num != remove
    });
  })

  return result;
}
```
  </p>
</details>
