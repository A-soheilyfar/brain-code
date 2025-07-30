1 - Given a non-empty array of integers, return the result of multiplying the values together in order. Example:

`[1, 2, 3, 4] => 1 * 2 * 3 * 4 = 24`


Solution: 
```javascript
//Solution 1
const grow=x=> x.reduce((a,b) => a*b);

//Solution 2
const grow = (nums) => nums.reduce((product, num) => product * num, 1);

//Solution 3
function grow(x){
 let acc = 1 
 for(i=x.length-1;i >=0;i--){
  acc = acc * x[i]
 }
  return acc
}

//Solution 4
const grow = x => {
  let res = 1;
  for (let i = 0; i < x.length; i++) {
    res *= x[i];
  }
  return res;
};
```
---


