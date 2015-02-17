---
layout: page
permalink: /development/gsoc15.html
---

---
title: "GSoC 2015 Ideas"
hide_toc: true
---

# GSoC 2015 Ideas

## Sensu Core
...

## Sensu Community Plugins

Creating a set of production grade gems from the [Sensu Community Plugins][2] is a huge task that will take considerable time, only with the continued effort of many people can this goal can be achieved.

The original community plugins repo has been split in smaller [repos][3], based upon application. This would mean all the Windows plugins, handlers, etc are in a repo named sensu-plugins-windows, the aws ones are in sensu-plugins-aws and so on.

This is only the first step towards completing the transformation, existing tooling will need to be improved and new tooling created for managing all the repos separately but also as a whole.  A maintainer should be able to issue a single command and have a template generated and installed in all repos, manually copying a file to every repo is so 2006, :D

### Task 1 General refactoring of community plugins code base

**Brief explanation:**

All the binaries in a repository should be broken down into libraries and any common code should be shared.  All new code should be written in Ruby and when possible existing code in other languages should be converted or its functionality should be folded into other code.

**Expected Results:**

* Minimal code duplication
* Standard Ruby coding practices
* Ephemeral data whenever needed, no traces left on a monitored system including temp files used to store state data
* Favor a pure ruby method, over a arch specific method even at the sacrifice of code complexity ie sys-filesystem gem vs `df`
* **Note** Not every repository needs to be complete, a list of high priority repos or ones of particular interest will be mutually determined

**Why Work On This:**

This would be a great project for someone who wants to improve their Ruby skills or learn about using various Open Source api's and how to integrate with them.  Much of the code is already written so the ability to examine functional code in various styles could be very beneficial.

**Knowledge prerequisite:**

* general concepts of monitoring or willingness to learn them
* general understanding of how to define, generate, and handle exit codes and what they mean within a monitoring environment
* must believe in and understand treating infrastructure as code, ephemeral data, and why this is necessary in a cloud environment

**Skill level:**

* beginner/medium, someone with an established track record of rapid learning will do fine

**Mentor:**

[Matt Jones](https://github.com/mattyjones) or [Artem Chernikov](https://github.com/kalabiyau)

### Task 2 Automated testing framework built around Travis using standard Ruby methods, practices, and tools

**Brief explanation:**

In order to be considered production grade test coverage needs to be fairly high and not everyone has the time or ability to write tests. A framework should be designed and built to automate the process of writing and executing tests.  There is a fair amount of latitude in how this is accomplished as minimal work has been done on this.

**Expected Results:**

We expect to have the foundation for a set of tools written in Ruby which will:

* Improve the existing set of development tools including [GIR][1] which is currently able to bootstrap a plugin development environment including gem and repo creation.
* Create an automated testing framework which will allow us to run a set of tests within virtual machines and report back the status of that process

**Why Work On This:**

This would be a great project for someone who wants to improve their Ruby skills and learn more about tool writing and writing automated test suites.  This is a ground up project so you would have the ability to contribute in a major way including helping to select the test packages, and work on the design of the tooling to help facilitate its use.

**Knowledge prerequisite:**

* general understanding of various testing tools such as rspec, rubocop, and serverspec
* basic understanding of TravisCI, Vagrant and RVM would be helpful but are not necessary
* basic understanding of Rake
* basic understanding of current infrastructure automation and tooling
* must believe in and understand treating infrastructure as code, ephemeral data, and why this is necessary in a cloud environment

**Skill Level:**

* medium

**Mentor:**

[Matt Jones](https://github.com/mattyjones) or [Artem Chernikov](https://github.com/kalabiyau)

### Task 3 Integrate Github, Rubygems, and other existing Services into the project [site][3] to give users a simple comprehensive directory of all monitors, handlers, and tools.

**Brief explanation:**

With the split of the community repo in ~150 separate repos, user may have a hard time finding a particular monitor or know that a monitor or handler for a service already exists.  There should be a directory we can point them to that will offer the functionality in a clean manner.  The directory should be generated automatically upon the release of a new gem, github tag, or repo.

**Expected Results:**

We would like a solid design and poc of the code and tools necessary to build the directory. It need not be complete but substantial progress should have been made and it should be in a poc state with complete functionality.

**Why Work On This:**

Not much has been done on this front yet so the student would in effect have free rein with the design as long as it meets the functional requirements and the code is clean modular and stable.  This would include the ability to design the layout, pick the methods to gather the required data and select the best language for the project.

Guidance is available on these topics as well as examples of the types of functionality and style we are looking for.

**Knowledge prerequisite:**

* general understanding of web application design
* general knowledge of web site template engines, any would be fine but the site currently uses Jekyll/Liquid
* good working knowledge of standard web languages such as html, css, js
* basic understanding of the necessary api's including Github, TravisCI, and RubyGems
* basic understanding of current infrastructure automation and tooling
* must believe in and understand treating infrastructure as code, ephemeral data, and why this is necessary in a cloud environment

**Skill Level:**

* medium/advanced

**Mentor:**

[Matt Jones](https://github.com/mattyjones) or [Artem Chernikov](https://github.com/kalabiyau)


[1]: https://github.com/sensu-plugins/GIR
[2]: https://github.com/sensu/sensu-community-plugins
[3]: https://github.com/sensu-plugins
