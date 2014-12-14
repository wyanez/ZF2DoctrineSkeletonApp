ZF2DoctrineSkeletonApplication
===============================

Introduction
------------
This is a simple, skeleton application using the ZF2 MVC layer and module
systems and Doctrine2 ORM Layer. This application is meant to be used as a starting
place for those looking to get their feet wet with ZF2 and Doctrine2 ORM Layer.
Contains base classes: BaseDoctrineController, BaseDoctrineForm, BaseDoctrineModel and BaseDoctrineEntity and thus facilitate the development of your application.

Installation
------------

Simply clone this project and run 
```sh
$ php composer.phar install
```

Post-Installation
------------------
* Create `doctrine.local.php`: `cp autoload/doctrine.local{.php.dist,.php}`
* Edit `doctrine.local.php` and set your params of conexion to database in $dbParams array.
* Create your entities and place it in the folder `module\Application\src\Application\Entity`,  this entities must belong  at namespace `\Application\Entity`
* **Optional:** Activate `ZendDeveloperTools`: 
```sh
$ cp config/autoload/zenddevelopertools.local{.php.dist,.php}
```
    Activate the module ZendDeveloperTools in the section 'modules' of file `config\application.config`, uncoment the line //'ZendDeveloperTools'.

Web Server Setup
----------------

### PHP CLI Server

The simplest way to get started if you are using PHP 5.4 or above is to start the internal PHP cli-server in the root directory:

    php -S 0.0.0.0:8080 -t public/ public/index.php

This will start the cli-server on port 8080, and bind it to all network
interfaces.

**Note: ** The built-in CLI server is *for development only*.

### Apache Setup

To setup apache, setup a virtual host to point to the public/ directory of the
project and you should be ready to go! It should look something like below:

    <VirtualHost *:80>
        ServerName zf2-tutorial.localhost
        DocumentRoot /path/to/zf2-app/public
        SetEnv APPLICATION_ENV "development"
        <Directory /path/to/zf2-app/public>
            DirectoryIndex index.php
            AllowOverride All
            Order allow,deny
            Allow from all
        </Directory>
    </VirtualHost>
