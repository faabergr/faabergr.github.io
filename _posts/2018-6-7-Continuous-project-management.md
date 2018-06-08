---
layout: post
title: "Continuous project management"
image: todd-quackenbush-701-unsplash-cropped.jpg
description: Continuous deployment, where teams work in short cycles and push new versions of software frequently (perhaps multiple times per day), is a big mind shift from scheduled (often weekly) releases. Heavy-weight project management applications (hereafter refered to as "Jira" for no reason in particular) can be ill-suited to such compressed timelines and introduce a lot of overhead, and alternate tools are worth exploring to reduce bottlenecks and get the most value out of CI.

---

![Photo of tools]({{ site.baseurl }}/images/todd-quackenbush-701-unsplash-cropped.jpg)

[Continuous deployment](https://puppet.com/blog/continuous-delivery-vs-continuous-deployment-what-s-diff), where teams work in short cycles and push new versions of software frequently (perhaps multiple times per day), is a big mind shift from scheduled (often weekly) releases. Heavy-weight project management applications (hereafter refered to as "Jira" for no reason in particular) can be ill-suited to such compressed timelines and introduce a lot of overhead, and alternate tools are worth exploring to reduce bottlenecks and get the most value out of CI.<!--more--> 

The ideal system is to have a pair working on a particular story. You get better knowledge sharing, continuous code reviews, and many other benefits. Stories should be scoped as small as possible while big enough to provide some useful feedback for the next iteration. In the course of development work, it's natural for lots of additional work to be discovered. This "we learn along the way" ethos should be embraced, though it can also be a challenge to keep track of everything in your head on top of the current task at hand. We all have limited memory space.

This is where a lightweight system of tracking tasks comes in handy. The key is to have three statuses: "To Do", "Doing", and "Done". [Trello](https://trello.com/) or a similarly streamlined web app can work well here, or even the low-tech route of a whiteboard with stickies. All that matters is that it's low-ceremony and low-friction to do a brain-dump. A card/sticky may be as simple as "Refactor the order total calculation logic" or "Add post-deployment verification step".

Note that tasks can be something that reflects acceptance criteria and business requirements, known as "above the line" items, or infrastructure/tech-debt-related "below the line" items, which need to be done but aren't something of which a product owner need be aware. If it needs to be done before the software can be released, then it's worth writing down, even if you can't get to it at the moment. This includes such non-technical things like "Talk to team that maintains Catalog Service about getting pricing info" or "Get clarification on Requirement #2 from PO".

Add new items as you or your pairing partner think of them. Each should have enough info to follow-up on but small and concrete enough to finish quickly. A couple of hours all the way up to a day is a good rule of thumb. In the beginning of a new story there will likely be an explosion of new items, but it should taper off with some flare-ups as you come to grips with the true size of the development effort.

How does this relate to more comprehensive project management tools like Jira? Consider them as meeting the need of a different audience. Jira is used for visibility across (potentially) many different use cases: the product owner who wants to know the status of the feature, the manager who wants to know who is working on what and what is queued up next, the release manager wanting to get a sense of what is slated for the next release, and so on. This can often mean many required fields and sign-offs before an item can move into the next status, which is fine for needs similar to those just mentioned but unnecessary bookkeeping when you just need a glorified to-do list with easy tracking of what's been done, what you're currently working on, and what's still to be done.

If your organization and infrastructure are ready for it, as well as your automated test suite, you can even ship each "chunk of value" represented by a card into production. Feature flags or other techniques can decouple release from deployment, which is worth going into in its own post.

Can Jira and a lightweight solution co-exist? Many users hope for "one project management tool to rule them all" but these are sufficiently different use cases to support the use of two specialized tools and reap the benefits of each.

([Photo by Todd Quackenbush on Unsplash](https://unsplash.com/photos/IClZBVw5W5A))
