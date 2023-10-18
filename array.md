## JavaScript Array methods:

### filter()
filter() returns a new array of filter elements that meet a certain condition. The filter() method creates a new array with all elements that pass the test implemented by the provided function.<br/>
filter() does not execute the function for array elements without values and doesn't change the original array.<br/><br/>
Syntax:
```
array.filter(function(currentValue, index, arr), thisValue)
```

<b>function(currentValue, index, arr) is required.</b> <br/><br/>
A function to be run for each element in the array, function arguments are:<br/>
<b>currentValue</b> - required, the value of the current element<br/>
<b>index</b> - optional, the array index of the current element<br/>
<b>arr</b> - optional, the array object the current element belongs to.<br/>
<b>thisValue</b> - optional. A value to be passed to the function to be used as its "this" value. If this parameter is empty, the value "undefined" will be passed as its "this" value.<br/><br/>

Example:
```
const words = ['spray', 'limit', 'elite', 'exuberant', 'destruction', 'present'];
const result = words.filter(word => word.length > 6);
console.log(result);
Output: ["exuberant", "destruction", "present"]
```

```
[10, 20, 30, 40].filter(function() {
  return true;
})
Output: [10, 20, 30, 40]

[10, 20, 30, 40].filter(function(e) {
  return e < 30;
})
Output: [10, 20]

[10, 20, 30, 40].filter(function(e, index) {
  return index % 2 === 0;
})
Output: [10, 30]
```

```
const myArray = [
  { id: 1, name: "Mark" },
  { id: 2, name: "Sam" },
  { id: 3, name: "Sandy" },
  { id: 4, name: "Mark" },
]
myArray.filter(element => element.name === "Mark")

Output:
0:{id: 1, name: "Mark"},
1:{id: 4, name: "Mark"}
```
