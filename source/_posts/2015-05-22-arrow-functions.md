---
layout: post
title: ES6 - Arrow Functions
description: Arrow functions are always anonymous functions and have a shorter syntax then their ES5 counterpart
manualdate: May 22, 2015
category: ES6
---

Arrow functions are one of the more popular features of `ES6` saving developer time and simplifying function scope. 
* The arrow `(=>)` or `fat arrow` provides a shorthand for the function keyword with lexical `this` binding
 * Arrow functions change the way `this` binds in functions
 * They work much like `lambdas` in languages like `C#` or `Python`
   * `lambda` expressions are are often passed as arguments to **higher order functions**
 * we avoid the `function` keyword, `return` keyword and `curly brackets` when using arrow functions
* Arrow functions allow developers to remove boilerplate, however you shouldn't remain ignorant of how 'lexical` scoping `this` works 
* Be careful when using `arrow functions` as they aren't applicable everywhere, **use cases** will depend from situation to situation

For the sake of simplicity, we could do the following:

<pre><code class="language-javascript">const msg = () => alert("Hello Arrow Function");
console.log(msg());
</code></pre>

<pre><code class="language-javascript">let square = ( a, b ) => a * b; 
console.log(square(5, 5)); // 25
</code></pre>

<pre><code class="language-javascript">
let x = [0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10];
let z = x.map(x => x); 
console.log(z); // [ 1, 2, 3, 4, 5, 6, 7, 8, 9, 10 ]
</code></pre>

Every new function defines it's own `this` value, yet `arrow` functions **close** over the `this` value

<pre><code class="language-javascript">// in ES5
function Tree() {
  that = this;
  that.age = 0;
  
  setInterval(function growOld() {
    that.age++;
  }, 1000);  
}

var t = new Tree();

// in ES6
function Tree() {
  this.age = 0;
  
  setInterval(() => {
    this.age++;
     5000);
  }
}
     
var t = new Tree();
</code></pre>