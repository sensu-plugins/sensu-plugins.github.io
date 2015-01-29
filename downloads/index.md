---
layout: page
title: Downloads
permalink: /downloads/
---

All Sensu-Plugins gems are cryptographically signed. To be sure the gem you install hasn’t been tampered with:

Add the public key (if you haven’t already) as a trusted certificate

{% highlight bash %}
gem cert --add <(curl -Ls https://raw.githubusercontent.com/sensu-plugins/sensu-plugins.github.io/master/certs/sensu-plugins.pem)
gem install <gem> -P MediumSecurity
{% endhighlight %}

You can also download the key from */certs/* within each repository.

## Current Releases

| Gem                       | Current Version        | Release Date    | Changelog |
| ------------------------- |:----------------------:| :--------------:| --------- |
| sensu-plugins-handlers    | 0.0.1.alpha.1          |                 |           |
| sensu-plugins-extensions  | 0.0.1.alpha.1          |                 |           |
| sensu-plugins-mutators    | 0.0.1.alpha.1          |                 |           |

## Past Releases
