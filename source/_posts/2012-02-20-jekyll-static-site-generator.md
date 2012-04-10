---
layout: post
title: "Jekyll, the Static Site Generator"
comments: true
categories: [Jekyll]
description: Jekyll is being introduced and what are the pros and cons about static site generators in this post.
---
[Jekyll](https://github.com/mojombo/jekyll/) is a static site generator written in ruby by [Tom Preston Werner](http://tom.preston-werner.com/). It runs through [Markdown](http://daringfireball.net/projects/markdown/) or [Textile](http://www.textism.com/tools/textile/), and with [Liquid Templating System](http://liquidmarkup.org/), turns into static website to be served by any web server. Jekyll is also the tool used to produce [GitHub Pages](http://pages.github.com/).

## Static Site Generator

### What is it?

A Static Site Generator reads through configs, markups, templates and generates static HTML website as output. These generated static HTML website is then served by your web server. Unlike the old school blogs, you can now customize your blogs with ease.

### Advantages

* Code Versioning - Better control with GitHub as the platform, to be able to revert changes or recover from disaster easily
* Performance - Better performance with no server scriptings; less cpu / memory usage to serve your site
* Portable - Easier to relocate as there is no need to backup the database and configurations
* Secure - Better security without PHP / ASP server scriptings and database layer for exploits
* Web Hosting - Cheap or web hosting at no cost and don't have to worry about server scripting languages

### Disadvantages

* No Local Stuffs - No local comments, pingbacks and contact form with dynamic codes
* No Backend - No backend to update changes and you probably need a computer to update your blog
* Not Easy To Use - Not for people without programming exposure