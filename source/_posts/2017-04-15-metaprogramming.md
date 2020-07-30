---
title: Metaprogramming in JavaScript
manualdate: April 15, 2017
description: ES6 comes with a set of features that aid in metaprogramming, but not much has been written about them. I'd like to briefly touch base on reflection and introspection whilst opening doors for further posts detailing ES6 Proxy, Symbol and Reflect.
wordcount: 422 
category: Software, JavaScript, ES6
---

## Discovering Metaprogramming

You probably use meta programming everyday without even realizing it, so let's take a brief few moments to discover the basic concepts behind the world of metaprogramming. Metaprogramming is is all about what's under the hood, as opposed to the higher levels of programming like business logic or data modelling. Metaprogramming can be described as "making programs making programs" or something similar. 

Imagine a guy who builds cars. Say it's the same thing as using a computer. At some point he realizes he's always doing the same thing, more or less. So he builds factories to build cars, and it's much better. He's now programming! Nevertheless, once again, at some point, he realizes he's always doing the same thing, to some extent. Now he decides to build factories that build factories that build cars. 

That's metaprogramming.

## Metaprogramming in JavaScript / ES6

One feature of metaprogramming is code generation, like for example <code>eval</code> (JavaScript has had <code>eval</code> since ES1) - it's worth noting that most programming languages have code generation features. Another feature of metaprogramming is Reflection - finding out about and adjusting the structure and semantics of your application. JavaScript has some tools for Reflection....

Functions have:

* Function#name
* Function#length
* Function#bind
* Function#call 
* Function#apply 

Also, all of the available methods on Object are Reflection, <code>Object.getOwnProperties</code>. Let me remind you that Reflection tools that don’t alter code, but instead gather information are often called Introspection). Also we have Reflection/Introspection operators, like <code>typeof</code>, <code>instanceof<code>, and <code>delete</code>.

So without further ado, the new APIs in ES6 come in three: <code>Symbol</code>, <code>Reflect</code>, and <code>Proxy</code>. Symbols are all about Reflection within implementation - you dabble them on your existing classes and objects to change the behavior. Reflect is all about Reflection through introspection which is used to discover very low level information about your code. Proxy is all about Reflection through intercession and wrapping objects & intercepting their behaviours through traps.

Quite obviously we have just touched the surface of metaprogramming in JavaScript, but the above information will be useful to you. In the next couple of posts I'd like to talk about Symbols, Reflection and Proxy in more detail with syntactical examples.