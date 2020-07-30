---
title: Thoughts on Node
description:  I love working with NPM and tools but I can't help continuously thinking about how we might outgrow Node and NPM and replace it with just vanilla JS 
category: Javascript
manualdate: April 10, 2016
wordcount: 1,009
---

I've been thinking alot about the future of JavaScript lately, and with the upcoming ES6 spec we can look forward to an ample amount of features that will eventually become a standard within browsers - I'm really excited about when we finally have native support and aren't ( for the most part ) just settled on CommonJS for creating modules. Adding a module system into a language isn't that easy but it will happen — till then the JavaScript community have Node and NPM and we will continue to see the all too familiar require, exports and module statements in our Node code.

Node is definitely not the shiny new object anymore, but since JavaScript is gaining alot of momentum as a language these days ( and for the foreseeable future ) this niche technology is here to stay and will evolve with time as developers tend to adopt more isomorphic applications. I feel we still haven't seen the peak of Node JS yet, and with the evolution of client side frameworks, build tools and transpilers like Babel NPM ( Nodes Package Manager ) appears to be getting more and more traffic - it's worth noting NPM has over 250,000 modules and is growing at a phenomenal rate dwarfing package managers from different languages. Having said that, Node is not the silver bullet platform that will dominate, but fills a particular need.

Understanding this is essential, but the intention of this post is not here to talk about how exactly Node works and what apps run best on single threaded, non-blocking I/O supporting tens of thousands of concurrent connections. 

Interestingly many community members have said that Node ( the server side JavaScript ) framework is the _MOTHER_ of server side frameworks - having used Node in my daily workflow for some time now I can still say that's an utterly absurd statement. Ruby on Rails, PHP, .NET and company have been around the block for a while and neither of them boasted sweeping the world by it's feet. Still Node.js is a fair choice and is going through the same life-cycle that all other frameworks have gone through; a small niche technology which with more adoption is slowly becoming a more broadly used niche technology.

Companies like Walmart, Paypal and Google are all working on Node, hiring developers and pushing the boundaries of JavaScript development - who knows maybe they'll have a big impact on the community in the years to come. Yahoo is probably the most aggressive Noder with over 1200 modules both private and public while Netflix & friends have proven that companies are thinking about Node as their goto server environments.

So, __the future of Node__ is still bright and I'd like to see more adoption in business and enterprise in 2016. Node already has given businesses a great amount of leverage, besides just lowering costs. Now business can:

* Retain staff for longer periods with happier developers
* Happy developers push great things and in turn customers are happy
* Reduce the number of servers
* Reduce developers and use 1/2 the number of developers to develop cutting edge products

I mentioned that there is no silver bullet with any framework, and Node isn't an exception. From a personal perspective I don't like Node because of the following:

* Awkward programming styles using callbacks - with ES6 we will see a more fluent way to write Node applications
* Blocking operations are the root of all evil, and 99% of Node misues come as a direct consequence
* Node has baggage:
 * it's tightly tied to V8, a single JS engine and makes it hard to compare engines outside the browser
 * it adds globals to your script: exports, require, module
 * working with relational data is still immature in Node - when comparing Node & Express to Ruby on Rails it's easy to see why you'd choose the latter

Things I simply love about Node which are appealing to me and probably the rest of the community:

* NPM and the ability for developers to micro-control their architecture
 * Express, Connect, Socket.io. Mongo, Underscore, Lodash et al
* Single Responsibilty Principle
* Having JavaScript run on both the server and client side means that developers don't have to learn separate languages for full stack web development
* Silos that exist between backend and frontend developers are now broken down
* Efficiency and developer productivity see an increase, and with that companies can lower costs

To play the devil's advocate I'd like to have a swappable JS engine where the developer can have the benefit of having multiple competing implementations and is able to choose one. However right now Node core is too tighly coupled with V8 and would need a complete overhaul.

It will be interesting for us to see how Node evolves as the standardization of ES6 comes to fruition. Currently, Node supports a number of new language features from the ECMAScript6 specification which gives developers a good look at the future of the language. 

There are certain facts that we should look at historically. Node is only 75% JavaScript, and has C++ and it's predecessor C involved in it's architecture. We all know that it was forked to retain it's vanilla JavaScript state and there have been alot of dog gone politics between developers, the board at Joyent and community. For now and the forseeable future, I love working with NPM and tools but I can't help continuously thinking about how we might outgrow Node and NPM and replace it with just vanilla JS.



  
  
