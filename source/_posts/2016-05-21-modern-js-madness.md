---
title: Modern JavaScript Madness
description: JavaScript fatigue
wordcount: 850
manualdate: May 22, 2016
category: JavaScript, Other
---

The state of JavaScript development is advancing rapidly, so rapidly that in-fact my people can't help but feel overwhelmed, fatigued and exasperated trying to keep up with the ebb and flow of the churn rate. For those not persistent enough, this can zap your productivity and hinder your progression. Let's try and describe our beloved ecosystem with as slew of familiar words: 

Node, ES6, NPM, React, Angular 2.0, Mocha, Chai, Closures, Prototype, Classes, Require, Bowserify, WebPack, SystemJS, Exports, modules, package managers - the list is long and distinguished. 

_Are you feeling fatigued already?_

## Beginnings of Madness

So what is all this madness and where has it come from you might ask. Part of the answer comes from it's bad design and a fragmented ecosytem. JS is one language that has no native built in support for modules - on a language level there is a distinct problem and it's the fact that you have to know the three, four, five different ways to do something. If you want to author a library, you'd need to let your users consume your code in different environments and you'll always get into a situation where someone or other will complain about the portability of your code. On the bright side however if someone desperately wants your code, they'll find a way to consume it.

On an API level things play much nicer where packages contain small bytes of code and you have reasonable amounts of choice and control whilst developing. NPM has thousands and thousands of modules for us to achieve what is missing in the core of the language - need extensive array or string methods, no problem. Awesome. 

So... We can derive that JavaScript design has some flaws, the ecoysystem is fragmented and there are many ways to do achieve something. If you're working on a team, each member needs to know all of those ways - the more ways to do something, the more likely a team member could get it wrong (not to mention more pointless arguments over syntax, style, et al) 


## Overengineering

Let's talk about overengineering for a moment, a common phenomenon in software development. Creating a web application can also be maddening within the context of the modern workflow - not only can the approach be convoluted and contain steps that can easily be overlooked, your single source of truth might be coming in at over 20K+ lines of code and you only had to install webpack, babelify and react for your simple "Hello World" application ( according to modern day front end dev standards ). I can bet that if you took your little Hello World application and wrote it in plain JavaScript you wouldn't exceed 35 lines of code. 

Here's the rub: the applications that you will be working on throughout your career will most likely fall between 4,000 - 6,000 lines of code. If you've already started with a full React stack, chances are in the real world you have already over-engineered your application. Most of the tools that we use you really don't even need, and if you're not savvy with those tools chances are that they will cause you more problems instead of solving the problems you set out to solve in the first place.

Experience counts and finding the equilibrium to start JavaScript applications by structuring them correctly takes practice - we've all seen the trend to use NPM's package.json ( npm run build ++ minify + concat, npm run test )for dead simple build commands instead of Gulp. Do I need to use Angular or React, should I use npm/require/babelify/webpack/browserify can all be answered if you understand and learn how to structure your application correctly.

## Enter ES6

The whole situation I've describe can be bad enough, but it gets more complicated once you add ES6 to the mix. Till date we have no implementation of modules across evergreen broswers, which should be the "future proof" way of authoring JavaScript. Most folks use Babel in their build or Node which supports 96% of ES6 features - this still doesn't make the transition any easier as you still need to translate between Node and browser code - supporting all this comes with it's own frustrations. Some users know Bower and not NPM and might not even understand the difference between the two.

On the bright side the community has taken up the transition to ES6 and the web is abundant with tutorials, opinions and resources to learn. ES6 featurees will eventually be implemented by a significant enough base for actual use - the question is simplly when that will happen. Edge has already implemented an exprimental flag for modules and common syntax can be found in Firefox and Chrome already (minus modules of course!).

Personally, I feel ES6 brings alot of great new features and minimizes the "so many ways to do one thing" syndrome. Many features will help developers repeat mundane tasks and with time standardize a way to author JavaScript. With the new specification on the horizon, we need to brace ourselves for the future and hope our wonderful little language takes a step towards maturity and standardization.


