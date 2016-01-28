---
layout: post
title:  Sensu Plugins 2016 Roadmap
author: Matt Jones
date:   2015-01-28 12:09:18
categories: issue
---

It's been a long time since we broke anything and they say if your not breaking anything then you are not trying hard enough, so on with the show.

The new sensu-plugins org has been a fairly good success, it has been a bumpy road for sure, but overall we feel the transition has been fairly smooth and has done a lot to make the plugins easier for many. They are certainly easier to manage from a developer/maintainer standpoint and last time I checked there were nearly 170 different plugin repos and on average we add a new one every month.

From a user's standpoint the latest versions of Sensu have [docs](https://sensuapp.org/docs/latest/plugins) and tooling built to help manage the plugins as well.

A huge thanks goes out to the community for making this growth possible and also the efforts by the committers. I would guess that we have at least a dozen new pr's a week across all the repos, which when you think about it, is pretty cool. As we move forward all pull requests are welcome, we don't care what you want to monitor. One that I always use as an example is [sensu-plugins-kegbot](https://github.com/sensu-plugins/sensu-plugins-kegbot), because an empty keg in a travesty that could have been avoided.

Now, on to the business at hand. There are several changes coming down the pipeline this year that should move this project forward even more and help to ensure we can adapt and continue to meet future monitoring demands.

The first will be the the death, in glorious battle, of the orginal [sensu-community-plugins](https://github.com/sensu/sensu-community-plugins) repo on **Wednesday Feburary 3rd**. The [sensu-plugins](https://github.com/sensu-plugins) org has been active for nearly a year and gems have been available for at least six months now. Trying to maintain two codebases is just not feasible, advisable, or even sane. Just to be clear, the old repo **will not** be removed, instead it will simply be zero'd out and the README will contain a link to the new org.

All existing pull requests that can be safely merged will be and all open issues will be closed unless they are an active conversation from within the previous two weeks. To ensure you can still use this repo if you must, you should pin to a commit that works for you. It would be safe to assume that about 95% of the code in that repo has been ported and updated within the new org but a final walkthrough will be done after the closure of the repo to ensure all code that needs to be ported is. One thing to note, **extensions** will not be ported to the sensu-plugins org. These interact with the Sensu server by design and therefore will remain under the Sensu org as they are the group best suited to openly maintain them.

On the roadmap this year will also be the dropping of support for Ruby 1.9.3 in favor of the embedded Ruby that is packaged with Sensu.  This will happen most likely around the end of the summer but that is a moving target at this point. We should all be installing from the omnibus installer or if not at least using the embedded Ruby. This is not to say that functionality will be broken but as a project we will no longer guarantee that all plugins will work with 1.9.3. Many still will but as time moves forward this will become less and less, several plugins have already dropped 1.9.3 but we are now letting people know that this is coming down the line project wide.

There has also been some internal dialogue on monitoring containers, specifically where it concerns carrying around the weight of a runtime environment. How to monitor containers and what tools you use for this are far out of our hands, what is in our hands is helping to ensure Sensu can be used in this capacity if the desire is there. With all that being said at this time **unofficially** there will be support for golang. For the time being, only x86 and amd64 will be supported but as time allows support for Windows and BSD will be added. While it is currently true you can write your plugin in any language and open a pull request, there are some limitations to using gems with non-ruby code.

All plugins have also always been released as tarballs and at this time this will be the preferred method if you wish to utilize the non-ruby plugins. Anyone can write binstubs for the non-ruby code and they will be happily accepted but tarballs are simply a great platform-independent and language-agnostic way to distribute code. They will remain 1:1 with the gems, which will still be considered authoritative. Ruby and the gems that are currently used to distribute the plugins will not be going away at any point in the foreseeable future, we are simply providing another (at some point) supported way to write, distribute, and install plugins for Sensu.

In connection with the above, we would love to talk with anyone who has worked on Sensu plugins using golang. We can say from the outset all golang code needs to be fully tested, linted, and vetted before it will be merged and godeps will be the preferred way to handle vendoring. Many more details will be forth coming as things get worked out, but a rough, automated CI pipeline using Travis and golang 1.5x has already been poc'd.

So until next time, may your pagers remain silent(or off).

The Sensu Plugins Committers

