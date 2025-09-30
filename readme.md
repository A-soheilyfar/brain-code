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


---

🔵 6-Using an IF/ELSE statement, write a function closestToTheMark that takes two player inputs as number arguments. The function will return 'Player 1 is closest' or 'Player 2 is closest' depending on which player input is closest to the randomly generated number.

```javascript
function closestToTheMark(player1, player2){
  const theMark = Math.floor(Math.random() * 100)
  console.log(`If theMark is ${theMark}...`);
  // ADD CODE HERE
  if(Math.abs(theMark - player1 ) < Math.abs(theMark - player2) ){
    return 'Player 1 is closest'
  }else{
    return('Player 2 is closest')
  }
}

// Uncomment the line below to check your work!
 console.log(closestToTheMark(25, 75));
```
---


🔵 7- Write a function addingAllTheWeirdStuff which adds the sum of all the odd numbers in array2 to each element under 10 in array1. Similarly, addingAllTheWeirdStuff should also add the sum of all the even numbers in array2 to those elements over 10 in array1.

BONUS: If any element in array2 is greater than 20, add 1 to every element in array1.
```javascript

function addingAllTheWeirdStuff(array1, array2) {
  // ADD CODE HERE
  let sumOdd = 0;
  let sumEven = 0;
  //Sum of odd nums and Sum of Even Nums in array2
  for (let i = 0; i < array2.length; i++) {
    if (array2[i] % 2 == 0) {
      sumEven += array2[i];
    } else {
      sumOdd = sumOdd + array2[i];
    }
  }

  // adds the sum of all the odd numbers in array2 each element under 10 in arr1
  //add the sum of all the even numbers in array2 to those elements over 10 in array1.
  for (let y = 0; y < array1.length; y++) {
    if (array1[y] < 10) {
      array1[y] = sumOdd + array1[y];
    } else if (array1[y] > 10) {
      array1[y] = sumEven + array1[y];
    }
  }

  //If any element in array2 is greater than 20, add 1 to every element in array1.
  for (let i = 0;i < array2.length;i++) {
  	if (array2[i] > 20) {
       
  		for (let j = 0; j < array2.length; j++) {
   		   array1[j] += 1;
         
    }
      break;
       }
 
  }
    return array1;
}

// Uncomment these to check your work!
console.log(addingAllTheWeirdStuff([1, 3, 5, 17, 15], [1, 2, 3, 4, 5])); // expected log [10, 12, 14, 23, 21]
console.log(addingAllTheWeirdStuff([1, 3, 5, 17, 15, 1], [1, 29, 3, 4, 5, 22])); // expected log [11, 13, 15, 46, 44, 11]


```

```javascript

function addingAllTheWeirdStuff(array1, array2) {
  // ADD CODE HERE
  const oddSum = array2
    .filter((num) => num % 2 !== 0)
    .reduce((sum, num) => sum + num, 0);

  const evenSum = array2
    .filter((num) => num % 2 === 0)
    .reduce((sum, num) => sum + num, 0);

  // Check for elements > 20
  const hasElementOver20 = array2.some((num) => num > 20);

  // Transform array1 using map
  return array1.map((num) => {
    let newNum = num;

    if (num < 10) {
      newNum += oddSum;
    } else if (num > 10) {
      newNum += evenSum;
    }

    if (hasElementOver20) {
      newNum += 1;
    }

    return newNum;
  });
}
```
---

🔵 8- Write a function disemvowel that takes in a string and returns a new string with all vowels removed.

```javascript
function disemvowel(string) {
  // ADD CODE HERE
  let newstring = "";
  for (let item of string) {
    if (
      item !== "a" &&
      item !== "A" &&
      item !== "e" &&
      item !== "E" &&
      item !== "i" &&
      item !== "I" &&
      item !== "o" &&
      item !== "O" &&
      item !== "u" &&
      item !== "U" 
    )
      newstring += item;
  }
  return(newstring);
}
```

```javascript
function disemvowel(string) {
  // ADD CODE HERE
  let newstring = "";
  for (let item of string) {
 		if (!["a", "e", "i", "o", "u","A","E","I","O","U"].includes(item)) {
      newstring += item;
    }
  
}
  return(newstring);
}

```
---

