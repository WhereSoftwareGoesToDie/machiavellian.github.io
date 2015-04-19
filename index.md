---
layout: page
title: Machiavelli
---
Machiavelli is a Ruby on Rails application for taking any arbitrarily defined data source, and feeding it into any arbitrarily defined graphing library.

Base Principles

> 1) Show Machiavelli how to access a list of things, and how to get information about a specific thing from that list. That's it.
>
> 2) At any time, you should be able to copy the URL of a specific Machiavelli page, open it somewhere else, and get the exact same view of the data.
>
> 3) Any sufficiently configured Machiavelli instance should be able to be used to visualize any metric from the configured backends without any interaction at the server level.


## Installation

Ensure Ruby 1.9.3 or higher, and Redis are installed locally. Then, clone and execute like any standard Ruby on Rails application:

    git clone https://github.com/machiavellian/machiavelli.git
    bundle install
    bundle exec rails server

The application can then be viewed at `http://localhost:3000`


## More information

We have detailed more about the internals of machiavelli, specifically regarding [components](components.html), and [settings](settings.html). Check the sidebar for all listings
