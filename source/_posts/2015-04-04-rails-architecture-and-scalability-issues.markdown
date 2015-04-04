---
layout: post
title: "Rails Architecture and Scalability"
date: 2015-04-04 19:17:12 +0300
comments: true
categories: [ruby, rails, architecture]
---

{% img right  /images/blog/ruby.png %}
Everybody know when this _"Rails doesn't scale"_ has been begun:

- **2009** [Twitter message queue back-end moved from Ruby to Scala](http://www.artima.com/scalazine/articles/twitter_on_scala.html)
- **2011** [Twitter Search is Now 3x Faster](https://blog.twitter.com/2011/twitter-search-now-3x-faster)

> Panic, we must not use **Ruby on Rails** because Twitter had scalability problems.

I'm a Java developer who love Ruby language, but don't write anything in Rails. Despite this I've decided to look into this famous _"Rails doesn't scale"_ statement deeper to understand the root cause of this problem.

How did I do this? Well, I [collected][my-GH] public available Ruby on Rails architecture and scalability case studies (videos of conference talks, reports and blog posts) and tried to extract the general patterns of architecture and scalability issues.

There are two type of scalability issues:

1. **Application performance** - when web application can't handle huge traffic
2. **Delivery velocity** - when it's become hard to make changes in big Rails application, run quick tests, deploy it and manage big team

_Note_: You are not another "twitter" to worry about scalability issues right from beginning  of the project (there are fewer web apps on the internet to get enough traffic to even care about scalability). Your goal is to push your product as quick as possible.
But, in the same time you'd like to use Rails (due to it's productivity) and make you application scalable (in all possible terms)

The most interesting that scalability is about architecture, databases, caching, event queues, disk IO.

## Monolith Rails application

## Rails Application Deployment bgi and

##

## Servers

## References
- [Does Ruby on Rails scale][link Does Ruby on Rails scale] it's very nice Quora discu
- [Collection of Ruby on Rails Architecture Case Studies][my-GH]

[link Does Ruby on Rails scale]: http://www.quora.com/Does-Ruby-on-Rails-scale
[my-GH]: https://github.com/halyph/architecture-case-study#ruby-on-rails-architecture-case-studies
