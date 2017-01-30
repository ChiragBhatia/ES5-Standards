+++
date = "2016-11-04T00:45:05+05:30"
title = "Object.preventExtensions()"
next = "/js/Object.preventExtensions"
prev = "/js/Object.keys"
toc = true
weight = 18

+++

The *Object.preventExtensions()* method prevents new properties from ever being added to an object (i.e. prevents future extensions to the object).

<h3>Need for this</h3>
Prevents the addition of new properties to an object.

    Object.preventExtensions(obj)

*Object.preventExtensions()* marks an object as no longer extensible, so that it will never have properties beyond the ones it had at the time it was marked as non-extensible. Note that the properties of a non-extensible object, in general, may still be deleted. Attempting to add new properties to a non-extensible object will fail, either silently or by throwing a TypeError (most commonly, but not exclusively, when in strict mode).

*Object.preventExtensions()* only prevents addition of own properties. Properties can still be added to the object prototype. However, calling Object.preventExtensions() on an object will also prevent extensions on its __proto__  property.

<h3>Advantages</h3>
<ol>
  <li>Preventing extenstions using this method is an excellent way to ensure that your objects aren't modified without your knowledge.</li>
  <li>If you are a library author, you may want to lock down certain parts of the core library to make sure they're not accidentally changed or to enforce where extensions are allowed to live.</li>
</ol>

<h3>Disadvantages</h3>
<ol>
  <li><i>Object.preventExtensions()</i> sets the extensible attribute of o to false so that no new properties can be added to it. This is a permanent change: once an object has been made non-extensible, it cannot be make extensible again.</li>
  <li>Note that Object.preventExtensions() does not affect the prototype chain, and a nonextensible object can still gain new inherited properties.</li>
  <li>Note that this is not a method to be invoked on an object: it is a global function and you must pass an object to it.</li>
</ol>


<h3>Working Example</h3>
The following example illustrates the use of the *Object.preventExtensions* function.

    // Create an object that has two properties.
     var obj = { pasta: "spaghetti", length: 10 };

     // Make the object non-extensible.
     Object.preventExtensions(obj);
     document.write(Object.isExtensible(obj));
     document.write("<br/>");

     // Try to add a new property, and then verify that it is not added.
     obj.newProp = 50;
     document.write(obj.newProp);

     // Output:
     // false
     // undefined


<h3>References</h3>
[https://developer.mozilla.org/en/docs/Web/JavaScript/Reference/Global_Objects/Object/preventExtensions](https://developer.mozilla.org/en/docs/Web/JavaScript/Reference/Global_Objects/Object/preventExtensions)
[https://docs.webplatform.org/wiki/javascript/Object/preventExtensions](https://docs.webplatform.org/wiki/javascript/Object/preventExtensions)
