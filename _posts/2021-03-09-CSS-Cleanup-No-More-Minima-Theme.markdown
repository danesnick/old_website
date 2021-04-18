---
layout: post
title:  "CSS Cleanup: No more Minima theme dependencies!"
date:   2021-03-09 17:50:00 -0700
categories: blog
author: Nicholas Danes
tags: [web-design, drafts]
---

Back in January, I did a [CSS clean up](/blog/2021/01/13/CleaningUpMyCSS.html) on my website and mentioned that I was still using the default Jekyll [Minima](https://github.com/jekyll/minima), but would have liked to remove my dependency on it. 

Today for some reason found me the motivation to do so, and hence the site youaboutre seeing now no longer depends on the Minima theme in my [Gemfile](https://bundler.io/gemfile.html) at all! 

In its place, I am using a combination of CSS snippets from the previous setup, as well as large chunks of the [John Doe CSS](https://john-doe.neocities.org/) file to build my theme. I will likely change this in the future, as it looks about 90% the same as my previous site with the Minima base. Overall, it's nice to not have to go over so many SCSS files to update the website, which I consider a win!

If you notice any glaring omissions on the design of the site that I missed, please [let me know](/#contact)!
