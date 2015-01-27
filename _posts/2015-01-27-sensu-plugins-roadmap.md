---
layout: post
title:  Sensu Plugins Roadmap
author: Matt Jones
date:   2015-01-27 03:20:18
categories: issue
---

[Issue #847](https://github.com/sensu/sensu-community-plugins/issues/847)

## Abstract
Packaging and versioning of the plugins is something I know a lot of people want and for good reason.  I would like to purpose a thought and see how people feel about it. In a nutshell I would like to split the community-plugins repo in smaller repos, based upon application.  This would mean all the Windows plugins, handlers, etc would go into a repo named **sensu-plugins-windows**, the aws ones would go to **sensu-plugins-aws** and so one. Some projects already do this to some extent, specifically Hubot, and it presents many advantages.

## Pros
* Application groups are easier to package and version than a monolithic repository
* Plugin groups could be installed by an automation tool or Sensu itself with ease and be dependent upon only those checks currently running
* There would be no need to bump the entire plugins repo for a small change to a single plugin
* A user could pin separate gem versions depending on their environment

## Cons
* More overhead concerning dependency management
* More jobs to create and manage
* Plugin groups may not work for everyone


For those that want things the way they are we will create quarterly meta-gem releases of all the various gems, and these can be considered stable, whereas the individual gems could be considered production grade but active and the meta-gem would get built from each of these. This paves the way for company's to create specific gemsets for only the software they run. For example a lamp stack meta-gem would consist of core(system), mysql, and apache.

Dependency management could be somewhat solved over time as the community builds custom meta sets and such that all rely on a single dependency version, as they pin their version and run the included integration tests, if they pass then they could submit a PR back and we could bump the dependency for that specific gem.

## Proposed Timeframe

+ February (Creation)
+ Split all repos
+ Create gems for each repo as they currently stand

+ March - April (Transition Period)
+ Maintain both architectures
+ Accept pull requests from **sensu-community-plugins** repo and new repos
+ Create build schedule and pipeline for new gems

+ May (Start cutover)
+ Stop accepting PR's and issues for **sensu-community-plugins** repo for new functionality (bugs and security fixes still allowed)
+ Maintain desired build schedule for all new gems

+ June (End cutover)
+ Freeze **sensu-community-plugins** repo and stop accepting all PR's and Issues
+ Maintain desired build schedule for all new gems
+ Create first unstable release of meta-gem package
