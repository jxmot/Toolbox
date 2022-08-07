# XAMPP Set Up (*Windows*)

* [Overview](#overview)
* [Prerequisites](#prerequisites)
    * [XAMPP and MySQL](#xampp-and-mysql)
* [Folder Junctions](#folder-junctions)
    * [Example](#example)

# Overview

This document describes a development environment for Windows 10 that contains:

* XAMPP and PHP - For the purposes of this document MySQL/MariaDB **are not** installed as part of XAMPP.
* MySQL *Community Edition* - It is assumed that this has been installed separately and that a password has been set for the "root" user.

It also describes the use of folder **"junctions"** when content is located outside of XAMPP's *document root* during development.

# Prerequisites

* Windows 10 OS - these instructions are specific to Windows 10. I use *Pro* exclusively so there may be minor differences compared to *Home*.
* [MySQL *Community Edition*](https://www.mysql.com/) - The benefits to installing MySQL independently are:
  * It's bundled with Workbench which is extremely useful for managing databases and has a much nicer GUI than phpMyAdmin.
  * You can work on databases without running XAMPP.
  * You can choose a version that matches your web server.
    * Workbench can also be used to access your web server's MySQL databases. *This is not covered here.*
* XAMPP - You can find it [here](https://www.apachefriends.org/)
  * Choose a version where the PHP version matches your web server's PHP version.

**NOTES**: 
**a)** At the time when this document was created (2022-07-29) and when XAMPP installed on Windows 10 Pro (21H2) it may be necessary to run XAMPP as *administrator*.
**b)** XAMPP can be manipulated to use more than one version of PHP. See the [Xampp PHP Switcher](https://github.com/JackieDo/Xampp-PHP-Switcher) for details.

## XAMPP and MySQL

According to the [XAMPP Windows FAQ](https://www.apachefriends.org/faq_windows.html) it comes with MariaDB *instead of* MySQL since XAMPP versions 5.5.30 and 5.6.14. However, note that the XAMPP control panel might still say "MySQL" and not "MariaDB".

When MySQL *Community Edition* is installed it will be necessary to make a small change if you want to use XAMPP's phpMyAdmin script:

1) Start the XAMPP control panel
2) Stop Apache
3) Click the "Config" button and choose "phpMyAdmin(config.inc.php)"
4) Find the line - `$cfg['Servers'][$i]['password'] = ''`
5) Add your MySQL "root" user password
6) Save the file
7) Restart Apache via the XAMPP control panel

Now phpMyAdmin should work as expected.

The phpMyAdmin config file can be edited directly at `c:/xampp/phpMyAdmin/config.inc.php` but only if XAMPP was installed to its default location.

# Folder Junctions

You might be familiar with a Linux *symbolic link*. The Window's equivalent is a *junction*. And they are particularly useful when keeping project folders organized in separate and possibly unrelated locations but you want to serve them with XAMPP during development. 

Some alternatives to this method are - 

* Change XAMPP's document root path to the project's path, works for only one project at a time.
* Copy the project files into the document root after one or more edits. 

Neither of those methods are easy to work with. But junctions are a lot easier and since they look like folders you can have as many (*within the limits of Windows*) as you need.

**NOTE**: When editing project files make sure you are editing them from within their actual project folder, and **not** via the junction you created.

## Example

Let's say you're working on two separate projects and want to test them locally using XAMPP. And they're found in the following paths -

**Project A** - C:\Users\a-user\Documents\Projects\some-project 

**Project B** - D:\projects\web\customer-X\new-site

The following steps will create two project junctions :

1. Open a command-line window and go to `C:\XAMPP\htdocs`
2. Run the following commands - 

    `mklink /j c:\XAMPP\htdocs\projecta C:\Users\a-user\Documents\Projects\some-project`

    `mklink /j c:\XAMPP\htdocs\projectb D:\projects\web\customer-X\new-site`

3. While XAMPP is running and Apache has been started use your browser and go to - 

    `http://localhost/projecta/`

    In a separate tab go to - 

    `http://localhost/projectb/`

NOTE: The "junctions" are permanent until removed from the `c:\XAMPP\htdocs` folder. You **must** use rmdir to remove the junction.

