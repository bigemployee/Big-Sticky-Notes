Big-Sticky-Notes
================
    ______ _         _____                 _
    | ___ (_)       |  ___|               | |
    | |_/ /_  __ _  | |__  _ __ ___  _ __ | | ___  _   _  ___  ___
    | ___ \ |/ _` | |  __|| '_ ` _ \| '_ \| |/ _ \| | | |/ _ \/ _ \
    | |_/ / | (_| | | |___| | | | | | |_) | | (_) | |_| |  __/  __/
    \____/|_|\__, | \____/|_| |_| |_| .__/|_|\___/ \__, |\___|\___|
              __/ |                 | |             __/ |
             |___/                  |_|            |___/

Introduction
------------
Big Sticky Notes is web application tutorial built on Zend Framework 2 and uses
the ZF2 MVC layer and module system. This simple application is an extention to
the skeleton application provided by Zend Technologies.

Installation
------------

Using Composer (recommended)
----------------------------
Clone the repository and manually invoke `composer` using the shipped
`composer.phar`:

    cd my/project/dir
    git://github.com/bigemployee/Big-Sticky-Notes.git
    cd Big-Sticky-Notes
    php composer.phar self-update
    php composer.phar install

(The `self-update` directive is to ensure you have an up-to-date `composer.phar`
available.)

Database
--------
Create Database and run the following query to create the table and insert
sample data.

    -- -----------------------------------------------------
    -- Table `stickynotes`.`stickynotes`
    -- -----------------------------------------------------
    DROP TABLE IF EXISTS `stickynotes`.`stickynotes` ;
    CREATE TABLE IF NOT EXISTS `stickynotes`.`stickynotes` (
    `id` INT NOT NULL AUTO_INCREMENT ,
    `note` VARCHAR(255) NULL ,
    `created` TIMESTAMP NOT NULL ,
    PRIMARY KEY (`id`) ,
    UNIQUE INDEX `id_UNIQUE` (`id` ASC) )
    ENGINE = MyISAM;
    -- -----------------------------------------------------
    -- Data for table `stickynotes`.`stickynotes`
    -- -----------------------------------------------------
    START TRANSACTION;
    USE `stickynotes`;
    INSERT INTO `stickynotes`.`stickynotes` (`id`, `note`, `created`) VALUES (1, 'This is a sticky note you can type and edit.', '');
    INSERT INTO `stickynotes`.`stickynotes` (`id`, `note`, `created`) VALUES (NULL, 'This is another sticky note ', NULL);
    COMMIT;

open config/autoload/global.php and config/autoload/local.php and configure
your Database credentials.

if local.php is missing duplicate local.php.dist and modify the file

    // /config/autoload/local.php
    return array(
        'db' => array(
            'username' => 'DB_User_Name',
            'password' => 'DB_Password',
        ),
    );

Virtual Host
------------
Afterwards, set up a virtual host to point to the public/ directory of the
project and you should be ready to go!
