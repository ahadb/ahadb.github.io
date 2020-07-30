---
title: Thoughts on TypeScript
manualdate: Oct. 02, 2016
description: I was surprised to see myself like alot of what TypeScript has to offer, but pondered over the disruption it could cause to vanilla ECMAScript driven JavaScript if communities chose to adopt and embrace it
wordcount: 
category: JavaScript, ES6, Software
---

Over the weekend, I was compelled to take a closer look at [TypeScript](https://www.typescriptlang.org/index.html) and immersed myself into the documentation and examples of TypeScript usage.To my surprisethere were many parts that I liked, and of course some that I severely disliked. 

## JavaScript That Scales

It's been four years since [TypeScript](https://www.typescriptlang.org/index.html) has been around to use in modern day JavaScript applications. Deemed the new compile-to-JavaScript language for application scale JavaScript, TypeScript (a superset of JavaScript) was born to solve the problem of getting JavaScript to scale. During the past four to six years we've seen exposive growth in JavaScript usage as the standards web has become significantly more compelling to provide rich user experiences. We've all seen the community overcome issues in JavaScript development by using tools for linting, builds, code checking and adopting best practices like module patterns to achieve modular and scalable encapsulation. At it's core native JavaScript still hasn't been able to scale well, but we have hope with modules and classes in the new specification ES2015.

## A Precursor

JavaScript has some warts, and pain points - we've all seen these in our daily workflows and found workarounds from the community, thank goodness for the community around which churns out so much to improve the fundamental flaws of JavaScript. That being said, currently there are many more good JavaScript developers than there were five years ago, but the demand still outweighs the supply for proficient JavaScript developers in todays modern ecosytem.

Proficient JavaScript developers are high in demand and can ask for the salaries they want - that's a really great thing. On the flip side however, when thinking of improving the web we need a universal way of learning JavaScript so that developers entering the market also have the opportunity to contribute and push good code to the world wide web while developing standardized habits that are considered applicable in real world scenarios.

Every language has it's shortcomings, and parts that are truly remarkable. JavaScript is definitely no different, some would argue worse even. Personally I would like to see companies and development teams / shops who spend energy, time, resources and lot's of money to improve JavaScript, actually improve JavaScript instead of providing alternatives to not write JavaScript. What this does is split up communities that are really just writing JavaScript across different projects.

_[cough]_ **ANGULAR 2** _[cough...]_

## Enter TypeScript

I'm not going to give you a complete synopsis on TypeScript, you can read the documentation yourself. TypeScript does at its core start out with plain JavaScript and adds additional features that blend with the syntax remarkably well. Basic features like variable annotation, function aruguments and variable declarations can be clearly seen. These are the building blocks of TypeScript.

<pre><code class="language-javascript">// code from TypeScript tutorial:
// https://www.typescriptlang.org/docs/tutorial.html

function greeter(person: string) {
    return "Hello, " + person;
}

var user = [0, 1, 2];

document.body.innerHTML = greeter(user); 

// ==>  greeter.ts(7,26): Supplied parameters do not match any signature of call target
</code></pre>

TypeScript also has support for ES2015 classes and modules, obviating from the main point of using it which is to give some semblance of static typing to JavaScript:

<pre><code class="language-javascript">class Student {
    fullName: string;
    constructor(public firstName, public middleInitial, public lastName) {
        this.fullName = firstName + " " + middleInitial + " " + lastName;
    }
}

interface Person {
    firstName: string;
    lastName: string;
}

function greeter(person : Person) {
    return "Hello, " + person.firstName + " " + person.lastName;
}

var user = new Student("Jane", "M.", "User");

document.body.innerHTML = greeter(user);
</code></pre>

Above and beyond additional classes, TypeScript also supports everything else in ES2015 such as: 

* Template Strings
* let, const
* Spread Operator
* Async Await / Promise
* Arrow Functions

...the list is long and distinguished, you can check it all out for yourself if you're curious.

Prefering the bullet list style that we all love, I'd like to sum up my likes and dislikes:

## Likes 

Mostly at a language level as opposed to syntactical sugar.

* Does not coerce you into using it's new features, is largely unopinionated unlike [CoffeeScript](http://coffeescript.org/). Use the features you like
* The ability to add features which is why we have a new tool chain, a new language and the freedom to innovate (syntatically)
* $MSFT has open sourced TypeScript which shows their commitment to the community, at least initially.
* The fact that you can write JavaScript in TypeScript is my biggest like, of course! $MSFT hasn't tried to mutate the language and i applaud them for that.
* Type checking isn't outputted in JavaScript code, phew - when the code compiles into plain ole JavaScript it remains familiar
* npm install -g typescript // enough said
* Support for JSX and React

...and of course, for the OOP crowd out there, the ability to write classical OOP in the way that's familiar to them.

## Dislikes

* My biggest dislike is the ambuguity of how the language will evolve - will it remain withing the realm of ES2015 by aliging itself with future features, or will it digress and create a fork (like Node did) and end up with odds with ECMAScript.
* By creating a community behind TypeScript and succeeding the community might feel like moving away from ECMAScript which creates an even more splintered ecosystem. This really gets me because Microsoft has some pretty powerful friends that are using the language.

Remember [CoffeeScript](http://coffeescript.org/) was driven by the community, not by huge companies that you might be working for.

## Conculsion

Personally I would use TypeScript for Angular 2.0, or even perhaps if I'm planning on writing a large application that needs to scale efficiently within a team of classical OOP folks coming to JavaScript. I've also been pondering over well dropping it into my existing libraries/modules and creating a .ts version, but this would solely depend on the context of my users. These are all possibilities I have considered, and I feel I could use this superset on a frequent basis.

That said, TypeScript has some undisputed strengths and expirmenting with it has opened my mind to different styles of programming (since I am more a functional coder). I woudn't even be surprised if you're asked to use it at your next gig, so I would suggest that you experiment with it - I actually thought I wouldn't like it, but surprisingly I actually really like things, both from a syntatical and high level perspective.