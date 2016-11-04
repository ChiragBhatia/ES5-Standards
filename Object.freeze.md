+++
date = "2016-11-04T00:45:05+05:30"
title = "Object.freeze()"

+++

The *Object.freeze()* method freezes an object: that is, prevents new properties from being added to it; prevents existing properties from being removed; and prevents existing properties, or their enumerability, configurability, or writability, from being changed. In essence the object is made effectively immutable. The method returns the object being frozen.

<h3>Need for this</h3>
Prevents the modification of existing property attributes and values, and prevents the addition of new properties.

    Object.freeze(obj)

Nothing can be added to or removed from the properties set of a frozen object. Any attempt to do so will fail, either silently or by throwing a TypeError exception (most commonly, but not exclusively, when in strict mode).

Values cannot be changed for data properties. Accessor properties (getters and setters) work the same (and still give the illusion that you are changing the value). Note that values that are objects can still be modified, unless they are also frozen.

<h3>Advantages</h3>
<ol>
  <li>You can use this when you have an object representing a logically immutable data structure, especially if:
   <ul><li>Changing the properties of the object or altering its "duck type" could lead to bad behavior elsewhere in your application</li>
   <li>The object is similar to a mutable type or otherwise looks mutable, and you want programmers to be warned on attempting to change it rather than obtain undefined behavior.</li>
   </ul>
  </li>
  <li>Freezing an object is the ultimate form of lock-down. Once an object has been frozen it cannot be unfrozen – nor can it be tampered in any manner. This is the best way to make sure that your objects will stay exactly as you left them, indefinitely</li>
</ol>

<h3>Disadvantages</h3>
<ol>
  <li>In ES5, if the argument to this method is not an object (a primitive), then it will cause a TypeError. In ES6, a non-object argument will be treated as if it were a frozen ordinary object, and be simply returned.</li>
</ol>

<h3>Working Example</h3>
The following example illustrates the use of the *Object.freeze* function.


    // Create an object that has two properties.
     var obj = { pasta: "spaghetti", length: 10 };
     
     // Freeze the object.
     Object.freeze(obj);
     
     // Try to add a new property, and then verify that it is not added. 
     obj.newProp = 50;
     document.write(obj.newProp);
     document.write("<br/>");
     
     // Try to delete a property, and then verify that it is still present. 
     delete obj.length;
     document.write(obj.length);
     document.write("<br/>");
     
     // Try to change a property value, and then verify that it is not changed. 
     obj.pasta = "linguini";
     document.write(obj.pasta);
     
     // Output:
     // undefined
     // 10
     // spaghetti


<h3>References</h3>
[https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/freeze](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/freeze)
[https://docs.webplatform.org/wiki/javascript/Object/freeze](https://docs.webplatform.org/wiki/javascript/Object/freeze)

