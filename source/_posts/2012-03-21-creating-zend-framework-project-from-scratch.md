---
layout: post
title: "Creating Zend Framework Project from Scratch"
comments: true
categories: [Guide,Zend]
description: We describe how to start a zend framework project from scratch.
---
## Requirements

* A working Apache web server
* mod_rewrite enabled
* PHP 5.2+

Download latest Zend Framework from [Zend Framework](http://framework.zend.com/) website and extract to your working directory.

<!-- more -->

## Create the Project Directory

First, create a new directory in your working directory for the project and navigate into it.

{% codeblock %}
$ mkdir zf-project
$ cd zf-project
{% endcodeblock %}

Next, we will need to create a directory **application** to hold all the controllers, models, views and configs, etc.

Also create a **.htaccess** in the root like this:

{% codeblock %}
SetEnv APPLICATION_ENV "development"

RewriteEngine On
RewriteCond %{REQUEST_FILENAME} -f [OR]
RewriteCond %{REQUEST_FILENAME} -d
RewriteRule ^.*$ index.php [L,QSA]
{% endcodeblock %}

And create an **index.php** in the root like this:

{% codeblock lang:php %}
<?php
defined('APPLICATION_PATH')
    || define('APPLICATION_PATH', realpath(dirname(__FILE__) . '/application'));

defined('APPLICATION_ENV')
    || define('APPLICATION_ENV', (getenv('APPLICATION_ENV') ? getenv('APPLICATION_ENV') : 'production'));

set_include_path(implode(PATH_SEPARATOR, array(
    realpath(APPLICATION_PATH . '/../../zf/library'),
    get_include_path(),
)));

require_once 'Zend/Application.php';

$application = new Zend_Application(
    APPLICATION_ENV,
    APPLICATION_PATH . '/configs/application.ini'
);
$application->bootstrap()
            ->run();
{% endcodeblock %}

## Create the Project Structure

Create these directories and sub-directories in `application/` directory:

* configs
* controllers
* models
* modules
* views
> * scripts
> > * error
> > * index
> * template

{% codeblock %}
$ mkdir application/configs
$ mkdir application/controllers
$ mkdir application/models
$ mkdir application/modules
$ mkdir application/views
$ mkdir application/views/scripts
$ mkdir application/views/scripts/index
$ mkdir application/views/scripts/error
$ mkdir application/views/template
{% endcodeblock %}

## Create the Application Configurations File

Create config **application.ini** under `application/configs/` directory:

{% codeblock %}
[development]
phpSettings.display_startup_errors = 1
phpSettings.display_errors         = 1
phpSettings.DATE.timezone          = "Asia/Singapore"

resources.frontController.controllerDirectory      = APPLICATION_PATH "/controllers"
resources.frontController.params.displayExceptions = 0
resources.layout.layoutPath                        = APPLICATION_PATH "/views/template/"

[staging : development]
phpSettings.display_startup_errors = 0
phpSettings.display_errors         = 0

[production : development]
phpSettings.display_startup_errors = 1
phpSettings.display_errors         = 1
{% endcodeblock %}

## Create the Application Controllers

Create controller **IndexController.php** under `application/controllers/` directory:

{% codeblock lang:php %}
<?php
class IndexController extends Zend_Controller_Action {
  public function indexAction() {
  
  }
}
{% endcodeblock %}

Create controller **ErrorController.php** under `application/controllers/` directory:

{% codeblock lang:php %}
<?php
class ErrorController extends Zend_Controller_Action {
  public function errorAction() {
  
  }
}
{% endcodeblock %}

## Create the Default Template

Create header **header.phtml** under `application/views/template/` directory:

{% codeblock lang:php %}
<!DOCTYPE html>
<html>
<head>
  <meta charset="utf-8" />
  <title>Zend Framework Tutorial</title>
  <?php echo $this->headLink()->appendStylesheet('//twitter.github.com/bootstrap/assets/css/bootstrap.css') . PHP_EOL; ?>
  <?php echo $this->headScript()->appendFile('//ajax.googleapis.com/ajax/libs/jquery/1.7.1/jquery.min.js') . PHP_EOL; ?>
</head>
<body>
  <div class="container">
    <div class="row">
      <div class="span12">
        <p>This is the header!</p>
      </div>
    </div>
    <div class="row">
      <div class="span12">
{% endcodeblock %}

Create footer **footer.phtml** under `application/views/template/` directory:

{% codeblock lang:php %}

        <hr />
        <footer>
          <p>This is the footer!</p>
        </footer>
      </div>
    </div>
  </div>
</body>
</html>
{% endcodeblock %}

Create template **layout.html** under `application/views/template` directory to combine both header and footer:

{% codeblock lang:php %}
<?php
include_once('header.phtml');
echo $this->layout()->content;
include_once('footer.phtml');
{% endcodeblock %}

## Create the View for Controllers

Create view **index.phtml** for **IndexController** under `application/views/index/` directory:

{% codeblock lang:php %}
<h2>Welcome to Zend Framework Tutorial!</h2>
{% endcodeblock %}

Create view **error.phtml** for **ErrorController** under `application/views/error/` directory:

{% codeblock lang:php %}
<h2>An error occurred!</h2>
{% endcodeblock %}

## Project Ready

You can now browse to [http://www.example.com/zf-project/](http://www.example.com/zf-project/) and will see a plain and clean website like this:

![Example 01](http://s3.kcblog.net/images/creating-zend-framework-project-from-scratch.png)

## Source Code

Project source code available in [GitHub](https://github.com/kwangchin/zf-tutorial) for your convenience.

## Conclusion

You can create projects with Zend Framework easily with Zend Framework Console Tool. Check [Documentation: Using the CLI Tool](http://framework.zend.com/manual/en/zend.tool.framework.clitool.html) for more information.