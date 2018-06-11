---
layout: post
title: "Embrace the walking skeleton"
image: umbrellas.jpg
description: A walking skeleton can relieve pressure and find problems earlier.

---

Technology infrastructure is often difficult. Many of us dream of living in a world filled with fluffy white clouds or a serverless existence, while sadly still being bound to the land of ACLs, config settings, and other such mundane matters.

In such a world as that, getting a new server application up and running on the first attempt can be a miracle. Remember to have all your config settings set properly for each environment. Make sure that all accounts have been setup for each environment and with the correct permissions. It's a lot of pressure when you're expected to deliver features as well. 

Walking skeletons are a concept I recently embraced that take away much of the scariness. The gist is that you make a shell for your application, whether that's an API, a background service, a website, or whatever. You don't implement any feature yet, but instead just have it interact with whatever external systems you know that it will utilize when the features do start shipping. 

This lets you shake out any environmental-specific problems before you start piling on complicating factors. You're able to establish a baseline so that if suddenly you can't connect to a database, write to the filesystem, or whatever other external systems you connect to are suddenly inaccessible, you can trace through the commits and see when things started to go wrong.
