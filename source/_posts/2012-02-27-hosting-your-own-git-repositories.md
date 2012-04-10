---
layout: post
title: "Hosting Your Own Git Repositories"
date: 2012-02-27
comments: true
categories: [Git,Linux,Unix,SSH,Subversion]
description: Learning how to host your own Git repositories in this post.
---
I was using [Subversion](http://subversion.apache.org/) as software versioning and revision control system with my previous company. Hosting repositories with Subversion is not easy, and it is a centralized system where you can't have your own local commits; and mergings within branches to trunk always a nightmare for me.

I am happy to get to know about Git. [Git](http://git-scm.com/) is a free, open source and well developed source control management system developed by [Linus Torvalds](http://en.wikipedia.org/wiki/Linus_Torvalds), initially for [Linux kernel](http://kernel.org/) development.

Hosting with Git is easy, and it is a distributed version control system where you can have your codes committed to local or remotes. Git copy all of the data containing branches, tags and stored locally in client's system in order to switch between branches in seconds. With Git, you can work offline, by committing your codes locally and push to the remotes whenever you have internet connections.

## Requirements

- Linux or Unix based system
- Git to be installed on both server and client
- SSH access to the server

## Git on Server

SSH to the server, create the repository and create a bare Git repository.

{% codeblock %}
$ mkdir test.git
$ cd test.git
$ git --bare init
{% endcodeblock %}

That is all for the server side.

## Git on Client

Open up Terminal, create a working directory, create an empty Git repository.

{% codeblock %}
$ mkdir test
$ cd test
$ git init
{% endcodeblock %}

We have created an empty Git repository. We will now add a file and commit the changes.

{% codeblock %}
$ touch README
$ git add README
$ git commit -a -m 'first commit'
{% endcodeblock %}

We have committed the changes. We will now setup the remote server and push to the server.

{% codeblock %}
$ git remote add origin git@server.com:test.git
$ git push origin master
{% endcodeblock %}

That is all for the first commit. Each and every time you want to push the changes to remotes, you can just do `git push`

## Conclusion

Code versioning makes our life easy! Try to start everything with `git init` today!