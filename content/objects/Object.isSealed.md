+++
date = "2016-11-04T00:45:05+05:30"
title = "Object.isSealed()"
next = "/objects/Object.keys"
prev = "/objects/Object.isFrozen"
toc = true
weight = 26

+++

The Object.isSealed() method determines if an object is sealed.

<h3>Need for this</h3>
Returns true if existing property attributes cannot be modified in an object and new properties cannot be added to the object.

    Object.isSealed(obj)

An object is sealed if it is not extensible and if all its properties are non-configurable and therefore not removable (but not necessarily non-writable).

<h3>Advantages</h3>
<ol>
  <li>Using this we can find whether the properties be added to or deleted from an object.</li>
</ol>

<h3>Disadvantages</h3>
<ol>
  <li>Note that this is not a method to be invoked on an object: it is a global function and you must pass an object to it.</li>
</ol>

<h3>Working Example</h3>
The following example illustrates the use of the *Object.isSealed* function.

    // Create an object that has two properties.
     var obj = { pasta: "spaghetti", length: 10 };

     // Seal the object, and verify that it is sealed.
     Object.seal(obj);
     document.write(Object.isSealed(obj));
     document.write("<br/>");

     // Try to add a new property, and then verify that it is not added.
     obj.newProp = 50;
     document.write(obj.newProp);
     document.write("<br/>");

     // Try to delete a property, and then verify that it is still present.
     delete obj.length;
     document.write(obj.length);

     // Output:
     // true
     // undefined
     // 10

<h3>References</h3>
[https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/isSealed](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/isSealed)<br/>
[https://docs.webplatform.org/wiki/javascript/Object/isSealed](https://docs.webplatform.org/wiki/javascript/Object/isSealed)<br/>
[https://www.safaribooksonline.com/library/view/javascript-the-definitive/9781449393854/rn01re161.html](https://www.safaribooksonline.com/library/view/javascript-the-definitive/9781449393854/rn01re161.html)
