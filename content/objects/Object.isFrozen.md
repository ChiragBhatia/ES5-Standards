+++
date = "2016-11-04T00:45:05+05:30"
title = "Object.isFrozen()"
next = "/objects/Object.isSealed"
prev = "/objects/Object.isExtensible"
toc = true
weight = 15

+++

The *Object.isFrozen()* determines if an object is frozen.

<h3>Need for this</h3>
Returns true if existing property attributes and values cannot be modified in an object, and new properties cannot be added to the object.<br/>

    Object.isFrozen(obj)

An object is frozen if and only if it is not extensible, all its properties are non-configurable, and all its data properties (that is, properties which are not accessor properties with getter or setter components) are non-writable.

<h3>Advantages</h3>
<ol>
  <li>Using this we can find whether the object is immutable or not.</li>
</ol>

<h3>Disadvantages</h3>
<ol>
  <li>Note that this is not a method to be invoked on an object: it is a global function and you must pass an object to it.</li>
</ol>

<h3>Working Example</h3>
The following example illustrates the use of the *Object.isFrozen* function.

    // Create an object that has two properties.
     var obj = { pasta: "spaghetti", length: 10 };

     // Freeze the object, and verify that it is frozen.
     Object.freeze(obj);
     document.write(obj.isFrozen());

     // Try to add a new property, and then verify that it is not added.
     obj.newProp = 50;
     document.write (obj.newProp);
     document.write ("<br/>");

     // Try to delete a property, and then verify that it is still present.
     delete obj.length;
     document.write (obj.length);
     document.write ("<br/> ");

     // Try to change a property value, and then verify that it is not changed.
     obj.pasta = "linguini";
     document.write (obj.pasta);

     // Output:
     // true
     // undefined
     // 10
     // spaghetti

<h3>References</h3>

[https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/isFrozen](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/isFrozen)<br/>
[https://docs.webplatform.org/wiki/javascript/Object/isFrozen](https://docs.webplatform.org/wiki/javascript/Object/isFrozen)<br/>
[https://www.safaribooksonline.com/library/view/javascript-the-definitive/9781449393854/rn01re159.html](https://www.safaribooksonline.com/library/view/javascript-the-definitive/9781449393854/rn01re159.html)

