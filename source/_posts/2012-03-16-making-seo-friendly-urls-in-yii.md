---
layout: post
title: "Making SEO-Friendly URLs in Yii"
comments: true
categories: [Guide,Yii]
description: In this guide, we show how to make SEO-friendly URLs in Yii.
---
After [Starting Up Yii Project with Git](http://kcblog.net/2012/03/01/starting-up-yii-project-with-git.html) you can try open up your browser and navigate to [http://www.example.com/project/](http://www.example.com/project/) and you will then notice the links are like [http://www.example.com/project/index.php?r=site/contact](http://www.example.com/project/index.php?r=site/contact) and [http://www.example.com/project/index.php?r=site/page&view=about](http://www.example.com/project/index.php?r=site/page&view=about).

<!-- more -->

##  URL Routes

This can be archived easily via uncommenting the `urlManager` located in `./protected/config/main.php`.

{% codeblock lang:php %}
// uncomment the following to enable URLs in path-format
'urlManager'=>array(
  'urlFormat'=>'path',
  'rules'=>array(
    '<controller:\w+>/<id:\d+>'=>'<controller>/view',
    '<controller:\w+>/<action:\w+>/<id:\d+>'=>'<controller>/<action>',
    '<controller:\w+>/<action:\w+>'=>'<controller>/<action>',
  ),
),
{% endcodeblock %}

Refresh the page and you will notice that the URLs have been changed to [http://www.example.com/project/index.php/site/contact](http://www.example.com/project/index.php/site/contact) and [http://www.example.com/project/index.php/site/page?view=about](http://www.example.com/project/index.php/site/page?view=about).

## Further Makeup

You can further cleanup the URLs by removing `index.php` and adding a suffix `.html` to the URLs.

{% codeblock lang:php %}
// uncomment the following to enable URLs in path-format
'urlManager'=>array(
  'urlFormat'=>'path',
  'showScriptName'=>false,
  'urlSuffix'=>'.html',
  'rules'=>array(
    '<controller:\w+>/<id:\d+>'=>'<controller>/view',
    '<controller:\w+>/<action:\w+>/<id:\d+>'=>'<controller>/<action>',
    '<controller:\w+>/<action:\w+>'=>'<controller>/<action>',
  ),
),
{% endcodeblock %}

Refresh the page and you will notice that the URLs have been changed to [http://www.example.com/project/site/contact.html](http://www.example.com/project/site/contact.html) and [http://www.example.com/project/site/page.html?view=about](http://www.example.com/project/site/page.html?view=about).

Notice that the generated URLs will get a 404 Error if you don't add the follow `.htaccess` file:

{% codeblock %}
RewriteEngine On
RewriteCond %{REQUEST_FILENAME} !-f
RewriteCond %{REQUEST_FILENAME} !-d
RewriteRule ^(.*)\?*$ index.php/$1 [L,QSA]
{% endcodeblock %}

You can now enjoy the prettified SEO-friendly URLs.

## Conclusion

Making SEO-friendly URLs makes your web application search engines optimized and compatible. 