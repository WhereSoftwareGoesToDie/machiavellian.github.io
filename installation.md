---
layout: page
title: Installation

sidebar_link: true
---

Prior requirements: 
 * installation of ruby 1.9.3 or ruby 2.1.2 (see travis.yml for current tested versions)
 * `redis-server`

For development, `libqt4-dev` for capybara, and a dev version of ruby for pry-debugger

Then, clone and execute like any standard Ruby on Rails application:

    git clone https://github.com/machiavellian/machiavelli.git
    bundle install
    bundle exec rails server

The application can then be viewed at `http://localhost:3000`
