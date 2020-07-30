---
title: Classes vs. Prototype
manualdate: March. 24, 2017
description: JavaScript uses prototypes, but new ES6 implementations also uses the traditional class keyword. What's the real difference between the two?
wordcount: Mix { ... } / 336
category: Software, JavaScript
---

In a traditional programming language a class is an entity responsible for creating objects and defining the behavior of objects. Though they might be objects in their own right, they're certainly different from other types of objects. A <code>Class</code> then in the classical sense is an object whose Class is <code>Class</code>. 

A simple demonstration would be as follows:

<pre><code class="language-javascript">function MyClass() {}
typeof MyClass
// => "function"

class SomeClass {}
typeof SomeClass
// => "function"
</code></pre>

In the JavaScript world, we have constructors and prototypes. Thus we can use JavaScript like a classical language, and it has enough expressive power to simulate a classical system. Embracing the prototypal nature of the language objects inherit from other objects.

The <code>new</code> keyword:

<pre><code class="language-javascript">new Foo();
</code></pre>

...creates a new object that inherits from:

<pre><code class="language-javascript">foo.prototype
</code></pre>

We all know that JavaScript instances are created with a constructor and the constructor of an instance is a function that was invoked with the new operator. As a matter of fact any function can be a prototype. There is a stark difference here where a <code>Class</code> is a special type of object that creates new instances.
Classes in traditional languages have special methods attached to them.

In JavaScript we see no such mechanism, there is nothing special about a prototype object, no special class methods or constructors:

<pre><code class="language-javascript">function norf() {}
norf.prototype
// => {}
</code></pre>

## In Short

* “Classes” are objects in most “classical” languages, but they are special in the sense that they have methods associate with them. In JavaScript, prototypes aren't special, they’re just objects (as seen above)
* JavaScript takes the responsibility for instances into separate processes, a constructor and a prototype. A constructor in JavaScript can be any function and are responsible for creating new instances.

So when we say JavaScript has "Classes", we really mean that we have something that works just like a simple class-based system, with the constructor function and its prototype acting as the “Class.”