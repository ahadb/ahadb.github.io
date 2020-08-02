---
layout: post
title: Sublime Plugins for Front End Devs
manualdate: March 08, 2015
wordcount: 309
category: JavaScript
description: Sublime Text, a text editor we all love. Blazingly fast, has a HUD for goto anything using [CTRL + P]
---

Sublime Text, a text editor we all love. Blazingly fast, has a HUD for goto anything using [CTRL + P]. I've been asked this question quite a number of times though so I'll do a quick post on some of my favorite plugins for the front end workflow.

<strong>Package Control:</strong> [Install first](https://sublime.wbond.net/installation). It allows users to manage packages very easily, with one shortcut you have access to a long list of plugins available to install and update is automaticly handled. Click View > Show Console and type in:


import urllib2,os; pf='Package Control.sublime-package'; ipp=sublime.installed_packages_path(); os.makedirs(ipp) if not os.path.exists(ipp) else None; urllib2.install_opener(urllib2.build_opener(urllib2.ProxyHandler())); open(os.path.join(ipp,pf),'wb').write(urllib2.urlopen('http://sublime.wbond.net/'+pf.replace(' ','%20')).read()); print('Please restart Sublime Text to finish installation')

<strong>Live Reload:</strong>  No need to hit the pesky refresh button in your browser with this time saving plugin. Just hit save and your browser will refresh automatically.

<strong>Sass:</strong> There are several here. Try using Sass, Sass Builder, Sass Snippets.

<strong>jQuery Snippets Pack:</strong> Includes a bunch of handy snippets for jQuery

<strong>CSS Snippets:</strong> Handy little package. The scope has been expanded to include LESS, Sass and Stylus files.

<strong>Auto Prefixer:</strong> You shouldn't have to care about vendor prefixes.

<strong>Clipboard History:</strong> Keep a history of your clipboard items. Let you paste them back in, as needed.

<strong>JS Minifier:</strong> Sublime Text plugin for javascript minification using Google Closure compiler

<strong>Bracket Highlighter:</strong> SBracket and tag codeblocker for Sublime Text. Bracket Highlighter matches a variety of brackets such as: [], (), {}, “”, ”, , and even custom brackets.

<strong>HTML5:</strong>An HTML5 bundle with snippets for easy access.
