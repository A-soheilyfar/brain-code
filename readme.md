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
---

🔵 4- Write a function that takes an array of words and smashes them together into a sentence and returns the sentence. You can ignore any need to sanitize words or add punctuation, but you should add spaces between each word. Be careful, there shouldn't be a space at the beginning or the end of the sentence!

```bash

['hello', 'world', 'this', 'is', 'great']  =>  'hello world this is great'

```
Solution 1
```javascript
function smash (words) {
  if (words == false){
    return ""
  }else{
    
  return words.reduce((accumulator = 0, currentValue)=> (accumulator +" "+ currentValue) )
  }
};
```

Solution 2
```javascript
smash = function (words) {
  return words.join(" ");
};
```

Solution 3
```javascript
const smash = words => words.join(' ');
```

Solution 4
```javascript
function smash (words) {
   return words.join(' ').trim();
};
```

