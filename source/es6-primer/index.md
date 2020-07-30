---
title: ES6 Primer
manualdate: March 31, 2016
---

An introdcutory repo to ramp you up quickly with `ES6` features, tools and syntax - there's even a short section on `ES7`. Read the **contributions** section and check back from time to time for intermittent updates.

## Table of Contents
* [ECMA Brief History](#history)
* [Introduction](#es6-introduction)
* [Tools](#tools)
* [Block Scoping](#block-scoping)
* [Let and Const](#let-and-const)
* [Destructuring](#destructuring)
* [String & Template Literals](#string-and-template-literals)
* [Math & Number](#numbers-and-strings)
* [Arrays](#arrays)
* [Parameters](#parameters)
* [Modules](#modules)
* [Getters & Setters](#getters-and-setters)
* [Classes](#classes)
* [Symbols](#symbols)
* [Generators](#generators)
* [Arrow Functions](#arrow-functions)
* [Map & WeakMap](#map-and-weakmap)
* [Set & WeakSet](#set-and-weakset)
* [Promises](#promises)
* [Contributions](#contributions)
* [ES7 - ES2016](#es7) :star:

## History
* ECMAScript is now 17 years old with it's birth in 1997 
  * ECMAScript is the standard. `JavaScript`, `ActionScript` and `JScript` are implementations of it
  * JavaScript popularized two paradigms on the web, `functional programming` and `prototypal inheritance` (objects without classes)
  * `JavaScript` first appeared in Navigator 2.0 browser and has appeared in all subsequent browsers from Netscape and in all browsers from Microsoft starting with Internet Explorer 3.0
  * JavaScript was designed with C-like syntax with curly braces, the statement/expression dichotmory, dot notation etc
  * ECMAScript is designed by [TC39](http://www.ecma-international.org/memento/TC39.htm) and operates on consensus

_A brief snapshot of it's history:_

| Edition  | Year          | Notes                                                                                    |
| -------- |:-------------:|------------------------------------------------------------------------------------------|
| 1        | 1997          |      Oracle (prev. Sun) had trademark to Java, therefore JavaScript                      |
| 2        | 1998          |      ECMA International creates the ECMA-262 standard                                    |
| 3        | 1999          |      Introduced many features inherint in the language today                             |
| *3.1     | 2008          |      Eventually standardized as the 5th of ECMA-262, also described as ECMAScript 5      |
| *4       | abandoned     |      Abandoned due to political reasons                                                  |
| 5        | 2009          |      Added 'use strict' ( aligns with 3+ )                                               |
| 5.1      | 2011          |      Maintenance revision (alings with 3+ )                                              |
| 6        | 2015          |      Significant features added, that's why you're here                                  |
| 6        | unreleased    |      Early stages of development                                                         |

&#8593; [Back to TOC](#table-of-contents)

## ES6 Introduction
`ES6` is the newest addition to the language and adds **significant** new syntax for writing complex JavaScript applications.
 * There is 5 years between `ES5` and `ES6`.  
 * 'ES6' is the first **ECMAScript Harmony** specification and is also known as `ES Harmony`, `ES2015`, `ES.next` but commonly referred to as `ES6`.
* The specification was finalized in `June 2015`as it reached `feature complete` status
  * Subsequent versions will be released on a 12 month cadence, and will be dubbed `ES7`, `ES2016` respectively.

[&#8593; Back to TOC](#table-of-contents)  

## Tools
You should want to experiment and play around with code — it's easy to get up and running. There are several techniques and the premise all these tools are built upon is called `transpiling`, or **JavaScript to JavaScript** transpiling which compiles the latest version into older versions.
* Transpilation is the future for future ECMAScript such as `ES2015` and `ES2016`
* The most popular JavaScript transpilers are `Babel` and was previously known as `6to5` and `traceur`
* Transpilation is possible to incorporate into your build process using [Broccoli](), [Gulp](), [Browserify](), [RequireJS](), [Webpack]() et al and friends.

_The easiest way to get up and running in the `web browser`:_

* In the web browser you can use the online `Babel REPL` — this compiles `ES6` to `ES5` and you don't have to install anything.
* Another web based tool is `Scratch JS` and comes in the form of a chrome extension. This interactive playground let's you transpile your code in the all familiar `dev tools` environment.

_If you prefer the `command line`:_

* Use Node,js v4.x.x or `>`, they support is in-built for Babel
* Run `npm install -g babel' and `babel node`

_Using an `IDE`:_

* You can easily use `Babel` to transpile your code in **Webstorm**, the setup won't take more than a couple of moments.

_Node has decent built in support for `ES6` thanks for the `V8` engine:_

* Node suports `ES6` features split into three groups
 * Shipping: which do not require a **runtime flag**
 * Staged: almost-complete features that are not considered stable
 * In progress: features can be individually activated by their respective harmony flag `--harmony_destrucuting`

&#8593; [Back to TOC](#table-of-contents)
 
## Block Scoping
ES6 introduces block scoping:
* anything between `{` ... `}` introduces it's own scope
* this works like an `IIFE`
* functions are **block scoped** in ES6 
 * this is more mainstream than **function scoping** which makes it easier when coming from or moving to other languages  

<pre><code class="language-javascript">{
    let quux = "Hello World from ES6";
    console.log(quux); // => Hello World from ES6
}

{
    let foo = "This has a different scope";
    console.log(foo); // => This has a different scope
}

console.log(quux); // Reference Error: quux is not defined
</code></pre>

> In ES5 you would use the `function` as the **fundamental construct** for all your variable scoping.

<pre><code class="language-javascript">var x = 7;

(function iife() {
  var x = 10;
  console.log( x ); // => 10;
})();

console.log( x ); // 7  
</code></pre>

&#8593; [Back to TOC](#table-of-contents)
    
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

&#8593; [Back to TOC](#table-of-contents)

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

<pre><code class="language-javascript">const myArr = [ 'y', 'z'];
const [ a, b ] = myArr;
console.log( a, b ); // => y, z

let [ a, , b ] = [ 'x', 'y', 'z' ];
console.log( a, b );

// deeper arrays
const [ a, [b, [c, d]]] = [1, [2, [[[3, 4], 5], 6 ]]];
console.log("a:", a, "b:", b, "c:", c, "d:", d); // => a: 1 b: 2 c: [ [ 3, 4 ], 5 ] d: 6
</code></pre>

&#8593; [Back to TOC](#table-of-contents)

## String and Template Literals
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

&#8593; [Back to TOC](#table-of-contents)

## Math and Number 

* Additions to `integer literals` have been added included `octal` and `binary` literals
* Methods that have been added to `Number` apart from the usual four suspects are, `Number.EPSILON`, `Number.isInteger`, `Number.isNaN`, `Number.isFinite`, `number.isSafeInteger`
* `Number.MAX_SAFE_INTEGER`, `Number.MIN_SAFE_INTEGER` are the largest and smalled integer that are represented in JavaScript
* The math object has also received some useful methods in `ES6`, `Math.sign`, `Math.trunc`, `Math.cbrt`

&#8593; [Back to TOC](#table-of-contents)

## Arrays

`ES6` brings an abundance of new Array methods

* Array: `from`, `of`
* Array.prototype: `findIndex()`, `fill()`, `find()`, `copyWithin()`, `keys()`, `values()`, `entries()`

Using `Array.from` we create a new array instance from an `array-like` or `iterable object` 

<pre><code class="language-javascript">var doc = document.querySelectorAll('*');
Array.from(doc).forEach(function(nodes) {
  console.log(nodes);
});
</code></pre>

Using `Array.of` we create an array of variable arguments passed to the function

<pre><code class="language-javascript">var arr = Array.of(true, null, undefined, `some message`, 50);
console.log( arr ); //[ true, null, undefined, "some message", 50]
</code></pre>

Examples of additional `array` methods:

<pre><code class="language-javascript">// copyWithin()
[1, 2, 3, 4, 5].copyWithin(0, 3); // => [4, 5, 3, 4, 5]

let letters = ["A", "B", "C", "D", "E", "F", "G", "H", "I", "J"];
letters.copyWithin(4, 0); // => there is an optional parameter copyWithin(4, 0, 2)
console.log(letters); // ["A", "B", "C", "D", "A", "B", "C", "D", "E", "F"]

// find()
let cities = ["Beirut", "Karachi", "Islamabad", "Athens", "Kabul", "Tapei", "Bucharest"];

let t = cities.find(char => char.endsWith("t"));
console.log( t ); 

// keys()
let people = ["Ahad", "Moe", "Zoey", "Snaey"];

for( let entry of fruits.entries() ) {
  console.log(entry[0]);
  // 0
  // 1
  // 2
  // 3
  
  console.log(entry[1]);
  // Ahad
  // Moe
  // Zoey
  // Snaey
}
</code></pre>

&#8593; [Back to TOC](#table-of-contents)

## Parameters

In ES6 we have a standardized and more laconic way to handle parameters ( /i.e: defaults, parameters and arguments ) which greatly reduces boilerplate code.

In `ES5` you could do something like this to handle `default parameters`:

<pre><code class="language-javascript">function multiply(x, y) {
    y = y || 10; // Default to 1
    return x * y;
}
</code></pre>

It's counterpart in 'ES6':

<pre><code class="language-javascript">function multiply(x, y = 10) {
  return x*y;
}

multiply(10); // => 100
</code></pre>

The `rest` parameter has been added into the spec, which also reduces the boilerplate code for handling arguments:

<pre><code class="language-javascript">function f(...theArgs) {
  console.log(theArgs.length);
}

f1();  // => 0
f1(5); // => 1
f1(5, 6, 7); // => 3
</code></pre>
> note: the arguments object is not a real array - rest params are instances of `Array` so you can call methods like **map**, **forEach** directly

Another example of using `rest`, note how we collected arguments into a real array and not an arguments object:

<pre><code class="language-javascript">function logEach(...stuff) {
    stuff.forEach(function (stuff) {
        console.log(stuff);
    });
}
logEach("a", "b", "c");
</code></pre>

The `...` construct in `ES6` is also used to provide “spread” for both function calls and array literals:

<pre><code class="language-javascript">// => in `ES5' we'd do this
function fnes5(a, b, c) {
    console.log(a, b, c); // 1, 2, 3
}
var args = [1, 2, 3];
fnes5.apply(null, args);

// in `ES6` we avoid the use of `apply`
function fnes6(a, b, c) {
    console.log(a, b, c); // 1, 2, 3
}
var args = [1, 2, 3];
fnes6(...args); // => 1, 2, 3
</code></pre>

## Modules

At the core of modularity developers need a module system — a way to spread their work across numerous files and directories with access to each other. Without support for modules natively in ECMAScript there has been a community created effort to implement work-arounds — CommonJS and AMD being the most prevelant as
they both have communities that rally around them, but are incompatible with each other. The good news is ES6, ( TC39 group ) has finalized a module syntax which developers can greatly benefit from using the best from both worlds.
* The goal of modules in `ES6` is to keep **both** `CommonJS` and `AMD` user happy with a single format and borrows the best from both worlds
 * `ES6` modules will have a compact syntax with a preference for a single exports ( such as CommonJS )
 * direct support for asynchronous and configurable module loading is supported
* There are two types of exports, `named` exports and `default` exports
 * **named exports** can be used to export multiple things using the keyword `export`
 * **default exports** used to export a default single value
* To import functions, objects and primitives that have been exported from an external module use the `import` statement
 * you may `import` an entire modules contents, a single member or multiple members in a module

A convenient way to specify `named` exports as below:
 
<pre><code class="language-javascript">// lib.js
// -------
export const quux = Math.sqrt( 2 ); // => exports a constant
export function multiply( x, y ) {
  return x * y;
} // => exports a function

export function addContact( id, callback ) {
  callback();
} // => exports a function

export function refreshContact() {
  alert( `Hello ES6 Modules` );
} // => exports a function
</code></pre>
> And of course `import` them into another file:

<pre><code class="language-javascript">// main.js
// -------
import quux from 'lib';
import { multiply, addContact, refreshContact } from 'lib';

console.log( quux ); // => 1.4142135623730951
console.log( multiply(10, 10); // => 1000
console.log(addContact(1, refreshContact)); // => alerts `Hello ES6 Modules`
// app.js
// ------
// import the whole module
import * as lib from 'lib'

console.log(lib.quux); // => 1.4142135623730951
console.log(lib.refreshContact()); // => alerts `Hello ES6 Modules`
</code></pre>

Another technique in a module, we could use the following:

<pre><code class="language-javascript">const quatro = 10 * 10 * 10 * 10;
export { quatro }; 
</code></pre>

> `default` exports is simple one module that you want to export as the default ( like CommonJS ) and it turns out you can use `default` exports and `named` exports both in your module. There is alot more on `modules` in `ES6` including `script` tags, using `promises` and `module loading` which is an API that allows you to programmatically work with modules and configure module loading. 

&#8593; [Back to TOC](#table-of-contents)

## Getters and Setters

Getters and setters allow you to use standard property access notation for reads and writes. In `ES6` there is a much cleaner way than using `Object.defineProperty` to do achieve this.
* `Getting` and `Setting` helps you organize functionality associated with direct access
  
<pre><code class="language-javascript">class Employee {
 
    constructor(name) {
        this._name = name;
    }
 
    get name() {
        return `Employees name is: ` + this._name.toUpperCase();
    }
 
    set name(newName){
        if(newName){ 
            this._name = newName;
        }
    }
}
 
let developer = new Employee("Sophia");
console.log(developer.name); // => Sophia
developer.name = "Dania";
console.log(developer.name); // => Dania
</code></pre>

## Classes

Classes are a welcome addition in `ES6` however do not introduce a new OO model and rather are just `syntactical sugar` over JavaScript's existing prototype-based-inheritance model.
* To declare a **class** simply use the `class` keyword
 * There are two ways to define a class by using either `class declarations` or `class expressions`
 * `class declarations` are not hoisted
 * `class expressions` can be **named** or **unnamed**
* The `constructor` creates and initializes an object created with a `class` and their `bodies` are executed in **strict mode**
* The `extends` keyword is used to create a `class` that is a child of another class
* The `static` keyword is used to define a **static** method of a `class`

<pre><code class="language-javascript">class Atom {
  constructor( name, mass, neutrons ) {
    this._name = name;
    this._mass = mass;
    this._neutrons = neutrons;
  }
  // using get 	
  get name() {
    return this._name;
  }
  
  get mass() {
    return this._mass;
  }

  get neutrons() {
    return this._neutrons;
  }

  toString() {
    return `${this.name}'s mass index is ${this.mass}, and is composed of ${this.neutrons} neutrons` ;
  }
}

const particle = new Atom('Mote', 100000, 1000);

console.log(particle.mass); 
console.log(particle.neutrons);
console.log(particle.toString());
</code></pre>

There can only be one special method with the name`constructor` however you can have many `prototype` methods in your class 

<pre><code class="language-javascript">class Atom {
  constructor( mass, neutrons) {
    this.mass = mass;
    this.neutrons = neutrons;
  }
  
  // prototype method
  get printMass() {
    return this.calcMass();
  }

  calcMass() {
     return `Atom's mass is ${this.mass}`;
    
  }
  
  // prototype method
  get printSize() {
    return this.calcSize();
  }
  
  calcSize() {
    return `Atom's size is ${this.mass * this.neutrons}`;
  }
}

const square = new Atom(1000, 10);
console.log(square.printMass);
console.log(square.printSize);
</code></pre>

## Symbols

We now have a public interface to use symbols in `ES6`. A symbol is a unique and immutable `primitive data type`.
* Their main purpose is `interoperability` and to avoid name clashes between properties - you can use symbols as identifiers when adding props to an object
* Don't use the `new` operator when creating a symbol, just invoke the function
* Symbols are **unique**, you cannot alter them ( which is the whole point )
* Interestingly symbols used as `keys` to an object will not appear as part of the object when using a `for in` loop

Syntax for creating a symbol, `Symbol` or Symbol( description )`:

<pre><code class="language-javascript">let sym1 = new Symbol(); // => throws an error

let sym2 = Symbol( "symbol description" ); // => you can add a optional description
let sym3 = Symbol( "symbol description" ); // => both `sym1` and `sym2` are unique
</code></pre>

> Using symbols as keys into an object, when you iterate with `for in` your symbol identifier will be hidden:

<pre><code class="language-javascript">const phoneNo = Symbol();

const employee = {
  firstName: "Moe",
  lastName: "Khan",
  [ phoneNo ]: 555-555-5555
}  

for (const key in employee) {
  if (employee.hasOwnProperty(key)) {
    alert(key + " -> " + employee[key]);
  } // => key -> firstName: Moe, key -> lastName: Khan
}
</code></pre>

Symbols can be useful for hiding information in an object, and there is a new **object method** named `getOwnPropertySymbols` that will help you reflect into symbol props:

<pre><code class="language-javascript">const phoneNo = Symbol();
let symbol0 = Object.getOwnPropertySymbols(employee);

const employee = {
  firstName: "Moe",
  lastName: "Khan",
  [ phoneNo ]: 5555555555
}  

for (const key in employee) {
  if (employee.hasOwnProperty(key)) {
    alert(key + " -> " + employee[key]);
  }
  if (symbol0) {
    alert("Hidden symbol " + " -> " + employee[ phoneNo ]);
  }
} 
</code></pre>

## Generators

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
myGenerator.next('Maya '); //{ value: 'second name', done: 'false' }
myGenerator.next('Bethea') // { value:'undefined', done: 'true' }

// => Maya Bethea
</code></pre>

## Arrow Functions

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

<pre><code class="language-javascript">let x = [0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10];
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

&#8593; [Back to TOC](#table-of-contents)

## Map and WeakMap

With the addition of new data structures that are new to `ES6`, `Map` has been sorely awaited by developers to map values to values - `Objects` have been used as `maps` historically
* The `Map` object is a simple key/value map and is deemed an `iterable`
* `for...of` loop returns an array of [key, value] for each **iteration**
* While similar, there are certain distinctions between **Objects** and **Maps** and therefore are certain use-cases
 * Most importantly `Map` instances are **only** useful for collections and `Objects` used as records with fields and methods
 
At a fundamental level when working with maps you could do the following:

<pre><code class="language-javascript">let map = new Map();    
map.set( 'min', Number.MIN_SAFE_INTEGER );
map.set( 'max', Number.MAX_SAFE_INTEGER );
map.has('baz'); // => false
map.size; 2
console.log( map ); // => Map { "min" => -9007199254740991, "max" => 9007199254740991 }
map.delete( 'max' );
console.log( map ); // => Map { "min" => -9007199254740991 }
map.clear()
map.size; // => 0
</code></pre>

Another way to set a `map` via **iterable** `key-value "pairs". Notice that you can any value as the key:

<pre><code class="language-javascript"> let hash = new Map([
        [ 'age', 1 ],
        [ false, 'true' ],
        [ function () {}, 'function' ],
        [ {}, 'object' ], 
        [ 5, 'five' ],
        [ undefined, 'undefined'],
        [ null, 'null'],
  			[ Symbol(), 'Symbol']
    ]);

for ( let key of hash.keys()) {
  console.log( typeof key ); 
} // => string, boolean, function, object, number, undefined, object, symbol
</code></pre>

> Note: The `for...of` statement creates a loop iterating only over `iterable objects' (Array, Map, Set, String, etc). You can also use the built in `forEach` to iterate over map collection

## Set and WeakSet

...

## Promises

Promise objects help us with asynchronous programming, espercially deferring async operations. Think of functions that return their results asychronously ( heard of callback hell? ).
* ES6 has adopted `[PromiseA+](https://promisesaplus.com/)` spec, but there are other libraries out there as such as RSVP, Bluebird, Q
* This allows you to create handlers to asynchronous actions's eventual success or failure in a synchronous way
* So, promises have a sense of `state` which is either fullfilled, pending, or rejected

An example of **callback hell**, also known as the **pyramid of doom**

<pre><code class="language-javascript">asyncFn1(function(err, result) {  
  asyncFn2(function(err, result) {
    asyncFn3(function(err, result) {
      asyncFn4(function(err, result) {
       asyncFn5(function(err, result) {
         // Do something
       });
      });
    });
  });
});
</code></pre>

`Promises` help flatten our structures, a most welcome **struct**:

<pre><code class="language-javascript">asyncFn1(value1)
.then(asyncFn2)
.then(asyncFn3)
.then(asyncFn4)
.then(asycnFn5, value5 => {
    // Do something with value5
})
.catch(function (error) {
    // Handle any error from all above steps
})
.done();
</code></pre>

An example of what a native `promise` looks like:

<pre><code class="language-javascript">var p = new Promise(function(resolve, reject) {  
   if (/* condition */) {
      resolve(/* value */);  // fulfilled successfully
   }
   else {
      reject(/* reason */);  // error, rejected
   }
});
</code></pre>

## ES7

Proposals for the ES2017, ES7 specification can be found here:  [https://github.com/tc39/ecma262](https://github.com/tc39/ecma262) - definitely check the spec when in doubt.

Some of the features might include:

* `Array.prototype.includes`
 * myArr.includes(value) // nice! 
* `Async` and `Generator` functions
* Exponential Operators

## Contributions

Contributions in the form of code samples and syntax are welcome - if you spot errors in example code or feel you have a better use case for a given feature issue a pull request. Typos and formatting requests will also be considered.

