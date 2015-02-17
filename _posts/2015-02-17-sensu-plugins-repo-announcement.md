---
layout: post
title:  New Sensu Plugins Repos
author: Matt Jones
date:   2015-02-17 10:56:23
---

The split of the community-plugins repo is complete.  The new repos can be found [here][1].

The short of it is that no functionality has changed and gems have not been created for each repo yet.  There are however several breaking changes that need to be accounted for.

All plugins in the new repos now follow a standard naming scheme of being prefixed by either **handler**, **check**, **metrics**, **extension**, or **mutator** depending on their primary function.  This was done to make things easier to deal with as all binaries now live in */bin*, regardless of function.  This means that the ec2 handler and the ec2/elb checks are included in the same repo and will be built into a single gem.  If you want to monitor aws you only need install the aws gem or clone the aws repo

There is an ongoing refactor of all amazon checks to not allow keys, passwords, or tokens to be passed as commandline arguments.  If you have thoughts on this or would like to offer insight please take a look [here][2]

When looking for a check, please don't assume the repo will be the same as the directory name in the community plugins repo.  In many cases they will be nearly identical but some changes have been made for example:

check-fs-writeable used to be in /disk but has now been moved to the [filesystem-checks][3] repo.

Some checks that didn't fit anywhere were broken off into their own repos as well.

While the community-plugins repo is still considered authoritative, these new repos are going to be our future.  The community-plugins repo will never go away but at some point later this year, most likely mid-summer, it will be archived and we will no longer accept PR's or Issues for it.

When the new repos reach more stable states, within the next few months, the corresponding checks in the community-plugins repo will be frozen for all new features.  At this point when submitting a feature PR you may be asked to pull the new repo containing the check and submit it there.  Bug fixes will still continue to be accepted for all plugins until the actual hard cutover.  

Release tags will start to appear for many of these repos fairly quickly as well, most will be flagged as prerelease to account for anything that may still break as things are shifted and moved but rest assured [semantic][4] versioning will be strictly followed and once the github prerelease flag or the alpha tag from the gem is removed, no breaking changes will occur.

There is a still a lot of work needed to get these repos to stable, production grade state but rest assured they will get there and we will all be able to sleep a little better at night.

[1]: https://github.com/sensu-plugins
[2]: https://github.com/sensu-plugins/sensu-plugins-aws/issues/2
[3]: https://github.com/sensu-plugins/sensu-plugins-filesystem-checks
