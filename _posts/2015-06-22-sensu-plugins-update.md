---
layout: post
title:  Plugin Directory, Trello Board, and A New Address
author: Matt Jones
date:   2015-06-22 11:20:18
categories: issue
---

### Pull Requests

The pull requests are coming in fast and furious it seems.  I apologize if we took a while to get to yours, we are a small team and there is still much work to be done.  In the future, we are trying to act upon PR's within 48 hours unless they are of a critical nature in which case we will get to it as soon as possible.

When it comes to Pull Requests, we have a few requests for the community that will make our lives much simpler and get your code merged in much faster.

* When submitting a PR please update the CHANGELOG in the repo following the [developer guidelines][1].  This will make for a much more accurate and complete changelog.

* Concerning versioning, there are three levels of versioning for each release. MAJOR.MINOR.PATCH.  The patch version is for any non-breaking changes to existing scripts or the addition of minor functionality to existing scripts.  The minor version is for the addition of any new scripts. Even though this is generally non-breaking, it is a major change to the gem and should be indicated as such.  The major version should only be bumped by a core contributor. This is for major breaking or non-breaking changes that affect widespread functionality. If anyone has any questions or concerns about this, we are all ears and open for debate.

### Project Site

 The site has been moved over to a real address now [http://sensu-plugins.io][2], in the future the site will also be fully SSL enabled.  The old site will redirect here so nothing is broken but the domain has finally been changed.  At some point towards the end of the year the site will be getting a major facelift, details on that will be coming at soon hopefully.


### Trello

There is a project [Trello board][3] that is open to the public for those that wish to see what we are spending our collective time on.  It will remain fairly up-to-date and will serve as the primary way that we communicate to the community about large projects, features, and changes.  please feel free to comment on any cards, these are your plugins as well and everyone has a say.

### July 6 Code Freeze 

This is still happening.  On this date we will no longer accept any new pull requests against the original community plugins repo.  All new features, scripts, and functionality will need to be pulled against a repo in the new org.  Many of you have already been doing this so this should be no more than a gentle reminder.

Security and bug fixes will still continue to be accepted for at least 90 days.  All open issues in the old repo will either be closed, resolved, or moved to the new repo and like pull requests issues will no longer be actively maintained on that repo.

I stress again that at no point will the original repo ever be removed, there is far to much history and knowledge there, it will simply be frozen and archived in place.

### Plugin Directory

Many people have expressed concern about not being able to find a plugin or to know what plugins are even available. A quick and dirty [directory][4] has been created to solve this.  This should only be considered a beta feature but rest assured it is stable and will always be current.  When the new site drops, this will be a significant part and will have a proper UI as well as be able to display the latest releases and additional metadata.

### Future Plans 

There are many things still to come such as detailed project documentation, documentation coverage on the checks, tests for the checks, the new site, and easier ways to communicate and collaborate with the plugins team and the community as a whole.  Stay tuned, its going to be a busy year.

[1]: https://github.com/sensu-plugins/documentation/blob/master/development/developer_guidelines.md
[2]: http://sensu-plugins.io
[3]: https://trello.com/b/QjkJ8CS3/sensu-community-plugins
[4]: http://sensu-plugins.io/plugins/

