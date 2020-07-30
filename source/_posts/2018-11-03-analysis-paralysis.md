---
title: Testing & Analysis Paralysis
manualdate: November 03, 2018
description: Prefer simplicity and use TAP (Test Anything Protocol) to minimize analysis paralysis. Just get on with it
wordcount:  296
category: JavaScript
---

Much of my time is spent on unit testing my code and I’ve been sinking needless unecessary hours into configuration and then reading through the documentation to figure things out. Then I have to assess out what matchers I’ll need, and whether i should use a mock from the plethora of choices. All of this is way too much cognitive load, I’d much rather choose a simple set of tools, /e: Tape and start writing my tests immediately - all i have to do is `require ‘file.js’` and begin.

Jest, Mocha and the likes of which give me too many choices and I suffer from analysis paralysis when trying to find the best path. I’d rather spend that time writing my tests and being done with it. After all you don’t want to spend more time configuring your environment for testing, then writing you tests as you do writing good software for your application.

I should be able to write simple tests based on pure functions quickly that act as documentation to me or anyone when my tests fail. To this end I have started using tape based on TAP (Test Anyting Protocol) for my testing and love the workflow - I only need a couple of assertions that cover most anything.

I encourage others to use this simple yet effective technique. No clutter and quick results, I’m in test bliss and can add in tape modules where i need. I really feel the rest is overkill - if you’re just learning how to unit test, starting with a fancy library can be overwhelming. TAP is the way you should go, otherwise you’ll tend to lose yourself to the configuration and setting up the environment instead of concentrating on what’s important.

Writing good software and testing.
