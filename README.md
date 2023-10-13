## Types of Loops in JavaScript
Loop is a process that repeats a particular block of code for a valid condition <br/>
### While Loop
The while statement generates a loop that gets executed over a particular block of statement (code) as long as the condition is true. Every time before executing the block of code the condition gets checked. <br/><br/>
Syntax
```
while (condition) {
  Block of code
}
```
Example
```
var i=8;
while (i<10) {
  console.log("I is less than 10");
  i++;

}
```

### do-while Loop
do-while loop is slightly different from while as it includes one extra feature. In case of do-while loop, the block of code gets executed at least once and if further the condition satisfies the code block will be executed accordingly. <br/><br/>
Syntax
```
do {
  Block of code
}
while (condition);
```
Example
```
var i=7;
do  {
  console.log("The value of i is " + i);
  i++;
}
while(i>7 && i<10);
```

### For Loop
The while loop and the for loop works exactly same, even the execution time doesn’t differ much. So what is the need of another looping system that delivers same functionality? in case of for loop the declaration & initialization of looping variable, condition checking & increment or decrements of the looping variable can be done in the same line. It increases the readability & reduces the chances of error. <br/> <br/>
Syntax
```
for ([initialization]; [condition]; [final-expression]) {
   Block of code
}
```

Example
```
for (var i=0; i<10; i++) {
  console.log("The Value of i Is " + i);
}
```

### forEach Loop
It is a prototypal method of Array (Even Map and Set). The forEach() method calls a given function/callback every time with each element in an array, according to the index order.<br/> 
Take note, forEach() does not run the given function for array elements having no values. <br/><br/>
Syntax
```
arrayName.forEach(function(currentValue, index, array) {
  function body
})
```

The forEach() method takes a function as an argument. The function consists of three parameters mentioned above. <br/>
the currentValue holds the present value being processed. <br/>
the index variable holds the index of the value in that particular array. <br/>
and the array variable holds the total array passed. <br/><br/>

You can iterate over a set using forEach(). <br/>
map can also be iterated using forEach() method. <br/><br/>
Example
```
var arr=[10, 20, "hi", ,{}];
arr.forEach(function(item, index) {
  console.log(' arr['+index+'] is '+ item);
});
```

The forEach() method is iterating over the arr array. If you have no use of the index, you can only use arr.forEach(function(item){}).The parameters can be used accordingly, you don’t have to mention all three every time. <br/>

The use of forEach() method has made iterating over an array very simple. We don’t have to worry about looping variable, conditions or anything else, it will take care of all the matters for iterating.

### for…in Loop
This one has been developed mainly to iterate over the properties of an object. The for...in statement iterates over the enumerable properties of an object. For each distinct property, statements can be executed.<br/>
As we know array is also a special kind of object, so don’t think array’s can’t be iterate using this for...in loop. <br/><br/>
Syntax
```
for (variableName in object) {
    Block of code
}
```

Example
```
var obj = {a: 1, b: 2, c: 3};    
for (var prop in obj) {
    console.log('obj.'+prop+'='+obj[prop]);
};
```

<b>Why array iteration using for...in loop is not preferable?</b><br/>
for...in should not be used for Array iteration specially where the order of the index is important.<br/>
Actually there is no difference between array indexes and a general object property, array indexes are just enumerable properties.<br/><br/>
The for...in won’t return the indexes in any particular order every time. for...in iterate This loop will return all enumerable properties, including those with non–integer names and those that are inherited.<br/><br/>
So it is recommended to use for or forEach() while iterating over an array. Because the order of iteration is implementation-dependent and iterating over an array may not visit elements in a consistent order in case of for...in.<br/>
```
var arr = [];
arr[2] = 2;
arr[3] = 3;
arr[0] = 0;
arr[1] = 1;
```

Using forEach() in this case will give an output 0, 1, 2, 3 where for...in it doesn’t guarantee anything. <br/><br/>

One more thing you should keep in mind while using for...in is, it iterates on all properties of the object; including the inherited ones (from parent class). If you just want to iterate on the object’s own properties, you should do something like the following. <br/>
```
for(var prop in obj){
    if(obj.hasOwnProperty(prop)){
        Code block here
    }
}
```

