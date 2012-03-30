---
layout: post
title: "Easy Deployment with GitHub"
comments: true
categories: [Git,GitHub]
description: Deploying applications to development, staging and production never been so easy with GitHub Post-Receive Deployment Hook script!
---
I wrote a [GitHub Post-Receive Deployment Hook](https://github.com/kwangchin/GitHubHook) to deploy applications to staging and production automatically.

Follow the instruction in the `README` to setup your `stage` and `prod` branches.

<!-- more -->

## Making Your Life Easier

You are on `master` branch by default, and this is the development branch for all your commits and pushes.

Next you might want to have `stage` branch for testing purposes.

### Creating `stage` branch

{% codeblock %}
$ git branch stage
{% endcodeblock %}

### Pushing `stage` branch

{% codeblock %}
$ git push origin stage
{% endcodeblock %}

You have a `prod` branch for the production site.

### Creating `prod` branch

{% codeblock %}
$ git branch prod
{% endcodeblock %}

### Pushing `prod` branch

{% codeblock %}
$ git push origin prod
{% endcodeblock %}

## Results

I have updated a tutorial of my previous post [Creating Zend Framework Project from Scratch](http://kcblog.net/2012/03/21/creating-zend-framework-project-from-scratch.html) to have branches and versions, and each of them are deployed to the following addresses:

* `master` - [http://zf-tutorial.kcblog.net/dev/](http://zf-tutorial.kcblog.net/dev/)
* `stage` - [http://zf-tutorial.kcblog.net/stage/](http://zf-tutorial.kcblog.net/stage/)
* `prod` - [http://zf-tutorial.kcblog.net/prod/](http://zf-tutorial.kcblog.net/prod/)

## Conclusion

We are trying to make developers life easier. Kindly fork this on GitHub and submit your pull requests to help us.