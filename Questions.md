<h1>JavaScript Questions</h1>
<h3>Q: What are the different data types present in javascript?</h3>
<p><strong>Primitive types</strong> - Primitive data types can store only a single value. </p>
<ul>
  <li>
    <strong>String</strong> - It represents a series of characters and is written with quotes. A string can be represented using a single or a double quote. <br/>
    Example <br/>
    var str = "John Doe"; //using double quotes <br/>
    var str2 = 'John Doe'; //using single quotes <br/>
  </li>
  <li>
    <strong>Number</strong> - It represents a number and can be written with or without decimals. <br/>
    Example <br/>
    var x = 3; //without decimal <br/>
    var y = 3.6; //with decimal <br/>
  </li>
  <li>
    <strong>BigInt</strong> - This data type is used to store numbers which are above the limitation of the Number data type. It can store large integers and is represented      by adding “n” to an integer literal. <br/>
    Example <br/>
    var bigInteger =  234567890123456789012345678901234567890; <br/>
  </li>
  <li>
    <strong>Boolean</strong> - It represents a logical entity and can have only two values : true or false. Booleans are generally used for conditional testing.
  </li>
  <li>
    <strong>Undefined</strong> - When a variable is declared but not assigned, it has the value of undefined and it’s type is also undefined.
  </li>
  <li>
    <strong>Null</strong> - It represents a non-existent or a invalid value.
  </li>
  <li>
    <strong>Symbol</strong> - It is a new data type introduced in the ES6 version of javascript. It is used to store an anonymous and unique value.
  </li>
</ul>
<p><strong>Non-primitive types</strong> - To store multiple and complex values, non-primitive data types are used. </p>
<ul>
  <li>
    <strong>Object</strong> - Used to store collection of data. <br/>
    
    ```
    // Collection of data in key-value pairs
    var obj1 = {
      x:  43,
      y:  "Hello world!",
      z: function(){
        return this.x;
      }
    }
      
    // Collection of data as an ordered list 
    var array1 = [5, "Hello", true, 4.1];
    ```
  </li>
</ul>
<h3><strong>Q1: Is Javascript single-threaded?</strong></h3>
<h3><strong>Q2: Explain the main component of the javascript engine & how it works</strong></h3>
<h3><strong>Q3: Difference between var, let and const</strong></h3>
<h3>Q: Explain Hoisting in javascript</h3>
<p>Hoisting is the default behaviour of javascript where all the variable and function declarations are moved on top.</p>
<p>This means that irrespective of where the variables and functions are declared, they are moved on top of the scope. The scope can be both local and global.</p>

```
Example 1:

hoistedVariable = 3;
console.log(hoistedVariable); // outputs 3 even when the variable is declared after it is initialized	
var hoistedVariable;
```

```
Example 2:

hoistedFunction();  // Outputs " Hello world! " even when the function is declared after calling
function hoistedFunction(){ 
  console.log(" Hello world! ");
} 
```

```
Example 3:

// Hoisting takes place in the local scope as well
function doSomething(){
  x = 33;
  console.log(x);
  var x;
} 
// Outputs 33 since the local variable “x” is hoisted inside the local scope
```

<strong>Note - Variable initializations are not hoisted, only variable declarations are hoisted:</strong>

```
var x;
console.log(x); // Outputs "undefined" since the initialization of "x" is not hoisted
x = 23;
```

<strong>Note - To avoid hoisting, you can run javascript in strict mode by using “use strict” on top of the code:</strong>

```
"use strict";
x = 23; // Gives an error since 'x' is not declared
var x;
```
