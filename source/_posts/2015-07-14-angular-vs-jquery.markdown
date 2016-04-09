---
layout: post
title: Stop Comparing jQuery to AngularJS
description: It's a debate that begets a debate, one is a library that interacts heavily with the DOM and the other a framework that abstracts away the DOM
wordcount: 624
manualdate: July 14, 2015
category: JavaScript
---

Note: As an AngularJS developer I've kept this post balanced as my short plausible opinion in the wee bit of spare time I have.

Yes, I know there are two camps these days, but hear me out please :)

It's a debate that begets a debate, one is a library that interacts heavily with the DOM and the other a framework that abstracts away the DOM. Some might forget about jQuery when working with Angular and others are infatuated with leveraging the power of both - if you're using Angular and want to do mundane things like animating or showing and hiding things I feel the approach it the Angular way by by looking at Angular directives like <code>ng-show</code> and <code>ng-animate</code> or <code>ng-class</code>and not loading jQuery (yes, we know you love jQuery's syntax and have been working with it forever. I admit I felt like a Demi-God the first time I used jQuery).

You might have run into this type of code before:

<pre><code class="language-javascript">
var myApp = angular.module('myApp', []);

myApp.directive('myWidget', function() {
    var linkFn;
    linkFn = function(scope, element, attrs) {
        var animateDown, animateRight, pageOne, pageTwo;
        pageOne = angular.element(element.children()[0]);
        pageTwo = angular.element(element.children()[1]);

        animateDown = function() {
            $(this).animate({
                top: '+=50'
            });
        };

        animateRight = function() {
            $(this).animate({
                left: '+=50'
            });
        };

        $(pageOne).on('click', animateDown);
        $(pageTwo).on('click', animateRight);
    };
    return {
        restrict: 'E',
        link: linkFn
    };
});
</code></pre>

Thanks [JSFiddle for the above code](http://jsfiddle.net/simpulton/E7xER/). I still feel it leads to brittle, non reusable and hard to maintain code inside AngularJS. Of course there would be another solution to the above the AngularJs way.

Anyhow, moving on: Angular is very different to jQuery, comparing them is like comparing apples to oranges - it's ludicrous to do so yet you hear this all the time in developer circles by the water fountain et cetera. Angular is a full fledged MVC framework and only contains a very light version of jQuery called JQLite; that too only to animate the likes of <code>ng-class</code>. jQuery is a fantastic wrapper for DOM manipulation and enriches our websites thoroughly. AngularJS is an entirely different ballgame, bringing complexity like Ruby and Rails, MVC (DI, routing, scope) and other server side frameworks while extending them on the front end.

So jQuery is equivalent to swimming, easy to understand and not too difficult to learn - a great and convenient way to cross the Thames river would be to use a library like jQuery. AngularJS is equivalent to a ship, it requires more effort to acquire it and to learn how to operate it. You might even need a whole crew of people to do it - so why bother if swimming is so much easier. I'm not saying folks shouldn't stick to the easier method, but it's a mistake to take that a step further and say that nobody ever needs to do anything but swim.

Manipulating the DOM is definitely part of an application, but not the end-and-b all. I know you feel that frameworks are meant to make things easier in the future and you might argue that Angular isn't even backwards compatible. With it's nature Angular is very opinionated, and you're locked into the Angular way throughout your application development life-cycle (unless you choose to run jQuery along with it).

Just deal with the fact that jQuery and Angular and entirely different beasts - if you use jQuery to do Angular-y stuff then you'll end up with lots of unmaintainable spaghetti code. Unfortunately developers fear their apps will be deprecated and Angular 2.0 has become a joke.

I have opinions about what Google might be thinking about Angular 2.0 and all the radical shocking changes that come with it, I might share it in a next post. I will say that the web evolves and that's a chance not a tragedy....
