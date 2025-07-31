🔵 1 - Given a non-empty array of integers, return the result of multiplying the values together in order. Example:

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

🔵 2-Given a set of numbers, return the additive inverse of each. Each positive becomes negatives, and the negatives become positives.

```bash
[1, 2, 3, 4, 5] --> [-1, -2, -3, -4, -5]
[1, -2, 3, -4, 5] --> [-1, 2, -3, 4, -5]
[] --> []
```

Solution 1
```javascript
function invert(array) {
  array.forEach((item,index) => (array[index]= item * -1))
   return array;
}
```


Solution 2
```javascript
const invert = array => array.map(num => -num);
```

Solution 3 
```javascript
function invert(array) {
   return array.map( x => x === 0 ? x : -x);
}
```
Solution 4 
```javascript
function invert(array) {
  var newArr = [];
  for(var i = 0; i < array.length; i++){
    newArr.push(-array[i]);
  }
   return newArr;
}
```
