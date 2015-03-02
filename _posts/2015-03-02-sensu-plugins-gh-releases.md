---
layout: post
title:  Sensu Plugins, Now With Github Releases
author: Matt Jones
date:   2015-03-02 10:04:18
categories: issue
---

It has been a long month since the split but I am happy to say all [sensu-plugins][1] repos now have github releases for those that want to pin, the list is at the bottom.  Though many of the repos are still in an alpha state, this does not mean they are unstable.  The alpha state simply denotes that breaking changes may still occur although that is most likely not going to happen very often.  Semantic versioning is in effect though so please pin away.

### Refactoring Galore

Several of the repo's including [raid-checks][2], [disk-checks][3], [aws][4], and [process-checks][5] are under heavy revision.  The checks are being rewritten to use pure ruby methods and gems instead of arch specific methods such as `df`.  While this may make sense for many people, the trade-off is platform dependence and in the long run we want to make all the plugins as platform independent as possible.

To that effect the [Windows repo][6] may also be receiving a lot of love shortly as well.

If you are using the new repos and notice the builds are failing or in error, please don't worry.  This is most likely due to rubocop complaining about lack of documentation or a dependency is puking.

### Gem Releases

The timeline for gem releases depends largely on the community.  All repos have a base gemspec and can be built.  You may need to add or tweak the dependencies though.  If you do build a gem and confirm that it works please submit a PR and we can merge it in, sign it,  and push the gem to Rubygems for everyone to use.  The current thinking is that the majority of gems will be built by the middle of April and Github releases will be updated.  The gem release and Github release will always be in sync, so v0.0.4 gem will be identical to 0.0.4 github tag.

The timeline for the freezing of the community-plugin repo is still a moving target but it will happen at some point this summer possibly the end June.  It all depends on adoption rate and progress of the new repos, but at some point the repo will be frozen to all feature/bug/security fixes.  It will not be removed, just archived in place for the spiders.


### Feature Requests, Issues, Bugs

I expect that by the end of April all feature requests and any additional functionality will need to be pulled against the new repos.  Security and bug fix PR's will continue to be accepted for some time.  This is done to both stabilize the community-plugins repo and to spur the continued development and adoption of the new repos.  The feature freeze will be done on a rolling schedule, as the new repo goes stable, denoted by the removal of the alpha tag or prerelease flag, the corresponding plugins in the community repo will be frozen.  Maintaining separate codebases is not easy nor is it wise.

Issues that are pending or open on the community repo will remain there and as the affected plugins are frozen a corresponding issue will be opened in the new repo with a link back to the original.