🔵 9-Create a function addWaldo that accepts an object with keys being first names and values being last names. For example addWaldo({'Luke': 'Skywalker', 'Harley': 'Quinn', 'Ryan': 'Reynolds'}) should add the key 'Waldo' with the value 'unknown' to the object and return the mutated object.

```javascript

// ADD CODE HERE 
const addWaldo = (object)=>{ object.Waldo = "unknown" ;return siliconValley} 
// addWaldo(siliconValley)

// Uncomment these to check your work!
const siliconValley = {'Richard': 'Hendricks', 'Erlich': 'Bachman', 'Bertram': 'Gilfoyle'}
console.log(addWaldo(siliconValley)) // should log:{ Richard: 'Hendricks', Erlich: 'Bachman', Bertram: 'Gilfoyle', Waldo: 'unknown' }

```

```javascript

// ADD CODE HERE 
const addWaldo = (object)=>{return Object.assign(object , {"Waldo":"unknown"})} 
// addWaldo(siliconValley)

// Uncomment these to check your work!
const siliconValley = {'Richard': 'Hendricks', 'Erlich': 'Bachman', 'Bertram': 'Gilfoyle'}
console.log(addWaldo(siliconValley)) // should log:{ Richard: 'Hendricks', Erlich: 'Bachman', Bertram: 'Gilfoyle', Waldo: 'unknown' }

```
---


🔵 10-Create a function findWaldo that accepts an object and returns the value associated with the key 'Waldo'. If the key 'Waldo' is not found, the function should return 'Where's Waldo?'

```javascript
// ADD CODE HERE
let findWaldo = (object)=>{
  if(object.hasOwnProperty("Waldo")){
    return object["Waldo"]
  } else{
    return 'Where\'s Waldo?'
  }
}
// Uncomment these to check your work!
const DC = {'Bruce': 'Wayne', 'Harley': 'Quinn'}
const supernatural = {'Sam': 'Winchester', 'Dean': 'Winchester', 'Waldo': 'unknown'}
console.log(findWaldo(DC)) // should log: 'Where's Waldo?'
console.log(findWaldo(supernatural)) // should log: 'unknown'

```
---

🔵 11-Write a function arrayBuilder that takes in a count object and returns an array filled with the appropriate numbers of elements. The order of the elements in the array does not matter, but repeated elements should be grouped.

```javascript
function arrayBuilder(obj) {
  // ADD CODE HERE
  let resArr = []
  let repeatCount = 0
  
  for (let keys in obj) {
    repeatCount = obj[keys]   // مثلاً اگر obj = {a: 3, b: 2} باشه
                              // در اولین دور repeatCount = 3 میشه
    
    while (repeatCount > 0) { // تا وقتی که تعداد باقی مونده بیشتر از صفره
      resArr.push(keys)       // کلید رو اضافه کن
      repeatCount -= 1        // یکی از تعداد کم کن
    }
  }
  
  return resArr
}

```



```javascript
function arrayBuilder(obj) {
  let resArr = []
  for (let [key, count] of Object.entries(obj)) {
    for (let i = 0; i < count; i++) {
      resArr.push(key)
    }
  }
  return resArr
}

```

```javascript
function arrayBuilder(obj) {
  return Object.entries(obj)
    .map(([key, count]) => Array(count).fill(key)) // مثلاً [["a","a"], ["b","b","b"]]
    .flat() // همه رو تبدیل می‌کنه به یه آرایه یک‌بعدی
}

```


```javascript
function arrayBuilder(obj) {
  return Object.entries(obj).reduce((acc, [key, count]) => {
    return acc.concat(Array(count).fill(key))
  }, [])
}

```
---

🔵 12- Write a function named setAlarm/set_alarm/set-alarm/setalarm (depending on language) which receives two parameters. The first parameter, employed, is true whenever you are employed and the second parameter, vacation is true whenever you are on vacation.

```bash

employed | vacation 
true     | true     => false
true     | false    => true
false    | true     => false
false    | false    => false
```

```javascript
function setAlarm(employed, vacation){
if(employed && vacation){
  return false
}else if(vacation){
  return false
}else if(!employed && !vacation){
  return false
}
  else{
  return true
}
}

```

```javascript
const setAlarm = (employed, vacation) => employed && !vacation;

```

```javascript
function setAlarm(employed, vacation){
  return employed && !vacation;
}

```


```javascript
function setAlarm(employed, vacation){
  return (employed && !vacation) ? true : false;
}

```

