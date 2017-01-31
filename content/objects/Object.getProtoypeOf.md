+++
date = "2016-11-17T00:45:05+05:30"
title = "Object.getPrototypeOf()"
next = "/objects/Object.isExtensible"
prev = "/objects/Object.getOwnPropertyNames"
toc = true
weight = 23

+++

The Object.getPrototypeOf() method returns the prototype (i.e. the value of the internal [[Prototype]] property) of the specified object.

<h3>Need for this</h3>
A common question at this point (and one that’s sure to come up often as new features start to trickle in from ECMAScript 3.1): Why is the method  Object.getPrototypeOf("test") and not "test".getPrototypeOf() – or even just a property, like __proto__? While having a method, or property, on every object would certainly be more convenient to use it ends up being impractical for generalized use.

For example, take the following case into consideration:

[js]var obj = { getPrototypeOf: “blah” };[/js]

Any attempt to call its getPrototypeOf method would end in failure, forcing the developer to always have to fall back to using the generalized  Object.getPrototypeOf. Since most uses of getPrototypeOf would be required to work in the general case the fallback would always have to be used. Thus it’s not necessary to include it as an extra property of every object.

Additionally, it makes it far easier to backport to old implementations since you no longer have to extend the Object prototype (Object.prototype.getPrototypeOf = ...;) which would’ve been bad in any case.

<h3>Advantages</h3>
<ol>
  <li>You can use the Object.getPrototypeOf function to validate data types.</li>
</ol>

<h3>Working Example</h3>
```javascript
var proto = {};
var obj = Object.create(proto);
Object.getPrototypeOf(obj) === proto; // true
```

<h3>References</h3>
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/getPrototypeOf
<br />
https://msdn.microsoft.com/nl-nl/library/ff877835(v=vs.94).aspx
<br />
http://docs.w3cub.com/javascript/global_objects/object/getprototypeof/
<br />
http://ejohn.org/blog/objectgetprototypeof/