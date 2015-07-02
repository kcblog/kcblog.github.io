---
layout: post
title: "Starting Up Yii Project with Git"
comments: true
categories: [Yii,Git]
description: Start up your Yii Project with Git as version control system.
---
[Yii Framework](http://www.yiiframework.com/about/) is a high-performance PHP framework best for developing Web 2.0 applications.

## Requirements

- Git version control system
- Yii framework v1.1.10 as of today
- Web server with PHP 5.1 or higher (optional)

## Checkout Yii Framework

First you need to checkout the framework from Yii repository. Checking out with Git allows you to have collaborations, updates and fast switching of versions. You can skip this step if you have Yii ready in your machine.

{% highlight %}
$ git clone https://github.com/yiisoft/yii.git
Cloning into yii...
remote: Counting objects: 41897, done.
remote: Compressing objects: 100% (9615/9615), done.
remote: Total 41897 (delta 31528), reused 41775 (delta 31415)
Receiving objects: 100% (41897/41897), 15.87 MiB | 138 KiB/s, done.
Resolving deltas: 100% (31528/31528), done.
{% endhighlight %}

Quick switching into the newly checkout Yii framework.

{% highlight %}
$ cd yii
{% endhighlight %}

You can check the current version of Yii framework by issuing the commands below.

{% highlight %}
$ php -r "include('framework/YiiBase.php'); echo YiiBase::getVersion() . PHP_EOL;"
1.1.11-dev
{% endhighlight %}

Yii versions are in tags and you can have a view of all the versions with `git tag`.

{% highlight %}
$ git tag
1.0.0
1.0.1
1.0.10
1.0.11
1.0.12
1.0.2
1.0.3
1.0.4
1.0.5
1.0.6
1.0.7
1.0.8
1.0.9
1.0a
1.0b
1.0rc
1.1.0
1.1.1
1.1.10
1.1.2
1.1.3
1.1.4
1.1.5
1.1.6
1.1.7
1.1.8
1.1.9
1.1a
1.1b
1.1rc
{% endhighlight %}

Now we are going to switch the version to 1.1.10 with `git checkout`, which is the latest stable version.

{% highlight %}
$ git checkout 1.1.10
Note: checking out '1.1.10'.

You are in 'detached HEAD' state. You can look around, make experimental
changes and commit them, and you can discard any commits you make in this
state without impacting any branches by performing another checkout.

If you want to create a new branch to retain commits you create, you may
do so (now or later) by using -b with the checkout command again. Example:

  git checkout -b new_branch_name

HEAD is now at 25b0d9e... 1.1.10 release.
{% endhighlight %}

We now have the Yii framework v1.1.10 and we can double check again.

{% highlight %}
$ php -r "include('framework/YiiBase.php'); echo YiiBase::getVersion() . PHP_EOL;"
1.1.10
{% endhighlight %}

Congratulations! Do not forget to go back to parent directory.

{% highlight %}
$ cd ..
{% endhighlight %}

## Create Your Yii Project

With Yii console script, it is pretty easy to create your Yii projects.

{% highlight %}
$ yii/framework/yiic webapp project
Create a Web application under '/var/www/project'? [yes|no] y
...
...
...
Your application has been created successfully under /var/www/project.
$ cd project
$ ls -a
.		..		assets		css		images		index-test.php	index.php	protected	themes
{% endhighlight %}

Your project is now created! We will have to initialize Git repository.

{% highlight %}
$ git init
Initialized empty Git repository in /var/www/project/.git/
$ ls -a
.		..		.git		assets		css		images		index-test.php	index.php	protected	themes
{% endhighlight %}

There are some empty directories in your newly created project and we will need to add .gitignore into those directories.

{% highlight %}
$ find . -type d -empty -exec touch {}/.gitignore \;
{% endhighlight %}

We can now add the files into Git repository and commit for the first time.

{% highlight %}
$ git add *
$ git commit -a -m 'first commit'
[master (root-commit) 6c0b79b] first commit
 36 files changed, 1561 insertions(+), 0 deletions(-)
 create mode 100644 assets/.gitignore
 create mode 100644 css/bg.gif
 create mode 100644 css/form.css
 create mode 100644 css/ie.css
 create mode 100644 css/main.css
 create mode 100644 css/print.css
 create mode 100644 css/screen.css
 create mode 100644 images/.gitignore
 create mode 100644 index-test.php
 create mode 100644 index.php
 create mode 100644 protected/.htaccess
 create mode 100644 protected/commands/shell/.gitignore
 create mode 100644 protected/components/Controller.php
 create mode 100644 protected/components/UserIdentity.php
 create mode 100644 protected/config/console.php
 create mode 100644 protected/config/main.php
 create mode 100644 protected/config/test.php
 create mode 100644 protected/controllers/SiteController.php
 create mode 100644 protected/data/schema.mysql.sql
 create mode 100644 protected/data/schema.sqlite.sql
 create mode 100755 protected/data/testdrive.db
 create mode 100644 protected/extensions/.gitignore
 create mode 100644 protected/messages/.gitignore
 create mode 100644 protected/migrations/.gitignore
 create mode 100644 protected/models/ContactForm.php
 create mode 100644 protected/models/LoginForm.php
 create mode 100644 protected/runtime/.gitignore
 create mode 100644 protected/tests/WebTestCase.php
 create mode 100644 protected/tests/bootstrap.php
 create mode 100644 protected/tests/fixtures/.gitignore
 create mode 100644 protected/tests/functional/SiteTest.php
 create mode 100644 protected/tests/phpunit.xml
 create mode 100644 protected/tests/report/.gitignore
 create mode 100644 protected/tests/unit/.gitignore
 create mode 100644 protected/views/layouts/column1.php
 create mode 100644 protected/views/layouts/column2.php
 create mode 100644 protected/views/layouts/main.php
 create mode 100644 protected/views/site/contact.php
 create mode 100644 protected/views/site/error.php
 create mode 100644 protected/views/site/index.php
 create mode 100644 protected/views/site/login.php
 create mode 100644 protected/views/site/pages/about.php
 create mode 100755 protected/yiic
 create mode 100644 protected/yiic.bat
 create mode 100644 protected/yiic.php
 create mode 100644 themes/classic/views/.htaccess
 create mode 100644 themes/classic/views/layouts/.gitignore
 create mode 100644 themes/classic/views/site/.gitignore
 create mode 100644 themes/classic/views/system/.gitignore
{% endhighlight %}

Check out my previous post, [Hosting Your Own Git Repositories](http://kcblog.net/2012/02/27/hosting-your-own-git-repositories.html) to host your repositories remotely.
