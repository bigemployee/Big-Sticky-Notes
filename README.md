Big-Sticky-Notes
================

Introduction
------------
Big Sticky Notes is web application tutorial built on Zend Framework 2 and uses
the ZF2 MVC layer and module system. This simple application is an extention to
the skeleton application provided by Zend Technologies.

Installation
------------

Using Composer (recommended)
----------------------------
The recommended way to get a working copy of this project is to clone the repository
and use `composer` to install dependencies using the `create-project` command:

    curl -s https://getcomposer.org/installer | php --
    php composer.phar create-project --repository-url="http://packages.zendframework.com" zendframework/skeleton-application path/to/install

Alternately, clone the repository and manually invoke `composer` using the shipped
`composer.phar`:

    cd my/project/dir
    git clone git://github.com/zendframework/ZendSkeletonApplication.git
    cd ZendSkeletonApplication
    php composer.phar self-update
    php composer.phar install

(The `self-update` directive is to ensure you have an up-to-date `composer.phar`
available.)

Another alternative for downloading the project is to grab it via `curl`, and
then pass it to `tar`:

    cd my/project/dir
    curl -#L https://github.com/zendframework/ZendSkeletonApplication/tarball/master | tar xz --strip-components=1

You would then invoke `composer` to install dependencies per the previous
example.

Using Git submodules
--------------------
Alternatively, you can install using native git submodules:

    git clone git://github.com/zendframework/ZendSkeletonApplication.git --recursive

Database Table
--------
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

Virtual Host
------------
Afterwards, set up a virtual host to point to the public/ directory of the
project and you should be ready to go!
