---
layout: post
title:  "Welcome to new Sensu Plugins!"
author: Matt Jones
date:   2015-01-27 03:20:18
categories: update
---

Welcome to the new Sensu Plugins website and [repos](https://github.com/sensu-plugins)!

There are a lot changes dropping in the next few months and all of them should greatly benefit the community.  A few of the changes have already been made, this site being a major one.  The [Developer Guidelines](http://sensu-plugins.github.io/contributing/) have also been updated to reflect some of the new features dropping over the next several months and the new policies that these bring.

Before we get too deep into things let me assure you that there will be no forced upgrades, changes in license/functionality, or anything else to harm our precious, held-together-with-duct-tape-and-<strike>perl</strike>ruby, monitors.  Sensu plugins was always designed to be an integral part of an open framework and that will not change.  What is going to change is the manner in which the plugins are written, test, built, and delivered.

This has always been a community project built upon the hardwork and input of many people, sometimes though people don't realize they can or should contribute.  This [post](http://sensu-plugins.github.io/issue/2015/01/27/sensu-plugins-roadmap.html) is a great example of how things will be done from now on.

### Sensu Plugins Blog

Whenever major changes are coming or hot issues, bugs, etc present themselves we can now create a simple blog post that gives an overview of the topic with a direct link back to the original post.  This post will be much more accesible then an Issue or a Pull Request buried among two dozen plus repos.  The RSS feed, for those that want to utilize it, will be ideal for keeping up with community developments and codebase changes.

### New Repositories

Why so many repos?  One of the major changes, if not the main change, will be the splitting up of the [Sensu Community Plugins](https://github.com/sensu/sensu-community-plugins) repo in the many smaller repositories.  Extensions, handlers, and mutators will be broken out completely into their own repositories as well.  These repos will be organized by application and contain all plugins used by the application.  This will allow much more granular deployments and easier versioning.  It will no longer be necessary to bump the entire project for a simple typo in a single plugin.  [Issue 985](https://github.com/sensu/sensu-community-plugins/issues/985) has been created for this discussion.

### Packaging

In the very near future each of these smaller repos will also be built into their own gem and released to RubyGems.  This will allow you to add 'sensu-plugins-aws' to your cookbook, manifest, or bundle and get either the latest version or a version of your choice.  At specific intervals throughout the year, the current thinking is quarterly, a meta-gem will be released containing the latest stable builds of every gem for those who would like to go the monolithic route.

A user could also create their own meta-gems if they would like, consisting of every gem needed for their own stack.

The timeline, reasoning, and further details can be found [here](http://sensu-plugins.github.io/issue/2015/01/27/sensu-plugins-roadmap.html) and [Issue 847](https://github.com/sensu/sensu-community-plugins/issues/847) but in a nutshell there will be ample time for people to transition to this new concept.  New features will continue to be accepted into the old repo till at least May 2015 while a build and release pipeline is stabilized.  Around this time the old repo will be frozen for all feature requests, bug and security fixes will still be actively merged till at least June.  I stress this timeline is very movable and dependent on a lot of hard work by several people.

When the community feels it is ready and has faith in the new pipeline and build process, the old repo will be hard frozen and archived in place.

### Documentation

Documentation for the plugins will be automatically generated from RDoc sources, built into each gem and also served from a central location on this site.


I hope to continue helping to build and work with this great community and I am always open to new ideas, ways of thinking, or being told I am flat-out wrong.
