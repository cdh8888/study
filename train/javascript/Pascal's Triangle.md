# **4kyu** Pascal's Triangle

### Instructions

#### Description:

#### Pascal's Triangle
![](https://upload.wikimedia.org/wikipedia/commons/0/0d/PascalTriangleAnimated2.gif)

Wikipedia article on Pascal's Triangle: http://en.wikipedia.org/wiki/Pascal's_triangle

Write a function that, given a depth (n), returns a single-dimensional array representing Pascal's Triangle to the n-th level.

#### For example:

```
pascalsTriangle(4) == [1,1,1,1,2,1,1,3,3,1]
```

### My Solution

<details>
  <summary>**Details**</summary>
  <p>
```js
function pascalsTriangle(n) {
  const result = new Array();
  for(i=0; i<n; i++){
  
    const array = new Array();
    for(j=0; j<i+1; j++){
      if(j !== 0 && i !== j){
        array.push(result[i-1][j-1] + result[i-1][j]);
      } else {
        array.push(1); 
      }
    }
    result.push(array);
  }
  
  return result.reduce((result, array)=>{ return result.concat(array); }, []);
}
```
  </p>
</details>
