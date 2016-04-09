---
layout: post
title: JavaScript Micro Frameworks, Hypermodularization & Libraries
description: Lately a trend in the JavaScript world has been moving away from JavaScript libraries and popular frameworks like jQuery to using independent libraries  for parts of your project.
manualdate: September 29, 2014
---
Lately a trend in the JavaScript world has been moving away from JavaScript libraries and popular frameworks like jQuery to using independent libraries  for parts of your project. I'm not here to answer your questions whether jQuery has become a crutch in our projects or should we use plain JavaScript for DOM related tasks et cetera, thus refactoring our code to native browser extensions and API's. Let's just take a moment to revisit some of the libraries that we might have forgotten and can use in our projects that have a smaller footprint.

You could consider some of the libraries I mention here as alternate libraries to jQuery and for the most part they are fully capabable of achieving most of what you already want, i.e.: selecting and traversing the DOM, events, Ajax, animations and plugin development.

The concept has been around for a while now, so let's consider some of the basic pros and cons (although there are many more debatable points):

##Pros

* Micro-frameworks encourage building smaller components that are tight and loosely coupled and can be assembled by the developer.
* You can avoid spaghetti code or huge chinds of code in the framework with solutions to problems that we aren't going to utilize.
* Using jQuery for example would have the developer to require the whole library including parts that they wouldn't use resulting in higher file size with modular solutions that one doesn't need. Many situations require the developer to only use part of the framework such as animations or Ajax.

##Cons

* Cross browser compatibility goes first on this list when comparing larger libraries that support the many quirks of different browsers. You or your team might end of debugging or patching your code often.
* In terms of scalability your application and therefore your codebase might grow and in turn the weight of your libraries in micro framework might extend that of a full blow framework.
* Lack of proper documentation and a community coupled with a one man team for the most part can hinder your progress in the learning phase or dealing with common bug fixes.

##Zepto

Zepto matches it's jQuery counterpart and the goal here is to have a small modular library that downloads and executes fairly fast with a flexible and versatile API. It's lean, a third of the size of jQuery and loads much faster.

 As usual the Zepto collection is an array-like object that has chainable methods for manipulating the DOM nodes it references. The following should look familiar:

 {% codeblock javascript %}
 $('div')  //=> all DIV elements on the page
 $('#foo') //=> element with ID "foo"

 // create element:
 $("<p>Hello</p>") //=> the new P element
 // create element with attributes:
 $("<p />", { text:"Hello", id:"greeting", css:{color:'darkblue'} })
 //=> <p id=greeting style="color:darkblue">Hello</p>

 // execute callback when the page is ready:
 Zepto(function($){
   alert('Ready to Zepto!')
 })

 {% endcodeblock %}

 Zepto is good for browser extensions and to develop HTML-based views within native app frameworks, such as PhoneGap. Note that it doesn't support old Internet Explorer versions < 10.

##Vanilla JS

If you're not using jQuery Vanilla JS is a great alternative with fewer requests and better performance. If you're building a small to medium sized application this could be a logical choice for you. Note that if you're reliant on element selectors this would be a good option, whereas jQuery is great for heavy animations. Vanilla JS is really fast, for example retrieving DOM elements when comparing with jQuery makes it worth competitor:

 {% codeblock javascript %}

 document.getElementById('test-table');         // vanilla js in 12,137211 ops / sec

 {% endcodeblock %}

  {% codeblock javascript %}

  $('#test-table');                             // jQuery in 350, 557 ops / sec

  {% endcodeblock %}

##Micro Libraries

The choice is yours so you'd want to do what's right for your team and the scalability of your application. You could progressively enhance your application depending on what side of the debate you stand :) Apart from micro-frameworks there are also a number of micro libraries that you can drop into your project using the tools of your choice.

* [Microjs](http://microjs.com/#)
* [JavaScriptOO](http://www.javascriptoo.com/)

By no means is this a comprehensive reference to how to choose a library or framework but a simple reminder that the language of the web we all love can have different implementations which will change as it evolves.
