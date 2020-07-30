---
title: ES6 - String & Template Literals
description: A personal favorite, template strings are a nifty addition in ES6 to the string object
manualdate: January 02, 2016
category: ES6
---

We all know that JavaScript `strings` are limited and lacking in capabality, especially if you're coming from **Ruby** or **Python**. Template literals are a feature that developers will love and are basically just `string literals` allowing `embedded expressions`.
* `ES6` introduces `string interpolation`, `string formatting`, `multiline strings` and `embedded expressions` with template literals
* Template strings use (``) rather than single or double quotes used with regular strings
* Placeholders using the `${ }` syntax are used from string substition and works fine with any kind of **expression**
 * expressions in between the placeholders (${expression}) and text b/w them get passed to a function
  
Familiarizing yourself with the `syntax`:

<pre><code class="language-javascript">const a = `this is a template literal`;
console.log( typeof a ); // => string

const b = `You can use template literals in multiline
statements without using \\n`;
console.log( b ); // => yup, it works!

const c = `Some string text ${expression}`;
</code></pre>

Use the following syntax to `embed` expressions within template literals

<pre><code class="language-javascript">const a = 100,
      b = 100;
console.log(`The sum of ${a} * ${b} is ${a * b}`); 
// => The sum of 100 * 100 is 1000

const user = { name: `Ahad Bokhari` };
console.log(`You are now logged in, ${ user.name.toUpperCase() }. `);
// => You are now logged in AHAD BOKHARI
</code></pre>