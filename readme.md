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

🔵 3- Write a function that takes an array of words and smashes them together into a sentence and returns the sentence. You can ignore any need to sanitize words or add punctuation, but you should add spaces between each word. Be careful, there shouldn't be a space at the beginning or the end of the sentence!

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

---

🔵 4- Write a function mergingElements which adds each element in array1 to the corresponding element of array2 and returns the new array.

```javascript
function mergingElements(array1, array2){
  
  let array3=[]
	for(let i=0;i<array1.length;i++){
    array3.push(array1[i] + array2[i])
    
  }
      return array3
}

console.log(mergingElements([1, 2, 3, 4], [5, 6, 7, 8])); // expected log [6, 8, 10, 12]

```

به کمک map
```javascript
function mergingElements(array1, array2) {
    return array1.map((num, index) => num + array2[index]);
}


```

به کمک متد forEach

```javascript
function mergingElements(array1, array2) {
    let result = [];
    array1.forEach((num, index) => {
        result.push(num + array2[index]);
    });
    return result;
}
```

به کمک متد from
```javascript

function mergingElements(array1, array2) {
    return Array.from(array1, (num, index) => num + array2[index]);
}

```


---

🔵 5- Write a function mergingTripletsAndQuints which takes in two arrays as arguments. This function will return a new array replacing the elements in array1 if they are divisible by 3 or 5. The number should be replaced with the sum of itself added to the element at the corresponding index in array2.


```javascript

function mergingTripletsAndQuints(array1, array2) {
 
  let array3 = []
  for(let i=0;i<array1.length;i++){
    if(array1[i] % 3 ==0 || array1[i] % 5 == 0 ){
	      array3.push(array1[i] + array2[i])
    }else{
      array3.push(array1[i])
    }
  }
return array3
}


console.log(mergingTripletsAndQuints([1, 2, 3, 4, 5, 15], [1, 3, 6, 7, 8, 9])); // expected log [1, 2, 9, 4, 13, 24]

```


```javascript
function mergingTripletsAndQuints(array1, array2) {
 
  let array3 = []
  array1.forEach((item,index,array)=>{
    if(array[index] % 3 ==0 || array[index] % 5 ==0 ){
     array3.push(array[index] + array2[index])
    }else{
       array3.push(array[index])
    }
  })
return array3
}


console.log(mergingTripletsAndQuints([1, 2, 3, 4, 5, 15], [1, 3, 6, 7, 8, 9])); // expected log [1, 2, 9, 4, 13, 24]

```
