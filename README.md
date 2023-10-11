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
