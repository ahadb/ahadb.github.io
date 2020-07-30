---
title: Angular 2 vs. React
manualdate: Oct. 24, 2016
description: Comparing Angular 2 to the React ecosytem by taking a deeper dive into each technology's advantages & disadvantages. Note, these two hold the most market value; surprisingly jQuery still takes third place in popularity and value
wordcount: 1142 
category: JavaScript, ES6, Software
---

Angular 2.0 recently released it's production ready framework on September 15th, 2016 - it took 2.5 years for the team at Google to reach this milestone and will cause developers to start learning the new framework with emphasis on scalable JavaScript using TypeScript. In Angular 2, components are the main way we build and specify elements and logic on the page as opposed to in Angular 1, where we achieved this through directives, controllers, and scope. 

That being said, React's whole ecosystem is built around modular, composable and reusable components that maintain state while passing data down from the parent to child as props. The React way has been loved by many developers across the world, and there is a vibrant open-source community. React has been the golden child for application development in 2015 when compared to other frameworks.


## Comparing React to Angular

You might wonder that comparning React to Angular 2.0 is like comparing Apples to Oranges as Angular is a full-blown framework and React is just the View in MVVM - a laser focused library if you will. To make it easier, I'll be discussing advantages / disadvantages between the two and concentrating on the component part of the lifecycle - that should drastically draw the lines closer to a better comparison.

## React Advantages

Let's look at the advantages that React has as our first look:

### JavaScript

At the end of the day React is just JavaScript from top to bottom, whatever way you look at it. This is the most important distinction between the two where Angular strives to make HTML more powerful while React relies on plain ole JavaScript. Those who might point fingers at React should likely question their own proficiency as JavaScript developers.

### Functional JavaScript

React will teach you a thing or two about functional JavaScript, pure functions, side effects, etc etc. Overall it will make you a better JavaScript developer and introduces new developers to `map`, `reduce` with plenty of usage of the `this` keyword.

### JSX

JSX is a big win for React and the JavaScript community. JSX is not an HTML template language, nore  simple token replace and `innerHTML = quux` dump like other tools out there.

JSX is a declarative syntax that's used to express the virtual DOM and get interpreted and converted to virtual DOM, which then gets diffed agains the real DOM. React renders fast because you don't rewrite the whole DOM tree, only the differences apply.

Other points about JSX:

* Designers like JSX and design teams adjust quickly since they find it easier to work with
* You get inline styles, style variables, style modules, style inheritance and don't have to learn a whole new syntax. Just do it in JavaScript.
* Keeps markup organized and DRY
* Easy rendering lists with `map`

### Single Responsibility / Unix Philosophy 

React embraces the UNIX philosphy, which means that you choose the libraries that you need to get the job done by having the ability to swap out at your free will.

### Vibrant Tooling, Community & Development Experience

Tooling will never be a problem with React, there are alot of open source projects that will ramp you up in no time. With hot-reload, support for WebPack and a plethora of options developed by passionate community members 

## Angular 2.0 Advantages

Now for Angular 2's advantages:

### Web Component Friendly
Angualar is web componet friendly in terms of native web components - this is a huge strength as the web is evolving towards the latest specifications and will be a big win in the long term as browsers start supporting it.

### TypeScript
Another huge win for Angular 2.0 is TypeScript - a way to write more scalable JavaScript which addresses the core weaknesses of the language itself. The Angular folks primary documentation uses TypeScript syntax (which is JavaScript at the end of the day, it doesn't force new features upon you) and recommend it's use within the lifecycle of your workflow. In turn this will be adopted by folks who develop Angular 2.0 apps and by the community. If you look at React there are multiple ways to create a component and that can lead to confusion for new developers.

There is something awesome about building a typed function interface and knowing that the next dev who comes along will know how to use your code.

### Less JavaScript Fatigue

React' moves a fast rate causing churn within the ecosystem - what you write today may be out of date tomorrow or require changes within the libraries that you have used today. This can be very frustrating and turns out to be the source of confusion and too much work trying to find the right libraries for the job.

Adding to this point, Angular forces more opinions on you which helps you get started much quicker without having to make too many decisions up front.

## Other Points To Consider 

### Performance
Performance is a key metric for many people looking at a tech buy in. Angular 1 had performance issues with dirty checking and digest cycles that were mentioned post after post on the internets. It looks like Angular 2 have cleaned it up, so it compares to React quite well where performance is concerned.

One should also consider team performance as highly as app performance - the team should be able to move fast and make quick changes.

### ng2 Templates / JSX / State

* With ng2 templates you need to learn Angular syntax like *ngIf and *ngFor. React's syntax is much more like plain JavaScript
* If you make a mistake with Angular 2 templates they fail silently, compare this with React that notifies you immediately if there is something wrong with your JSX syntax
* Both Angular 2 and React can use whatever data management layer that you like, and you can bring your own state management to ng2.


## Summary 

I think Angular 2 requires much more tech buy in and alot more boilerplate. However, Angular 2 is a huge improvement over version 1, the new component model is simpler and it uses a virtual DOM offereing. With the use of TypeScript many large corporations that eschew JavaScript's loose typing will gravitate towards it, making it the number 1 choice in the enterprise and a must have in your arsenal of tricks.

If you want something slimmer and prefer smaller modules as well as love a superfluous development experience that hits home to JavaScript then have a close look at React. There are alot of open sourced projects you can learn from.

Keep in mind that there are alot of things in React that you won't find in Angular 2.0 and vice versa. There are also other options out there, but React and Angular dominate usage and you can find value in a large ecosystem and developer community. If you choose one, stick with it and learn it's intricacies from the ground up - and remember never to lose complete sight of the other.
