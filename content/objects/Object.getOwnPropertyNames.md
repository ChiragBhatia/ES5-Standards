+++
date = "2016-11-17T00:45:05+05:30"
title = "Object.getOwnPropertyNames()"
next = "/objects/Object.getPrototypeOf"
prev = "/objects/Object.getOwnPropertyDescriptor"
toc = true
weight = 13

+++

The Object.getOwnPropertyNames() method returns an array of all properties (enumerable or not) found directly upon a given object.


<h3>Need for this</h3>
Object.getOwnPropertyNames() returns an array whose elements are strings corresponding to the enumerable and non-enumerable properties found directly upon obj. The ordering of the enumerable properties in the array is consistent with the ordering exposed by a for...in loop (or by Object.keys()) over the properties of the object. The ordering of the non-enumerable properties in the array, and among the enumerable properties, is not defined.

<h3>Advantages</h3>
<ol>
  <li>You can use the Object.getOwnPropertyNames function to obtain a list of non-enumerable only objects from an array.</li>
</ol>

<h3>Working Example</h3>
```javascript
var arr = ['a', 'b', 'c'];
console.log(Object.getOwnPropertyNames(arr).sort()); 
// logs ["0", "1", "2", "length"]

// Array-like object
var obj = { 0: 'a', 1: 'b', 2: 'c' };
console.log(Object.getOwnPropertyNames(obj).sort()); 
// logs ["0", "1", "2"]

// Logging property names and values using Array.forEach
Object.getOwnPropertyNames(obj).forEach(function(val, idx, array) {
  console.log(val + ' -> ' + obj[val]);
});
// logs
// 0 -> a
// 1 -> b
// 2 -> c

// non-enumerable property
var my_obj = Object.create({}, {
  getFoo: {
    value: function() { return this.foo; },
    enumerable: false
  }
});
my_obj.foo = 1;

console.log(Object.getOwnPropertyNames(my_obj).sort()); 
// logs ["foo", "getFoo"]
```
<h3>Exceptions</h3>
If the value supplied for the object argument is not the name of an object, a TypeError exception is thrown.

<h3>References</h3>
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/getOwnPropertyNames
<br />
https://msdn.microsoft.com/en-us/library/ff688126(v=vs.94).aspx
