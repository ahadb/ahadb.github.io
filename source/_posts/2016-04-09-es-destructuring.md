---
title: ES6 - Destructuring
description: Just like an object literal is a convenient way to construct an object, ES6 destructing allows you to extract values from data stored in objects or arrays
category: ES6
manualdate: April 09, 2016
---

## Destructuring

Just like an object literal is a convenient way to construct an object, ES6 destructing allows you to extract values from data stored in objects or arrays.
* You can assign to more than just **variables**
* Destructuring can be used in **assignments**, **variable declarations** and **parameters**
* `spread` and `rest` operators work with destructuring
* You can destructure a `for-of` loop

Objects:

<pre><code class="language-javascript">const myObj = { firstname: 'Ahad', lastname: 'Bokhari' };
const { firstName: fname, lastName: lname }; = myObj
console.log( fname, lname ); // => Ahad Bokhari

let a, b;
({ a, b } = {a: 1, b: 2});
console.log(a, b);

// deeper objects
const {
  prop1: z,
  prop2: {
    prop2: {
      nested: [ , , c]
    }
  }
} = { prop1: "Hello", prop2: { prop2: { nested: ["a", "b", "c"] }}};
console.log(z, c);
</code></pre>

Arrays:

<pre><code class="language-javascript">
const myArr = [ 'y', 'z'];
const [ a, b ] = myArr;
console.log( a, b ); // => y, z

let [ a, , b ] = [ 'x', 'y', 'z' ];
console.log( a, b );

// deeper arrays
const [ a, [b, [c, d]]] = [1, [2, [[[3, 4], 5], 6 ]]];
console.log("a:", a, "b:", b, "c:", c, "d:", d); // => a: 1 b: 2 c: [ [ 3, 4 ], 5 ] d: 6
</code></pre>
