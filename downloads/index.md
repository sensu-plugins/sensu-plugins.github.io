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

| Gem                       | Current Version        | Gem Release Date    | Changelog |
| ------------------------- |:----------------------:| :--------------:| --------- |
| sensu-plugins-datadog     | [0.0.1.alpha.1](https://rubygems.org/gems/sensu-plugins-datadog)          | 01.29.2015      |  [here](https://github.com/sensu-plugins/sensu-plugins-datadog/blob/master/CHANGELOG.md#010-alpha1)         |
| sensu-plugins-process-checks  | 0.0.1.alpha.1          |                 |  [here](https://github.com/sensu-plugins/sensu-plugins-process-checks/blob/master/CHANGELOG.md#010-alpha1)         |
| sensu-plugins-disk-checks    | 0.0.1.alpha.1          |                 |  [here](https://github.com/sensu-plugins/sensu-plugins-disk-checks/blob/master/CHANGELOG.md#010-alpha1)         |

## Past Releases
