---
layout: post
title: How / Why Use Objects in JavaScript?
description: Object oriented Programming (<code>OOP</code>) in JavaScript is based on a simple object-based paradigm. The name shouldn't intimidate you as an understanding of objects is cruicial to understanding JavaScript as a whole. 
manualdate: February 13, 2015
---

Object oriented Programming (<code>OOP</code>) in JavaScript is based on a simple object-based paradigm. The name shouldn't intimidate you as an understanding of objects is cruicial to understanding JavaScript as a whole. Almost everything in JavaScript is an object, functions are objects to and can be passed around as a reference. 

We use objects as building blocks for our applications that allow us to adopt valuable industry standard techniques like <code>encapsulation</code>, <code>inheritance</code>, <code>polymorphism</code>. These techniques aren't new, just like <code>closures</code> aren't a new phenomenon - they have been around for a while!

Much like variables are containers for data values, objects are data written as name: value pairs and are extremely useful for making a single unit out of values that are related or belong together. A JavaScript object has properties that are associated with it and the properties of an object succinctly define the characteristics of the object.

Note: Objects don't have classes like Java, however one way to create and use objects is the constructor pattern. To put it simply an Object is ultimately a function in JavaScript.

Assuming you don't know much about OOP it's best to try and understand some of the concepts below while conceptualizing features of an object using the table below:

<table>
  <thead>
    <tr>
      <th>Object Feature</th>
      <th>Concept</th>
    </tr>
  </thead>
  <tbody>
     <tr>
      <td>Alex is a human</td>
      <td>Object(s)</td>
    </tr>
    <tr>
      <td>Alex has black hair, is 6 feet tall and is a female</td>
      <td>Object Properties</td>
    </tr>
    <tr>
      <td>Alex can walk, speak and run</td>
      <td>Methods</td>
    </tr>
    <tr>
      <td>Alex is an instace of a class homo sapien</td>
      <td>Classical class in OOP</td>
    </tr>
    <tr>
      <td>Alex is also based on another object, called creature</td>
      <td>Prototype</td>
    </tr>
  </tbody>
</table>

By using a simple example, lets create this object with it's <code>properties</code>, <code>methods</code> and a <code>prototype</code> (which other instances can inherit from):

```javascript
function Human(firstName, lastName, gender, age) {
 // we use the this keyword to set context to reference our object: Human
 // a fundamental understand of context is vital to understand objects, expecially
 // when invoking. Don;t confuse context with scope (which is used for functions)
  this.firstName = firstName; 
  this.lastName = lastName;
  this.gender = gender;
  this.age = age;
}

Human.prototype = {
// let's use our Human object's prototype to add some methods to that all
// instances of our object can share! An method is simply a function within
// an object
  getFullName: function() { 
    return this.firstName + ' ' + this.lastName;
    },
  isMale: function() { 
    return this.gender == 'Male'; 
    },
  isFemale: function() { 
    return this.gender == 'Female'; 
  },
  getFullNameReversed: function() {
    return this.lastName + ', ' + this.firstName;
  }
};

// create some instances and store them in a variable using the new keyword
var jose = new Human('Jose', 'Carlos', "Male", "25");
var jennifer = new Human('Jennifer', 'Dewitt', 'Female', 43);

// view are newly created instances of our object Human
console.log(jose);
console.log(jennifer);

// now let's use some of our methods from prototype:
console.log(jennifer.getFullName()); //==> Jennifer Dewitt
console.log(jose.getFullName()); //==> Jose Carlos

// checking our object and instances using typeof and instanceof
console.log(typeof jose, typeof jennifer); //=> [object object]
console.log(jose instanceof Human, jennifer instanceof Human); //==> [true true]

// testing to see whether our getFullNameReversed method works!
console.log(jose.getFullNameReversed()); //==> Carlos, Jose
```

So this works as expected - it might look daunting but if you actually try a practical example and work your way through it, it's quite easy to understand. Take for example a handful of data elements that pretty much do the same thing but a more functional approach to relatively the same code:

```javascript
function getFullName(firstName, lastName) {
  return firstName + ' ' + lastName;
}

function isMale(gender) {
  return gender == 'Male';
}

function isFemale(gender) {
  return gender == 'Female';
}

var joseFirstName = 'Jose';
var joseLastName = 'Carlos';
var jenniferGender = 'Jennifer';
var jenniferAge = 43;
var jeffGender = 'Male';
var jeffLastName = 'Doe';
var jeffFirstName = 'John';


console.log(getFullName(joseFirstName, joseLastName));
console.log(isMale(jeffGender));
```
Our first example using object s doesn't inherently provide organizaton, but is extremely useful for orgainzing one's information (think about hundreds, maybe thousands of instances or functions which result in too much code).

It makes sense to organize your data if can be encapsulated and represented as whole objects rather than just a handful of data elements. Learning how to create and use objects is the first step to OOP, first understand and tackle this and then move on to inheritence.
