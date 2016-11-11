+++
date = "2016-11-11T00:45:05+05:30"
title = "Array.prototype.some()"

+++

The *some()* method tests whether some element in the array passes the test implemented by the provided function.

<h3>Need for this</h3>
*.some()* will run the callback function for each element in the array. Once the callback returns true, .some() will return true. If the callback returns a falsy value for every element in the array then .some() returns false.

*.some()* will not change/mutate the array that called it.

    arr.some(callback[, thisArg])

some() executes the callback function once for each element present in the array until it finds one where callback returns a truthy value (a value that becomes true when converted to a Boolean). If such an element is found, some() immediately returns true. Otherwise, some() returns false. callback is invoked only for indexes of the array which have assigned values; it is not invoked for indexes which have been deleted or which have never been assigned values.

<h3>Advantages</h3>
<ol>  
  <li>Iterating over an array to search for an item is a pretty common task. With JavaScript, Array.prototype.forEach is often the popular choice. In some cases however, Array.prototype.some can be a better fit for the job if there is no need to search the entire array once a condition is fulfilled.</li>
  <li>.some() will not change/mutate the array that called it.</li>
</ol>


<h3>Working Example</h3>
The following example illustrates the use of the *Array.prototype.some()* function.

    var isEven = function isEven(currentElement, index, array) {
    if(currentElement % 2 === 0) {
    return true;
    } else {
    return false;
    }
    }
    
    var arr1 = [1, 2, 3, 4, 5, 6];
    arr1.some(isEven);  // returns true
    var arr2 = [1, 3, 5, 7];
    arr2.some(isEven);  // returns false

<h3>References</h3>
[https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/some](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/some)<br/>
[https://ariya.io/2013/08/searching-with-array-prototype-some](https://ariya.io/2013/08/searching-with-array-prototype-some)