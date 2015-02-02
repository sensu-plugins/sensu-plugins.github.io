---
layout: post
title:  Sensu Plugins Gems
author: Matt Jones
date:   2015-01-31 04:16:41
categories: issue
---

Several [gems](https://rubygems.org/search?utf8=%E2%9C%93&query=sensu-plugins) have been released as of last night, and a few more are built in the repos.  The gems should be considered in an alpha state, they are functionally identical to the ones on the repos but please take care to read the changelog for each as some of the check or handler names have changed to better reflect their use.

There is no online documentation for them and they must be installed with the *--pre* argument for now or if using the chef gem_package *options('--prerelease')*.  The alpha status will be dropping on some of them as early as midweek if all goes well.  This will remove the need for the argument and the online documentation will be indexed at that time.

## Issues

Each repo/gem has its own set of issues on Github but a [waffle.io](https://waffle.io/sensu-plugins/sensu-plugins.github.io) has been created as well to more easily aggregate the issues across the entire project.  This should help, we shall see.  Ideas, thoughts, other opinions are always welcome.

Many of the gems already have several issues open, most pertaining to refactoring.  Now that they are organized into logical groups a good chunk of their functionality can be broken out into libraries.  Gems will be self-contained though.  They may have outside dependencies but unless absolutely necessary they will not share common code.  If this becomes an issue then a single gem may be created as a library or that functionality may be added to the sensu-plugin gem if deemed necessary.

## Feedback Requested

There are already a few issues open which the community at large has a say in.

[Rewrite disk checks to use the sys-filesystem gem](https://github.com/sensu-plugins/sensu-plugins-disk-checks/issues/2)

[Remove check-process.sh](https://github.com/sensu-plugins/sensu-plugins-process-checks/issues/1)

[Remove check-disk-health.sh](https://github.com/sensu-plugins/sensu-plugins-disk-checks/issues/6)

## Release Schedule

As of now due to the rapid development of the gems and the constant changing and updating of them, new gems will only be built once a day against the master branch of the repos.  The alpha tag is being used on these gems to let people now their current state but also due to the fact that large chunks of the code may change and it would be less than ideal to keep rapidly incrementing the versions.  As the code within the gems stabilizes and development slows, the alpha tags will give way to a beta tags and finally a real release.

Some of the larger or more complex gems will need considerably more work to achieve this goal but that was one of the major benefits to splitting them up.  With that said, now would be a great opportunity to request, or write yourself, any new functionality you need.  Non-Ruby has always been and will continue to be accepted, if I had the time I would love to write monitors in bf just because.
