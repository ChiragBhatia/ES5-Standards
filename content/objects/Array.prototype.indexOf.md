+++
date = "2016-11-16T00:45:05+05:30"
title = "Array.prototype.indexOf()"
next = "/objects/Array.prototype.lastIndexoF"
prev = "/objects/Array.prototype.forEach"
toc = true
weight = 5

+++

Returns the index of the first occurrence of a value in an array.

<h3>Need for this</h3>
Array.prototype.indexOf() compares searchElement to elements of the Array using strict equality (the same method used by the === or triple-equals operator).

<h3>Advantages</h3>
<ol>
	<li>To locate values in an array.</li>
	<li>Finding all the occurrences of an element</li>
	<li>Finding if an element exists in the array or not and updating the array</li>
</ol>

<h3>Working Example</h3>

//Example 1
var array = [2, 9, 9];
array.indexOf(2);     // 0
array.indexOf(7);     // -1
array.indexOf(9, 2);  // 2
array.indexOf(2, -1); // -1
array.indexOf(2, -3); // 0

//Example 2
//Finding all the occurrences of an element
var indices = [];
var array = ['a', 'b', 'a', 'c', 'a', 'd'];
var element = 'a';
var idx = array.indexOf(element);
while (idx != -1) {
  indices.push(idx);
  idx = array.indexOf(element, idx + 1);
}
console.log(indices);
// [0, 2, 4

//Example 3
//Finding if an element exists in the array or not and updating the array
function updateVegetablesCollection (veggies, veggie) {
    if (veggies.indexOf(veggie) === -1) {
        veggies.push(veggie);
        console.log('New veggies collection is : ' + veggies);
    } else if (veggies.indexOf(veggie) > -1) {
        console.log(veggie + ' already exists in the veggies collection.');
    }
}

var veggies = ['potato', 'tomato', 'chillies', 'green-pepper'];

updateVegetablesCollection(veggies, 'spinach'); 
// New veggies collection is : potato,tomato,chillies,green-papper,spinach
updateVegetablesCollection(veggies, 'spinach'); 
// spinach already exists in the veggies collection.

<h3>References</h3>
https://developer.mozilla.org/en/docs/Web/JavaScript/Reference/Global_Objects/Array/indexOf
<br>
https://msdn.microsoft.com/en-us/library/ff679977(v=vs.94).aspx
