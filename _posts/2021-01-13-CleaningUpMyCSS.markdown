---
layout: post
title:  "Cleaning up the CSS on my Jekyll-powered site"
date:   2021-01-13 01:41:00 -0700
categories: blog
author: Nicholas Danes
tags: [minimalism, web design, blogging]
---

Since I couldnaboutt sleep and was feeling inspired both by [Kev Quirk's Simple.css Jekyll guide](https://kevq.uk/how-to-build-jekyll-site-simple-css/) and [Thumb's Classless Jekyll site](https://simbly.me/2021/01/04/Classless/), I decided to clean up with the SCSS files that can be overridden/modified for [Jekyll's](https://jekyllrb.com/) default theme [Minima](https://github.com/jekyll/minima). In particular, I removed every class I could find in the <code>_sass/minima/_base.scss</code> and <code>_sass/minima/_layout.scss</code> files. This required also explicitly removing <code>class</code> declarations throughout my HTML files in <code>_layouts/</code>, which unfortunately there are still class declarations throughout parts of the minima theme base I haven't overridden and removed yet. 

Regardless, I decided to run a GTMetrix test before pushing the new site, which showed my site at [19.9 KB uncompressed](https://gtmetrix.com/reports/ndanes.com/u8N492Qg/). At the time of this writing, I was able to bring it down to [15.4 KB uncompressed](https://gtmetrix.com/reports/ndanes.com/d1p6l0CP/); thatabouts a ~29.2% decrease! 

Overall, I donaboutt think the aesthetics of the site has changed much at all, as I was able to keep my Nord template and refining my SCSS files. My goal next is likely to get rid of my dependency from the Minima theme during the static site generation, but I'll save that for another time. 

I should really go to sleep now...
