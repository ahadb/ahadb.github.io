---
title: ES6 - Generators
description: An exciting feature of ES6 is a new breed of function called the generator - they differ from normal functions with respect to "run to completion"
manualdate: Oct 10, 2015
category: JavaScript, ES6, ES6, Other
---

Generators are an exciting new feature and can be used as `iterators` as well as drastically help us write **asynchronous code**
* When you `invoke` a function it runs till completion before any other code can run because JS is always **single threaded**
* Generator functions allow you to **pause** a functions execution in a `synchronous` manner and return the value of an expression
* Inside the generator function body use the new `yield` keyword to pause the function intrinsically
* Use the `*` symbol to denote a generator function

Take a rudimentary example:

<pre><code class="language-javascript">function *myGenerator() {
  yield '1: First stab at generators';
  yield 2;
  yield '3: Use next() to start iterating';
  yield 4
  yield "5: Normal functions 'run to completion'";
}

let step = myGenerator();

console.log( step.next() ); // => { value: "1: First stab at generators", done: false }
console.log( step.next() ); // => { value: 2, done: false }
console.log( step.next() ); // => { value: "3: Use next() to start iterating", done: false }
console.log( step.next() ); // => { value: 4, done: false }
console.log( step.next() ); // => { value: "5: Normal functions 'run to completion'", done: false }
console.log( step.next() ); // => { value: undefined, done: true }
</code></pre>

Furthering on our example and passing values into next('some value'); This might be a little confusing at first:

<pre><code class="language-javascript">function *personFullName() {
    var fName = yield 'first name';
    var lName = yield 'second name';
    console.log(fName + lName);
}

var myGenerator = personFullName();

myGenerator.next(); //{ value: 'first name', done: 'false' }
myGenerator.next('Sophia '); //{ value: 'second name', done: 'false' }
myGenerator.next('Kahn') // { value:'undefined', done: 'true' }

// => Sophia Kahn
</code></pre>

