---
layout: page
title: About Us
permalink: /about/
---

## Community plugins, extensions, and handlers

This project contains  example plugins and handlers for Sensu. Most of them are implemented in Ruby and use the `sensu-plugin` framework (a small gem); some also depend on additional gems (e.g. `mysql`). Some are shell scripts! All languages are welcome.

In the future, some sort of browsing/metadata/installation system may be implemented. For now, just clone the various repositories, take a look around, and copy the plugins you want to use.

## Production usage

Linters currently run against Ruby 2.0 and 2.1 and RSpec3 tests are being run against 1.9.3, 2.0, and 2.1.  There are no plans to support prior versions of Ruby, if you have no access to these versions please use the embedded Ruby that is installed with Sensu.  

Gems will be built against all current versions of Ruby and one EOL Ruby, currently 1.9.3, will be actively supported.
Because of the nature of these repositories:

  * little test coverage
  * specific and exotic software being checked
  * no versioning system for plugins

at this time is not recommended that you use master for your production instances.  Better pick something which works for you and lock it via `:ref` in your `chef || puppet || ansible || bash script` you name it.

If you have installed Sensu using the omnibus package it will use an embedded version of ruby, but the ruby plugins here will use the system one. If you want to use the embedded ruby, which has the `sensu-plugin` gem installed as well, you can set `EMBEDDED_RUBY=true` in `/etc/default/sensu` and restart the Sensu services. This will put the embedded ruby first in the $PATH for commands run by the Sensu services.
