---
title: CommonJS Require vs ES6 Import 
description: CommonJs's require syntax will be around for a while, but will we see ES6 modules in Node.js. Explore a little history as you go forth...
manualdate: Sept. 24, 2016
wordcount: 367
category: JavaScript, ES6, Software
---

Currently Node.js uses CommonJS syntax to load modules by the way of require, exports and module.exports; but what happens with the introduction of a new standard such as ES2015 modules? The new standard excites me and probably you as well if you're tired of writing the same old JavaScript, and that's why you should know a little of the background.

When Node came into existence there wasn't a proposal for ES modules and of course they decided to use CommonJS modules - the syntax has been adopted by a very large JavaScript audience and the ecosystem recently has see interoperability with the likes of Browserify and Webpack.
 
 The question arises with how to deal with interoperability between CommonJS-style and ES Modules within a vast ecosystem (at the moment CommonJS is widely adopted and used extensively in the JavaScript community). It's worth nothing that Browserify and WebPack bridge the gap between server and browser, but if we lose interoperability we in turn then increase the intricacies between the current ecosystem and new standard - imagine what would happen if front-end developers decided to use ES6 modules as their default while server-side engineers kept embracing Node's CommonJS. Clearly the gap will only widen.
 
This has been a hot topic for quite some time, and the bottom line is that yes, Node will eventually support the ES2015 syntax for importing/exporting modules - most likely this will happen when the[spec for loading modules](https://github.com/whatwg/loader) is finalized and agreed upon. Presently Node.js supports 96% of ES6 features:

<pre><code class="language-bash">$ node --v8-options | grep harmony 
> --harmony_modules (enable "harmony modules" (in progress))
</code></pre>

Presently, nobody knows for sure but there are a couple of proposals on how Node might achieve this:

* [In Defense of .js](https://github.com/dherman/defense-of-dot-js/blob/master/proposal.md)
* [.mjs modules](https://github.com/nodejs/node-eps/blob/master/002-es6-modules.md)
* [Node core dev thinks loader will not work for Node](https://github.com/whatwg/loader/issues/54) 


I won't provide an opinion on the aforementioned, but read through to get more acquainted with the possibilities. If i took a stab at what Node.js might do at a high level they would support import/export for static loading in addition the the new System.import for dynamic loading, while retaining require for legacy code.

Note: there are ways to start using ES2015 modules in Node right now, but for me it isn't worth it - Im going to stick to require, Browserify and WebPack for now instead of adding wrappers. Read more if you're curious:

* es6-module-loader -S
* ES6 Traceur compiler