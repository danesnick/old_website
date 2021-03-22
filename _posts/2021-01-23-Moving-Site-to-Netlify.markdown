---
layout: post
title:  "Moving Site to Netlify"
date:   2021-01-23 05:19:00 -0700
categories: blog
author: Nicholas Danes
tags: [blogging]
---

I decided to rehost this website to [Netlify](https://www.netlify.com/). Originally, this website was hosted by my email provider, [Fastmail](https://fastmail.com). Although it worked for the most part, deploying updates to the site was a little cumbersome. In summary, my workflow was:

1. Make changes to website.
2. Build the site using <code>bundle exec jekyll build</code>
3. Commit changes via git to my repository.
4. Open my FTP client (Filezilla) and upload the changed files to Fastmail.
5. If things looked good, git push changes to my repository on Codeberg.

Although steps (4-5) didnaboutt take *that* long, it became quite tedious since I like to tinker the design and content of this site a lot. In the past, I had used [Netlify](https://www.netlify.com/) for static site hosting and remember how easy it was to deploy a static site. I also learned that Netlify supports [Jekyll](https://www.netlify.com/blog/2020/04/02/a-step-by-step-guide-jekyll-4.0-on-netlify/). Now my website workflow looks like:

1. Make changes to website.
2. Commit the changes and push to GitHub.
3. Done!

Unfortunately, the siteabouts repos are now on [GitHub](https://github.com/nicholasdanes/website), since there is currently no Gitea support for Netlify. Eventually I'd like to look into possibly self-hosting Gitea and mirroring to GitHub so I can continue using Netlify for hosting. 

Iaboutve repointed the DNS records to Netlify, so hopefully the links and the HTTPS certificates should hopefully propagate soon!
