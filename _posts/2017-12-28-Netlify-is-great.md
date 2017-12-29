---
layout: post
title: "Why you should consider using Netlify for your blog"
image: netlify.png
description: "Some reasons to consider Netlify over Github pages for your blog."

---

![Netlify logo]({{ site.baseurl }}/images/netlify.png)

The current iteration of my blog has been going since 2014. I recently started having it hosted on a free service called [Netlify](https://www.netlify.com/), which has so far been a great experience that I'll go into below. I am not affiliated in any way with Netlify and am not accruing large stacks of referral cash from anyone who signs up, but nonetheless I want to get the word out.<!--more-->

For awhile now I've been using [Github Pages](https://pages.github.com/) as my blogging platorm of choice. It uses [Jekyll](https://jekyllrb.com/) under the covers, which is a Ruby application that does the templating and has some nice plugins. The reasons still hold true:

* I get to write the posts in Markdown. If I ever want to switch to a different blogging application then it's pretty easy to do some parsing and convert to another format. I can use whichever text editor I want (currently Visual Studio Code which comes with Markdown previewing).
* Using git as the underlying storage medium gives me built-in versioning and a distributed backup in the form of Github and the copies I have checked out to various computers. Branches are also a nice place to get drafts started for new blog posts.
* Static pages are nice because I don't have to worry about security holes in admin applications or the server getting overwhelmed if I should ever be so lucky as to get flooded with traffic. (Dare to dream!)

Github pages have been fine, but then I heard about Netlify, which is free for personal use. Some features that I've loved:

![Netlify PR preview]({{ site.baseurl }}/images/netlify-pr-preview.png)

* Great Github integration. As soon as I create a pull request against a branch Netlify does as build of my site and publishes it to a preview URL so I can see how it looks. Fix a typo, resize an image, and repush, and it's on the preview site in less than a minute. Merge the branch in when it's ready and the live site updates.
* Easy HTTPS. I just had to click a button and I had a Let's Encrypt cert working. Almost *too* easy.
* Drop a snippet into a textbox to have it inserted into every page. Very nice to be able to add Google Analytics and be able to tweak it without adding it to my template.

Most of the work was figuring out what needed to go in my Gemfile and ruby-version file, thankfully easy to diagnose thanks to jekyll's informative error messages.

Overall I've found Netlify to be fantastic. It's free unless you want more fancy features, supports custom domains, and has cool stuff in the works. Best of all, it's super easy to switch back to Github pages if you so choose, better than can be said for a lot of services that offer free tiers. I highly recommend giving it a try.