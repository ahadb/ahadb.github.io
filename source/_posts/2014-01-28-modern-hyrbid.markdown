---
layout: post
title: Web Designer & Front End Web Developer - Today's Modern Hybrid
description: Welcome the hybrid; part designer, part developer - a talented person who can design visually, is a Html/CSS guru and yet also has the mindset of a developer.
manualdate: January 01, 2014
wordcount: 1,609
---

The modern web has evolved for web designers over the past years and especially intensive on the client side. Although a highly debatable topic for web designers in this day and age, I'll be bold enough to say there is a new breed of web designer and they're becoming quite popular with a plethora of web centric companies and organizations around the world.

Welcome the hybrid; part designer, part developer - a talented person who can design visually, is a Html/CSS guru and yet also has the mindset of a developer. Mindset here meaning understanding the tools of the trade when it comes to web development and being able to integrate those into her workflow.

We're not just talking about one single function here. Many designers will argue that their role is to concentrate on visual design in Photoshop, Illustrator et-cetera and nothing more. Asking them to translate their design into web standards Html/CSS and add some Javascript is like asking a cat to say "woof woof". They'll say: [let the developers code the CSS](http://www.uie.com/brainsparks/2011/05/31/why-the-valley-wants-designers-that-can-code/). Some product designers will argue that web designers should have the skill to translate visual designs to the browser and into production ready Html/CSS/Js just as easily as firing up Photoshop and laying out typical elements. From what I've seen the more experienced the designer, the more they tend to be able to convert their mocked up visuals to the web, however it's also situational and dependent on the sort of environment you work in.

#CSS Designers Think Like Developers
Often CSS designers or CSS gurus who can code well in CSS are usually inclined towards development as opposed to just visual design. Still the assumption remains that if you can code CSS you must be a web designer. Look at the folks at  [Bootstrap](http://www.getbootrap), [Foundation](https://github.com/zurb/foundation) or [Semantic](https://github.com/jlukic/Semantic-UI‎). They can be classified as web designers, but the following commands will not be alien to them:

$ sudo gem install less -s http://gemcutter.org
$ sass --watch style.scss:style.css
$ npm install less
$ ssh username@hostname
$ grep
$ git push origin master

Case in point. A pure graphical or visual designer will find the above counterproductive and will never take interest in coding, commands or the command line. [SASS](http://sass-lang.com/), [Compass](http://compass-style.org/) and [LESS](http://www.lesscss.org/) as well as other CSS preprocessors are also increasingly popular by talented designers around the world. Moreover these designers use programmer like principles when writing CSS; conditionals and loops, variables and mixins and other logic built into their CSS code.

Lot's of CSS folks out there will argue that they think CSS is just fine without developer coerced preprocessors, logic, variables and programming fluff. They'd rather write CSS from zero to one hunred percent and know the pro's and con's of the language.

I'll share a great excerpt[1] that explains it quite well:

>Most CSS gurus aren’t programmers. When they start seeing logic, variables, mixins, and other programming constructs  in their style sheet, they freak out a bit. CSS gurus are just that: CSS gurus. They already know how to write their  way out of any paper bag you can find using CSS. They’re experts. They don’t need a preprocessor. Developers are      writing these things because, for them, CSS is confusing and missing useful functionality. But CSS gurus don’t look
at CSS that way. Most CSS gurus think CSS is, by and large, pretty darn great. Sure, we have little nits to pick,
but for the most part, CSS works for us, and we know how to bend it to our will.

>To the typical CSS designer, the command line is a frightening place.

>Even a simple CSS guru knows that code generation reeks of inelegance (not saying Sass is inelegant or that there
aren’t good examples of code generation … just that, as a concept, it scares people).

If you're a CSS guru and have worked with a preprocessor before then the code below should not scare you:

@the-border: 1px;
@base-color: #111;
@red:        #842210;

#header {
  color: (@base-color * 3);
  border-left: @the-border;
  border-right: (@the-border * 2);
}
#footer {
  color: (@base-color + #003300);
  border-color: desaturate(@red, 10%);
}

#What Other Skills Could Hybrids Have?

Keep in mind that as a hybrid you should be able to design visually pleasing interfaces and coupled with front end web development take that layout and give it life within the browser. All the elements of your visual designs that you've obsessed and crafted over should function practically in the client on the browser.

The approach to building websites should be simple, and the craftsman should know how to use and manipulate the tools she has to effectively get the job done.

##Adobe Creative Suite:
Photoshop / Illustrator / InDesign: This is where it all begins, your sketches and thoughts come to life when you fire up the visual creation too of your choice. I'm a big beleiver of simple and functional design, so for me I keep my designs and interactivity as realistic as possible. That said, there is just so much more
possible in the browser than there was 2 years ago. I see this trend continuing.

##Visually Prototype and Scaffold Designs = Build Less:
I've always been a fan of visually prototyping first and then just building up a base scaffold of your website or application. In my opinion, when in the build phase just add the necessary elements to make your design come to life. Keep building with less in mind.

##Javascript:
Most of our coding skills are self taught. These days it's not enough to know jQuery or just one library. You should be able to work with more than one library or framework, but most importantly you should understand Javascript as a language at it's core. Other things here come to mind such as client side templating, Backbone JS, Angular JS and Ember JS as well as testing and performance.

Lot's more can be said on the aforementioned topic, perhaps I'll save that for a later post. Javascript is the virtual machine for the web so expect to be working alot with all aspects including the DOM, Objects, and your lexical programming.

##Git and Github:
Taking advantage of Github, cloning a repo, forking and contributing to rich open source projects should be first nature to you. If you're just starting out you don't need to know how to code to contribute to open source, there are numerous other ways if you'd like to be adventurous.

##In Browser Tools:
Having a good understanding of developer tools in the browser will take you a long way in debugging and understanding yours and other peoples code. Be sure to check out Google Chromes web inspector. Opera Dragonfly also has some pretty neat little features - I suggest having multiple browser tools to remotely debug and test. Also this is great tool for the curious minded..

##Front End CSS/Javascript Frameworks:
We have numerous front-end frameworks out there to design and develop mobile first, responsive websites and applications. Bootstrap, Semantic UI, Foundation are the first that come in mind.

##Command Line:
You can get alot done on the terminal and in this day and age it really shouldn't be an option anymore. Mac users have it prebuilt into their OS while others can take advantage of Linux or any *nix OS like Ubuntu or Mint. I really don't have much to say to the Windows folks out there, however you can install cygwin and make the command prompt in Windows behave more like Unix. I opine that Windows folk should virtualize a *nix OS or boot up from USB. It's pretty much that easy.


##Others
Here are some others and if you don't know how to use these methods and tools then at least start thinking about them. Knowing what they are, where to find them and what they do is the first substantial step:

* Process Automation (Grunt/Rake/Make/...)
* Code Quality using JS/CSS Hint
* Peformance (Gzipping, minifying, prefetching, optimizing, etc)
* More & more Javascript including JSON and restful API's, manipulating and populating data

#Alot to Digest?
This might be quite alot to digest and should in no circumstances be considered an exact guideline to what you should be doing. The web industry is huge and there is room for all kind's of people with multiple skillsets. This article is merely an attempt to give you information about web design and front end development in the modern world as well as introduce you to a new breed - Hybrid. A web designer and front end web developer.

Pure front end web developers have realized that they can call for and manipulate data on the client side. Instead of things being simplified they might look like they are getting more complex. Abstraction should simplify things and it appears that we might start behaving like software engineers who constantly automate repetive tasks.

Many argue that the [client side is a mess](https://www.tbray.org/ongoing/When/201x/2014/01/01/Software-in-2014) but we're not going there. For newbie web folks consider this article a guide to a solid guid to career path and progressive growth. Some would even say that I'm preaching religion and to which I would say there is nothing wrong with pursuing excellence.

Perhaps you might want to pursue it, perhaps you have a different path. The choice is yours.

##Footnotes
[1] Thanks to the blockquoted text from a post on Less from [Stuff & Nonsense](http://www.stuffandnonsense.co.uk/blog/about/less)
