---
layout: post
title: "Why you should use Netlify for your dev blog"
image: netlify.png
description: "Some reasons to host your dev blog on Netlify instead of Github Pages."

---

![Netlify logo]({{ site.baseurl }}/images/netlify.png){: .center-image }

All software developers should really be blogging, whether you're just getting started or have been in the industry for awhile. It's a great way to get better at communicating, go deeper on topics than you would otherwise, engage with the larger development community, and get feedback and alternate perspectives that help you accelerate your learning.

The current iteration of my blog has been going since 2014. I recently started having it hosted on a free service called [Netlify](https://www.netlify.com/), which has so far been a fantastic experience for reasons I'll go into below.<!--more--> I am not affiliated in any way with Netlify, nor am I accruing large stacks of referral cash from anyone who signs up, but nonetheless I want to get the word out.

For awhile now I've been using [Github Pages](https://pages.github.com/) as my blogging platform of choice. There's always the temptation to try to write your own blogging platform, but Pages was very attractive in its relative simplicity. It uses [Jekyll](https://jekyllrb.com/) under the covers, which is a Ruby application that does the templating and has some nice plugins. The reasons why I like it still hold true:

* I get to write the posts in Markdown. If I ever want to switch to a different blogging application then it's straightforward to do some parsing and convert to another format. I can use whichever text editor I want (currently Visual Studio Code which comes with Markdown previewing). Avoiding storing my posts in some database somewhere is a key benefit.
* Using git as the underlying storage medium gives me built-in versioning and a distributed backup in the form of Github and the copies I have checked out to various computers. Branches are also a nice place to get drafts started for new blog posts.
* Static pages are nice because I don't have to worry about security holes in admin applications or the server getting overwhelmed if I should ever be so lucky as to get flooded with traffic. (Dare to dream!)

Github Pages was serving up my blog fine for years, but then I heard about a service called Netlify, which is free for personal use (naturally with paid plans with additional capabilities). Some features that I've loved:

![Netlify PR preview]({{ site.baseurl }}/images/netlify-pr-preview.png)

* Great Github integration. As soon as I create a pull request against a branch Netlify does as build of my site and publishes it to a preview URL so I can see how it looks. Fix a typo, resize an image, and re-push, and it's on the preview site in less than a minute. Merge the branch in when it's ready and the live site updates.
* Easy HTTPS. I just had to click a button and I had a Let's Encrypt cert working. Almost *too* easy.
* Drop a snippet into a textbox to have it inserted into every page. Very nice to be able to add Google Analytics and be able to tweak it without adding it to my template.

Most of the work to switch over was figuring out what needed to go in my Gemfile and ruby-version file, thankfully simple to diagnose thanks to Jekyll's informative error messages.

Overall I've found Netlify to be fantastic. The free plan meets all my needs, including custom domains, and they seem to be working on a number of additional features. Best of all, it's super fast to switch back to Github Pages if you so choose, better than can be said for a lot of services that offer free tiers but try to lock you in. I highly recommend giving Netlify a try for your tech blog and getting your writings out there.