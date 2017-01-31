+++
date = "2016-11-17T00:45:05+05:30"
title = "Object.seal()"
next = "/objects/StrictMode"
prev = "/objects/Object.preventExtensions"
toc = true
weight = 29

+++

The Object.seal() method seals an object, preventing new properties from being added to it and marking all existing properties as non-configurable. Values of present properties can still be changed as long as they are writable.

<h3>Need for this</h3>
By default, objects are extensible (new properties can be added to them). Sealing an object prevents new properties from being added and marks all existing properties as non-configurable. This has the effect of making the set of properties on the object fixed and immutable. Making all properties non-configurable also prevents them from being converted from data properties to accessor properties and vice versa, but it does not prevent the values of data properties from being changed. Attempting to delete or add properties to a sealed object, or to convert a data property to accessor or vice versa, will fail, either silently or by throwing a TypeError (most commonly, although not exclusively, when in strict mode code).

The prototype chain remains untouched. However, the __proto__  property is sealed as well.

<h3>Advantages</h3>
<ol>
  <li>Makes the object non-extensible, so that new properties cannot be added to it.</li>
  <li>Sets the configurable attribute to false for all properties of the object.</li>
  <li>When the configurable attribute is false, property attributes cannot be changed and the property cannot be deleted. When configurable is false and writable is true, the value and writable attributes can be changed.
The Object.seal function does not change the writable attribute.
For more information about how to set property attributes, see Object.defineProperty Function (JavaScript). To get the attributes of a property, you can use the Object.getOwnPropertyDescriptor Function (JavaScript).</li>
</ol>

<h3>Working Example</h3>
```javascript
var obj = {
  prop: function() {},
  foo: 'bar'
};

// New properties may be added, existing properties may be changed or removed.
obj.foo = 'baz';
obj.lumpy = 'woof';
delete obj.prop;

var o = Object.seal(obj);

o === obj; // true
Object.isSealed(obj); // === true

// Changing property values on a sealed object still works.
obj.foo = 'quux';

// But you can't convert data properties to accessors, or vice versa.
Object.defineProperty(obj, 'foo', { get: function() { return 'g'; } }); // throws a TypeError

// Now any changes, other than to property values, will fail.
obj.quaxxor = 'the friendly duck'; // silently doesn't add the property
delete obj.foo; // silently doesn't delete the property

// ...and in strict mode such attempts will throw TypeErrors.
function fail() {
  'use strict';
  delete obj.foo; // throws a TypeError
  obj.sparky = 'arf'; // throws a TypeError
}
fail();

// Attempted additions through Object.defineProperty will also throw.
Object.defineProperty(obj, 'ohai', { value: 17 }); // throws a TypeError
Object.defineProperty(obj, 'foo', { value: 'eit' }); // changes existing property value
```

<h3>References</h3>
https://developer.mozilla.org/en/docs/Web/JavaScript/Reference/Global_Objects/Object/seal
<br />
https://msdn.microsoft.com/da-dk/library/ff806192(v=vs.94).aspx
<br/>
https://www.safaribooksonline.com/library/view/javascript-the-definitive/9781449393854/rn01re165.html
<br/>
http://www.2ality.com/2013/08/protecting-objects.html
