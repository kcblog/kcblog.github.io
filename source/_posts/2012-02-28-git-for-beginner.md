---
layout: post
title: "Git for Beginner"
comments: true
categories: [Guide,Git]
description: Simple and useful commands are being introduced in Git for beginners.
---
After [Hosting Your Own Git Repositories](http://kcblog.net/2012/02/27/hosting-your-own-git-repositories.html) I have been thinking of continuing on topics about Git, although I am not an expert. Please point out and comments if you have a better idea or anything to improve. Thanks!

## Introduce Yourself to Git

Setting up your display name and email address show in Git commits.

{% highlight %}
$ git config --global user.name "Your Name"
$ git config --global user.email "user@test.com"
{% endhighlight %}

You have to do this once and Git will remember you every time you commit your works.

## Copy of the Project

With `git clone` you can simply get a copy of the project you want to work on.

{% highlight %}
$ git clone git@server.com:test.git
Cloning into test...
git@server.com's password:
remote: Counting objects: 6, done.
remote: Compressing objects: 100% (3/3), done.
remote: Total 6 (delta 0), reused 0 (delta 0)
Receiving objects: 100% (6/6), done.
$ cd test
$ ls -a
.		..		.git		README		index.html
{% endhighlight %}

## Add Files into Project

With `git add` you are able to add files to the project's staging area.

{% highlight %}
$ echo "<?php phpinfo();" > info.php
$ ls -a
.		..		.git		README		index.html	info.php
$ git status -s
?? info.php
$ git add info.php
$ git status -s
A  info.php
$ git diff HEAD
diff --git a/info.php b/info.php
new file mode 100644
index 0000000..c4837a3
--- /dev/null
+++ b/info.php
@@ -0,0 +1 @@
+<?php phpinfo();
{% endhighlight %}

## Create Snapshot of the Staging Area

After adding files into staging area, you can now use `git commit` to create snapshot of the changes.

{% highlight %}
$ git commit -a -m 'add info file'
[master a591ab6] add info file
 1 files changed, 1 insertions(+), 0 deletions(-)
 create mode 100644 info.php
{% endhighlight %}

## Push Commits to Remote Server

Commits are done locally before a `git push` command is given.

{% highlight %}
$ git push
git@server.com's password: 
Counting objects: 4, done.
Delta compression using up to 2 threads.
Compressing objects: 100% (2/2), done.
Writing objects: 100% (3/3), 320 bytes, done.
Total 3 (delta 0), reused 2 (delta 0)
To git@server.com:test.git
   c62c56b..a591ab6  master -> master
{% endhighlight %}

## Fetching Updates from Remote Server

Power of the collaboration system, with `git pull` your local codes are to be sync'ed with other collaborators.

{% highlight %}
$ git pull
git@server.com's password: 
remote: Counting objects: 5, done.
remote: Compressing objects: 100% (2/2), done.
remote: Total 3 (delta 1), reused 0 (delta 0)
Unpacking objects: 100% (3/3), done.
From server.com:test
   a591ab6..5781fe7  master     -> origin/master
Updating a591ab6..5781fe7
Fast-forward
 info.php |    4 +++-
 1 files changed, 3 insertions(+), 1 deletions(-)
{% endhighlight %}

The command `git pull` combines `git fetch` with `git merge` commands, where will fetch the updates and merge into your local codes.

## Conclusion

