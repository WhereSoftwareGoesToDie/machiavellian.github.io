---
layout: page
title: Deployment

sidebar_link: true
---

Deployment of Machiavelli can be done in a number of ways

#The Anchor Way

Using a combination of [anchor/allah](https://github.com/anchor/allah), [mpalmer/giddyup](https://github.com/mpalmer/giddyup), nginx, unicorn and rails, you too can have your own daemonised Machiavelli instance. These will "just work" if you setup your server environment and use giddyup to `git push deploy_env`. 

# The Manual Way

Install all the things for a rails, unicorn and nginx instance, and use [the configurations](https://github.com/anchor/machiavelli/tree/master/sample_configs) we've prepared earlier. 

These are designed to help you out, but there are plenty of ServerFault resources should you get stuck with the server side. 
