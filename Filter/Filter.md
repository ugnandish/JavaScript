<div>
  <h1>Filter</h1>
  <p>The <b>Filter()</b> method takes each element in an array and it applies a conditional statement against it.
  <br/>If the conditional returns true, the element gets pushed to the output array.
  <br/>If the conditional returns false, the element does not get pushed to the output array.
  <br/>the Filter() method does not change the original array.</p>
</div>

```
var array1 = ['a', 'b', 'c', 'd'];
var array2 = ['a', 'e', 'f', 'b'];
array1 = array1.filter(val => !array2.includes(val));
document.write(array1); 

Output: c, d
```

  