### for…of Loop
This one is the most recent looping type included in JS, introduced in ES6. Using for...of statement you can iterate over any iterable object like Array, String, Map, WeakMap, Set, WeakSet, arguments object, TypedArray and even general objects <br/><br/>
Syntax
```
for (variable of iterable) {
  Block of code
}
```

Example
```
var str= 'paul';
for (var value of str) {
  console.log(value);
}
```

<b>Iterating over map</b>
```
let itobj = new Map([['x', 0], ['y', 1], ['z', 2]]);
for (let kv of itobj) {
  console.log(kv);
}

for (let [key, value] of itobj) {
  console.log(value);
}
```

<b>How for...of is different from for...in ?</b>
The `for...in loop mainly iterates over the enumerable properties of an object in the actual insertion order.<br/>
The for...of statement iterates over the given values (not property names) of any iterable object.<br/><br/>

Object.prototype.objProto = function() {}; <br/>
Array.prototype.arrProto = function() {};<br/> 
```
let iterable = [8, 55, 9];
iterable.title = 'nandish';
for (let x in iterable) {
    console.log(x);
}

for (let i of iterable) {
    console.log(i); 
}
```

As you can see, for...of is all about the object’s own values and for...in considers even the prototypal and inherited property names. If you want to iterate on an object (and not an iterable), for...of will consider all its own properties; but in case of iterable, it will only consider the elements suitable to that kind of iterables. 

### map()
map is another prototypal method of Array. The map() method creates a new array having the returned values generated by a function execution over a given array.<br/><br/>

Syntax
```
var newArray= oldArray.map(function (currentValue, index, array){
    //Return element for the newArray
});
```

The map() method takes a function as a argument, the function having three parameters.<br/><br/>

The currentValue is the current element being processed in the array.<br/>
The index is the index of the current element being processed in the array.<br/>
And array is the array map was called upon.<br/>

Example
```
var num = [1, 5, 10, 15];
var doubles = num.map(function(x) {
   return x * 2;
});
```

## Types of Function in JavaScript
### Named Function
A function defined with a name that can be called by its name
```
function great(name) {
  return `Hello, from ${name}`;
}
console.log(great("Nandish"));

//output: Hello, from Nandish
```

### Anonymous Function (Function Expression)
A function without a name, often assigned to a variable
```
const add = function(a,b) {
  return a+b;
}
console.log(add(3,5));

//output: 8
```

### Arrow Function
A Arrow function introduced in ES6, useful for short functions
```
const add = (a,b) => a+b;
console.log(add(2,4));

//output: 6
```

### IIFE (Immediately Invoked Function Expression)
A function executed immediately after it's defined, often used for scoping
```
(function() {
  console.log("This is an IIFE");
})();

//output: This is an IIFE
```

### Callback Function
A function passed as an argument to another function, used for event handling and asynchronous operations
```
function fetchData(callback) {
  setTimeout(() => {
    const data = "Data from the server";
    callback(data);
  }, 1000);
}

fetchData((result) => {
  console.log(result);
});

//output: "Data from the server"
```

### Higher Order Function
Functions that takes other functions as argument
```
function operate(a, b, operation) {
  return operation(a, b);
}

const addFunc = (x, y) => x+y;
const subtractFunc = (x,y) => x-y;

console.log(operate(5,3, addFunc));
console.log(operate(5,3, subtractFunc));

//output: 8
//output: 2
```

### Generator Function
A function that allows pausing & resuming its execution, often used for managing sequence
```
function* countToFive() {
  for(let i=1; i<=5; i++) {
    yield i;
  }
}

const generator = countToFive();
for(const num of generator) {
  console.log(num);
}

//output
1
2
3
4
5
```

### Constructor Function
A function used to create objects with shared properties and methods when invoked with new
```
function Person(name, age) {
  this.name = name;
  this.age = age;
}

const person1 = new Person("Alice", 30);
const person2 = new Person("Bob", 25);

console.log(person1.name);
console.log(person1.age);
console.log(person2.name);
console.log(person2.age);

//output
Alice
30
Bob
25
```
