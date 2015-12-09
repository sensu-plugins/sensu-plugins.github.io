---
layout: page
title: About
permalink: /about/
---
This project contains plugins, handlers, mutators and other code to maximize the effective use of [Sensu](https://sensuapp.org/) in various types of auto-scaling and traditional environments. 
Most of the plugins are implemented in [Ruby](https://www.ruby-lang.org/en/) and use the `sensu-plugin` framework; some also depend on additional gems (e.g. `mysql`); some are shell scripts.

### Production usage

Linters currently run against Ruby 2.0, 2.1, 2.2 and tests are being run against 1.9.3, 2.0, 2.1, 2.2 if they are written. 
There are no plans to support prior versions of Ruby, if you have no access to these versions please use the embedded Ruby 
that is installed with Sensu, directions on this can be found in the [Sensu FAQ](http://sensuapp.org/docs/0.12/faq) or below.

Gems will be built against all current versions of Ruby and one EOL Ruby, currently 1.9.3, will be actively supported.

<div class="alert alert-warning" role="alert">
<b>Ruby 1.9.3 (EOL)</b>: Linting is not done against it, and 1.9.3 will be supported where possible till Feb 2016 which is 
one year after EOL and 2 years after EOL was announced.
</div>

Because of the nature of these repositories:

  * little test coverage
  * specific and exotic software being checked

at this time is not recommended that you use master for your production instances.  Better pick something which works for you and lock it in your cookbook, manifest, or bash script.

### Which ruby?

If you have installed Sensu using the omnibus package it will use an embedded version of ruby, but the ruby plugins here will use the system one. 

If you want to use the embedded ruby, which has the `sensu-plugin` gem installed as well, you can set `EMBEDDED_RUBY=true` in `/etc/default/sensu` and restart the Sensu services. This will put the embedded ruby first in the $PATH for commands run by the Sensu services.
