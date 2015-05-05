---
layout: post
title:  Sensu Plugins Community Repo Update
author: Matt Jones
date:   2015-05-05 02:20:18
categories: issue
---

First off I would like to say thanks to the other contributors who have been doing considerable work on the plugins, this was not and continues to not be a one man show. @analytically @rmc3 and @tas50

## Gem Status

According to RubyGems, we are fast approaching 8000 downloads across 52 gems!  To give an overall idea of the current state of the organization, we have a total of 154 plugins repos and that number grows by at least 1 every week.

**On July 6th, we will be freezing the original community plugins repo.**  This is only a soft freeze and allows the team time to ensure everything is migrated.  On this date we will no longer accept new plugins or features to existing plugins at this location, all new code will need to be pulled against the new codebase.  Security fixes and bug fixes will continue to be accepted for at least 60 days, as will any issues related to these topics.

The procedure for PR's will remain nearly identical, only a small change will be needed.  If your code already has a home, or where you think it should live then submit a PR against that repo.  If you are unsure of where it should go, you can either reach out via email or Twitter or submit a PR against the [feature-requests](https://goo.gl/53yu2I) repo.

At this time I expect all plugins to be built into stable gems by the above date.  We currently have a CI/CD pipeline setup using Codeship and it appears to be working great and will go a long way towards ensuring stability.  For those interested in this pipeline [Tom Servo](https://github.com/sensu-plugins/tom_servo) can help.

I stress, at no point will the community plugins repo be removed.  After the team **and the community** are happy with the state of the new organization, the community plugins repo will be archived and any open issues of importance will be migrated.

We have also done a first pass at plugins specific documentation.  Development guidelines, including testing, have been updated and a basic set of installation instructions have also been created.  A lot more documentation needs to be written as well as an easier way to retrieve it.

Along with metadata, each gem now has a post-install message telling users how to use the embedded Ruby which is the recommended way to use the plugins.  Many other versions are supported but the less we have to maintain on our systems the better we all sleep at night ;)

The final major piece to drop will be a new site that incorporates the documentation and a searchable plugin directory.  This will go along way towards helping people find plugins that they can use.

Please feel free to reach out however you want with any suggestions, comments, or drunken ramblings about my beloved Red Sox and their lack of 27 rings. ;)

May The Source Be With You
