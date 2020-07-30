---
layout: post
title: ES6 - Let and Const
description: ES6 brings us two new keywords for variables which provide us a way to define block scoped variables and constants
category: ES6
manualdate: December 28, 2015
---

## Let and Const

`let` and `const` are two new identifiers for storing values in `ES6` which you can additionally use to declare variables
'let' and 'const' throw more exceptions as they behave more strictly than 'var'
* `let` is block scoped and is **hoisted** to the top of it's block, **unlike** `var` which is hoisted to the top of it's **function** or **script**
* `const` is also block scoped and is also **hoisted** to the top of it's block
    * it's worth noting that in ES6 functions are **block scoped** instead of lexically scoped
'var`
* `let` does not create a property on the global object
* `const` creates **immutable** variables, whilst `let` create **mutable** ones
* a duplicate declaration of `let` will throw a **Reference Error** within a block or function
 * this is also known as `TDZ` or temporal dead zone
* _Basic rules to follow_: 
 * don't use `var`, or leave it as a signal in untouched legacy code.
 * use `let` when you want to rebind.
 * prefer `const` for variables that never change.
 * don't blindly refactor legacy code when replacing `var` with `let` and `const`.
 
How `let` works: 
 
<pre><code class="language-javascript">function myfunc() {
   if ( true ) {
     let x = 54321;
   }
   console.log( x ); // => ReferenceError: x is not defined  
 }
</code></pre>

<pre><code class="language-javascript">// legacy ES5
 function myfunc() {
   if ( true ) {
     var x = 54321;
   }
   console.log( x ); // => 54321 
 }
</code></pre>

Using block scoped `let`:

<pre><code class="language-javascript">let outer = "outer";
{
  let inner = "inner";
    { 
      let nested = "nested"
    }
  console.log( inner ); // => you can access `inner`
  console.log( nested ) // => throws error  
} 
// you can access `outer` here
// you cannot access `inner` and `nested` here 
</code></pre>

More scoping rules for variables declared by `let`. you can clearly see that when refactoring:

<pre><code class="language-javascript">function letBlocks {
  let a = 23;
  if ( true ) {
    let a = 56;
    console.log( a ); // => 56
  }  
  console.log( a ); // => 23
}  
</code></pre>

How `const` works. Variables declared with `const` are immutable, but note that the values aren't just the declarations:

<pre><code class="language-javascript">const foo = '123';
foo = '321';
console.log( foo ); // TypeError

// changing const values
const myarr = [1,2,3,4];
myarr.push(5);
console.log( myarr ); // => 1, 2, 3, 4, 5

const obj = {};
obj.prop = 123;
console.log( obj ); // => { Object: prop: 123 }
</code></pre>
