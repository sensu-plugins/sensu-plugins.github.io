---
layout: post
title:  Sensu Plugins Gem and Deployment Updates
author: Matt Jones
date:   2015-04-21 08:30:00
categories: update
---

### Continuous Integration and Continuous Deployment (finally)

As some of you may have noticed the number of plugin repos being built into gems is growing.  It's about to grow much more rapidly.  We are currently integrating with [Codeship](https://codeship.com) to be our primary deployment pipeline.  Travis is still being used and will continue to be used as Codeship does not currently have a method of returning the build status publicly, a hard requirement by the team.  What it gives us over Travis is a way to debug build and test issues in ways that Travis can't provide, also the completion of a build is much faster.  There are other factors as well but these are the big ones.  I stress, all build and release info will always be public knowledge and shared in a very simple easy to find manner.

There are still a few mysteries to be solved including signing the gems and a true 'push a button' and the version is bumped, a github release is created and a gem is built and published.  Right now the pieces are in place but it requires pushing two buttons...that is two too many for my liking.

### Gem Metadata

Each gem being built has metadata that can easily be queried and is designed to allow users to get a good quick read on the current status of the gem and how stable it is.  This functions much like the [Milestone](http://logstash.net/docs/1.4.2/plugin-milestones) idea that Logstash plugins are built around, thanks goes out to @hatt for suggesting this.  

`{ 'maintainer' => ''}`

The maintainer field can be anyone, please feel free to reach out to the team about adding your github handle to the gem and assuming 'ownership' of it.  Many of these plugins require specialized knowledge and by their very nature many people depend upon them to be high quality. Those who use them daily and have the most at stake should have an active voice in how they are written.

`{ 'development_status' => ''}`

The development_status field allows users to know the development state of a plugin:

* **active** Active development is ongoing by a developer or maintainer
* **maintenance** No active refactoring or development but someone is watching out for any new pr's or things to do.
* **unmaintained** The community as a whole is keeping an eye on this but no one has staked a claim to it (most plugins will end up here)

`{ 'production_status' => ''}`

The production_status field gives a quick glance on whether the gem should be used for production grade monitoring or if some review and care should be taken.

* **production grade** near 100% rspec and yardoc coverage
* **stable - review recommended** incomplete rspec and yardoc coverage
* **stable - review required** little/no rspec and/or yardoc coverage
* **unstable - testing recommended** throw stuff at the wall and hope it sticks (currently most gems are here)

If anyone else has suggestions for meaningful metadata then let someone on the team know.

### FreeBSd Support...Windows Too If I Must

We have also begun doing some testing with FreeBSD and Windows.  While it has always been possible to install the sensu client there was a grey area around if checks would work as many use Linux specific commands or conventions.

I am quite happy to say that much of the Linux specific code is being refactored out for Ruby specific code.  A good example of this was using df/du for the disk checks.  Several of them have been rewritten to use the [sys-filesystem](https://github.com/djberg96/sys-filesystem) gem and are confirmed to work on multiple variants of Windows Server and FreeBSD.  Shortly we will be creating platform repos for plugins related only to those platform, ala sensu-plugins-windows(https://github.com/sensu-plugins/sensu-plugins-windows).

Many other improvements are coming including documentation, a plugin directory, and most importantly, more gems.

### Standard Naming Convention

One of the underlying questions requiring feedback though is how to name the plugins.  As a community we should decide on a standard naming convention to be followed.  Many of us use various automation tools and having a standard naming scheme just makes sense.

I personally am of the mindset that a check is different from a metric.  I feel that checks are plugins that return 0:3 and some status output, and metrics return data that can then be further aggregated and analyzed.  With this in mind I would like to propose the following naming scheme:

* check - for any plugin that returns 0:3 and any human readable text
* metrics - for any plugin that returns data that is bound for some sort of collection tool.
* extension - any plugin that extends the functionality of Sensu or another plugin
* mutator - any plugin that modifies event data for a handler
* handler - any plugin that acts up event data

I stress this is my personal thought and I am more then welcome too and encourage different opinions.  Once a decision is made and incorporated many of the gems currently in an alpha state will be rebuilt with proper semantic versioning.  We would like to avoid any breaking changes, such as name changes, once we drop the alpha state
