+++
date = "2016-11-17T00:45:05+05:30"
title = "Object.getOwnPropertyDescriptor()"
next = "/objects/Object.getOwnPropertyNames"
prev = "/objects/Object.freeze"
toc = true
weight = 21

+++

The Object.getOwnPropertyDescriptor() method returns a property descriptor for an own property (that is, one directly present on an object and not in the object's prototype chain) of a given object.

<h3>Need for this</h3>
This method allows you to access the descriptor of a property. This method is the only way to get at this information (it is, otherwise, not available to the user – these don’t exist as visible properties on the property, they’re stored internally in the ECMAScript engine).

This method permits examination of the precise description of a property. A property in JavaScript consists of a string-valued name and a property descriptor. Further information about property descriptor types and their attributes can be found in Object.defineProperty().

<h3>Advantages</h3>
<ol>
  <li>You can use the Object.getOwnPropertyDescriptor function to obtain a descriptor object that describes attributes of the property.</li>
  <li>Object.getOwnPropertyDescriptor allows the developer to override the default browser properties which are otherwise not overridable. This can be useful during unit testing.</li>
</ol>

<h3>Working Example</h3>
```javascript
// Create a user-defined object.
var obj = {};

// Add a data property.
obj.newDataProperty = "abc";

// Get the property descriptor.
var descriptor = Object.getOwnPropertyDescriptor(obj, "newDataProperty");

// Change a property attribute.
descriptor.writable = false;
Object.defineProperty(obj, "newDataProperty", descriptor);

// Get the descriptor from the object.
var desc2 = Object.getOwnPropertyDescriptor(obj, "newDataProperty");

// List the descriptor attributes.
for (var prop in desc2) {
    document.write(prop + ': ' + desc2[prop]);
    document.write("<br />");
}

// Output:
// value: abc
// writable: false
// enumerable: true
// configurable: true
```
<h3>References</h3>
https://developer.mozilla.org/en/docs/Web/JavaScript/Reference/Global_Objects/Object/getOwnPropertyDescriptor
<br />
https://msdn.microsoft.com/en-us/library/dd548686(v=vs.94).aspx
<br />
http://www.2ality.com/2016/02/object-getownpropertydescriptors.html
<br />
https://docs.webplatform.org/wiki/javascript/Object/getOwnPropertyDescriptor
