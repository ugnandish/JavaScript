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
