---
layout: post
title:  "Ditching GoatCounter: Do I really need analytics?"
date:   2021-02-12 08:53:00 -0700
categories: blog
author: Nicholas Danes
tags: [minimalism, blogging, mental-health]
---
*Disclaimer: I have no relationship with GoatCounter other than using their service and briefly contributing to the developer on GitHub sponsors; opinions are my own!*

This morning, I decided to remove the Privacy-respecting analytics service [GoatCounter](https://www.goatcounter.com/) from my website. There are a few reasons for this: (1) website performance and (2) for my mental health in terms of intentionality. **I should note that I absolutely have no issue with GoatCounter in principle and my reasons are largely personal.**

## Website Performance

### Javascript (JS)
Initially, I had been using the javascript version of GoatCounter. The benefit to do this was very detailed analytics, which includes:

* Pages that were visited
* URL Referrer
* Browser
* Operating System
* Screen Size
* Country (and State/Providence) of Origin

This was awesome! Since, it allowed me to see what pages were being viewed, allowing me to interpret what people were interested in. However, as someone who cares about website accessiblity and keeping my website as [lean](https://leanweb.dev/) as possible, I found that GoatCounter's ~2.5KB (compressed) size was a little too high for my tastes.

### No-JS Option

I decided to experiement with GoatCounter's No-JS option of website analytics, but you lose a lot of data. This method works by adding a small 1x1 pixel on your website that can see when people load your website. However, you lose my favorite feature of the analytics: seeing what pages people visit. 

In addition to this, unfortunately, load times for my website were fairly poor due to GoatCounter. even with the no-JS analytics option, I was seeing ~600 ms of latency to load my front page since it was waiting on Goatcounter. You can see the difference with GTMetrix below:

<figure>
<img loading="lazy" src="/images/feb12_2021_blog/goatcounter_before.png"><br>
<br>
<img loading="lazy" src="/images/feb12_2021_blog/goatcounter_after.png">
<figcaption><i>Before (top) and after (bottom) removing the no-JS GoatCounter</i></figcaption>
</figure>

## Analytics became another point of anxiety

Recently, Matt D'Avella, a "minimalism" YouTuber, made a [video](https://www.youtube.com/watch?v=NKYFNJMjtEM) on re-evaulating his relationship with "views"/analytics on YouTube Studio, the analytics dashboard for content creators on YouTube. In summary, Matt suggests that looking at these numbers can be a burden on your mental health; with analytics for me, I found this to become true. I found myself checking GoatCounter way too often, even knowing that nothing has changed. This became even more apparent when I switched to the no-JS option, where really the only data point was a new pageview. After seeing this video, I realized I was having a similar relationship with my analytics on GoatCounter. Hence, I decided to remove analytics entirely.

## Remembering why I decided to blog

I gained motivation to start blogging due to the wonderful community over at [Fosstodon](https://fosstodon.org). However, it is easy to lose sight on the original intent of blogging for me, and that is the enjoyment of the writing process. Sure, it's nice to receive feedback and gratitude for my writing, but I also don't want to be dependent on it. Analytics, at least at this time in my life, aren't the best way for me to motivate me to continue blogging. Especially since blogging is essentially just an enjoyable hobby and a carthatic process for me. 

## Will I bring back analytics?

Maybe? I do think there is a place for analytics on the web, and in particular ones that respect people's privacy. Google Analytics is still essentially everywhere, so I really hope that alternatives like [Plausible](https://plausible.io) and [GoatCounter](https://goatcounter.com) gain more momentum on the web. In particular, I think these analytic services seem perfect for personal blogs like this one! 

Maybe when I'm in a better place mentally, in terms of my relationship with technology, maybe I'll bring one of the analytics services back to my website. For now, I'll just focus on writing! 