### Current Releases
```
Name                                Github Release  Gem Release
sensu-plugins.github.io
sensu-plugins-datadog               v0.0.1          0.0.1
sensu-plugins-process-checks        v0.0.1.alpha.3  0.0.1.alpha.2
sensu-plugins-disk-checks           v0.0.1.alpha.5  0.0.1.alpha.4
sensu-plugins-nginx                 v0.0.1          0.0.1
sensu-plugins-raid-checks           v0.0.1.alpha.2  0.0.1.alpha.2
sensu-plugins-aws                   v0.0.1.alpha.2  0.0.1.alpha.2
sensu-plugins-network-checks        v0.0.1.alpha.1
GIR
sensu-plugins-campfire              v0.0.1.alpha.1
sensu-plugins-hipchat               v0.0.1.alpha.1
sensu-plugins-pagerduty             v0.0.1.alpha.1
sensu-plugins-apache                v0.0.1.alpha.1
sensu-plugins-dhcp                  v0.0.1.alpha.1
sensu-plugins-docker                v0.0.1.alpha.1
sensu-plugins-dns                   v0.0.1.alpha.1
sensu-plugins-consul                v0.0.1.alpha.1
sensu-plugins-couchbase             v0.0.1.alpha.1
sensu-plugins-cassandra             v0.0.1.alpha.1
sensu-plugins-mesos                 v0.0.1.alpha.1
sensu-plugins-mongodb               v0.0.1.alpha.1
sensu-plugins-memcached             v0.0.1.alpha.1
sensu-plugins-mysql                 v0.0.1.alpha.1
sensu-plugins-lxc                   v0.0.1.alpha.1
sensu-plugins-java                  v0.0.1.alpha.1
sensu-plugins-kannel                v0.0.1.alpha.1
sensu-plugins-jenkins               v0.0.1.alpha.1
sensu-plugins-influxdb              v0.0.1.alpha.1
sensu-plugins-gpg                   v0.0.1.alpha.1
sensu-plugins-etcd                  v0.0.1.alpha.1
sensu-plugins-github                v0.0.2          0.0.2  
sensu-plugins-graphite              v0.0.1.alpha.1
sensu-plugins-ssl                   v0.0.1.alpha.1
sensu-plugins-redis                 v0.0.1.alpha.1
sensu-plugins-rabbitmq              v0.0.1.alpha.1
sensu-plugins-puma                  v0.0.1.alpha.1
sensu-plugins-windows               v0.0.1.alpha.1
sensu-plugins-youtube               v0.0.1.alpha.1
sensu-plugins-varnish               v0.0.1.alpha.1
sensu-plugins-uchiwa                v0.0.1.alpha.1
sensu-plugins-postgres              v0.0.1.alpha.1
sensu-plugins-postfix               v0.0.1.alpha.1
sensu-plugins-openstack             v0.0.1.alpha.1
sensu-plugins-monit                 v0.0.1.alpha.1
sensu-plugins-fluentd               v0.0.1          0.0.1
sensu-plugins-newrelic              v0.0.1.alpha.1
sensu-plugins-haproxy               v0.0.1.alpha.1
sensu-plugins-elasticsearch         v0.0.1.alpha.1
sensu-plugins-unicorn               v0.0.1.alpha.1
sensu-plugins-twilio                v0.0.1.alpha.1
sensu-plugins-twemproxy             v0.0.1.alpha.1
sensu-plugins-trafficserve   r      v0.0.1.alpha.1
sensu-plugins-telapi                v0.0.1.alpha.1
sensu-plugins-cpu-checks            v0.0.1.alpha.1
sensu-plugins-memory-checks         v0.0.1.alpha.1
sensu-plugins-syslog-ng             v0.0.1.alpha.1
sensu-plugins-supervisor            v0.0.1.alpha.1
sensu-plugins-springboot            v0.0.1.alpha.1
sensu-plugins-solr                  v0.0.1.alpha.1
sensu-plugins-snmp                  v0.0.1.alpha.1
sensu-plugins-sip                   v0.0.1.alpha.1
sensu-plugins-sftp                  v0.0.1.alpha.1
sensu-plugins-serverspec            v0.0.1.alpha.2
sensu-plugins-sensu                 v0.0.1.alpha.1
sensu-plugins-selinux               v0.0.1.alpha.1
sensu-plugins-rspec                 v0.0.1.alpha.1
sensu-plugins-riak                  v0.0.1.alpha.1
sensu-plugins-resque                v0.0.1.alpha.1
sensu-plugins-qmail                 v0.0.1.alpha.2
sensu-plugins-pingdom               v0.0.1.alpha.1
sensu-plugins-php-fpm               v0.0.1.alpha.1
sensu-plugins-percona               v0.0.1.alpha.1
sensu-plugins-pacemaker             v0.0.1.alpha.1
sensu-plugins-opsgenie              v0.0.1.alpha.1
sensu-plugins-openvpn               v0.0.1.alpha.1
sensu-plugins-openldap              v0.0.1.alpha.1
sensu-plugins-nbzget                v0.0.1.alpha.1
sensu-plugins-logs                  v0.0.1.alpha.1
sensu-plugins-ipmi                  v0.0.1.alpha.1
sensu-plugins-imap                  v0.0.1.alpha.1
sensu-plugins-icecast               v0.0.1.alpha.1
sensu-plugins-http                  v0.0.1.alpha.1
sensu-plugins-hbase                 v0.0.1.alpha.1
sensu-plugins-growthforecast        v0.0.1.alpha.1
sensu-plugins-greylog               v0.0.1.alpha.1
sensu-plugins-gluster               v0.0.1.alpha.1
sensu-plugins-ftp                   v0.0.1.alpha.1
sensu-plugins-filesystem-checks     v0.0.1.alpha.1
sensu-plugins-eye                   v0.0.1.alpha.1
sensu-plugins-erlang                v0.0.1.alpha.1
sensu-plugins-cucumber              v0.0.1.alpha.1
sensu-plugins-chef                  v0.0.1.alpha.1
sensu-plugins-tripwire              v0.0.1.alpha.1
sensu-plugins-ceph                  v0.0.1.alpha.1
sensu-plugins-boundary              v0.0.1.alpha.1
sensu-plugins-beanstalk             v0.0.1.alpha.1
sensu-plugins-ansible               v0.0.1.alpha.1
sensu-plugins-officehours           v0.0.1.alpha.1
sensu-plugins-victorops             v0.0.1.alpha.1
sensu-plugins-twitter               v0.0.1.alpha.1
sensu-plugins-slack                 v0.0.1.alpha.1
sensu-plugins-mailer                v0.0.1.alpha.1
sensu-plugins-logstash              v0.0.1.alpha.1
sensu-plugins-irc                   v0.0.1.alpha.1
sensu-plugins-ponymailer            v0.0.1.alpha.1
sensu-plugins-splunk                v0.0.1.alpha.1
sensu-plugins-gtalk                 v0.0.1.alpha.1
sensu-plugins-dashing               v0.0.1.alpha.1
sensu-plugins-clockworksms          v0.0.1.alpha.1
sensu-plugins-sentry                v0.0.1.alpha.1
sensu-plugins-gelf                  v0.0.1.alpha.1
sensu-plugins-hubot                 v0.0.1.alpha.1
sensu-plugins-flowdock              v0.0.1.alpha.1
sensu-plugins-talker                v0.0.1.alpha.1
sensu-plugins-xmpp                  v0.0.1.alpha.1
sensu-plugins-eep                   v0.0.1.alpha.1
sensu-plugins-google-spreadsheet    v0.0.1.alpha.1
sensu-plugins-imkayac               v0.0.1.alpha.1
sensu-plugins-pushover              v0.0.1.alpha.2
sensu-plugins-messagemedia          v0.0.1.alpha.1
sensu-plugins-request-tracker       v0.0.1.alpha.1
sensu-plugins-zendesk               v0.0.1.alpha.1
sensu-plugins-statuspage            v0.0.1.alpha.1
sensu-plugins-tempodb               v0.0.1.alpha.1
sensu-plugins-skyline               v0.0.1.alpha.1
sensu-plugins-opentsdb              v0.0.1.alpha.1
sensu-plugins-mackerel              v0.0.1.alpha.1
sensu-plugins-librato               v0.0.1.alpha.1
sensu-plugins-geckoboard            v0.0.1.alpha.1
sensu-plugins-statsd                v0.0.1.alpha.1
sensu-plugins-flapjack              v0.0.1.alpha.1
sensu-plugins-system-profile        v0.0.1.alpha.1
sensu-plugins-redact                v0.0.1.alpha.1
sensu-plugins-execute               v0.0.1.alpha.1
sensu-plugins-time-to-live          v0.0.1.alpha.1
sensu-plugins-load-checks           v0.0.1.alpha.1
sensu-plugins-nvidia                v0.0.1.alpha.1
sensu-plugins-bluepill              v0.0.1.alpha.1
sensu-plugins-conntrack             v0.0.1.alpha.1
sensu-plugins-entropy-checks        v0.0.1.alpha.1
sensu-plugins-io-checks             v0.0.1.alpha.1
sensu-plugins-ntp                   v0.0.1.alpha.1
sensu-plugins-uptime-checks         v0.0.1.alpha.1
sensu-plugins-cgroups               v0.0.1.alpha.1
sensu-plugins-vmstats               v0.0.1.alpha.1
sensu-plugins-hardware              v0.0.1.alpha.1
sensu-plugins-environmental-checks  v0.0.1.alpha.1
```

[1]: https://github.com/sensu-plugins
[2]: https://github.com/sensu-plugins/sensu-plugins-raid-checks
[3]: https://github.com/sensu-plugins/sensu-plugins-disk-checks
[4]: https://github.com/sensu-plugins/sensu-plugins-aws
[5]: https://github.com/sensu-plugins/sensu-plugins-process-checks
[6]: https://github.com/sensu-plugins/sensu-plugins-windows
