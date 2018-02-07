# MAMP Set Up (*Windows*)

* [Overview](#overview)
* [Prerequisites](#prerequisites)
    * [MAMP Configuration and MySQL](#mamp-configuration-and-mysql)
        * [Additional Configuration Changes](#additional-configuration-changes)
* [Folder Junctions](#folder-junctions)
    * [Example](#example)

# Overview

This file describes how to set up MAMP when MySQL is present and may be running *outside* of MAMP. It also describes the use of folder **"junctions"** when content is located elsewhere during development.

At the time of this writing the current MAMP (*free*) version is/was **3.3.0**. 

# Prerequisites

* MAMP is installed (*includes its own MySQL server*) - <https://www.mamp.info/en/>
* MySQL may, or may not be installed - <https://www.mysql.com/>
* Windows OS - these instructions are specific to Windows. These instructions will work for 7 Pro, 10 Home & Pro.

## MAMP Configuration and MySQL

If you have installed MySQL prior to this point, or if you are planning on installing it for use without a HTTP server then either MAMP or MySQL will need to have their listening port changed. The default for an SQL server is 3306. And since I always have the stand-alone MySQL server running I've changed the MAMP SQL port to 3307.

If you aren't going to use MySQL then you can just install MAMP with it's default settings and skip changing the port number.

1. Install MAMP
2. Run MAMP and - 
     * Go to "Preferences"
     * Go to the "Ports" tab and change the MySQL Port to 3307
     * Save the change

### Additional Configuration Changes

Even if you had modified the MySQL port as descibed above MAMP *will not* fully recognize that change. If you were to run `phpinfo.php` after modifying the port number it would still report **3306** as it's port number and would connect to any MySQL server listening on that port.

To complete the port number modification you will need to edit `C:\MAMP\conf\`**`phpX.Y.Z`**`\php.ini`, where **`phpX.Y.Z`** corresponds to the version of PHP you've chose during the MAMP set up. Open the file in an editor and search for "`default_port`". There should be two occurances - `mysql.default_port` and `mysqli.default_port`. Modify both to appear as - 

`mysql.default_port = 3307`

*and*

`mysqli.default_port = 3307`

If the MAMP server was running while you were editing then it will require a restart in order for the new settings to take affect. The changed settings can be verified by running `phpinfo.php`.

# Folder Junctions

You might be familiar with a Linux *hard link*. The Window's equivalent is a *junction*. And they are particularly useful when keeping project folders organized in separate and possibly unrelated locations but you want to serve them with MAMP during development. 

Some alternatives to this method are - 

* Change MAMP's document root path to the project's path, works for only one project at a time.
* Copy the project files into the document root after one or more edits. 

Neither of those methods are easy to work with. But junctions are a lot easier and since they look like folders you can have as many (*within the limits of Windows*) you need. 

## Example

Let's say you're working on two separate projects and want to test them locally using MAMP. And they're found in the following paths -

**Project A** - C:\Users\a-user\Documents\Projects\some-project 

**Project B** - D:\projects\web\customer-X\new-site

The following steps will create two project junctions :

1. Open a command-line window and go to `C:\MAMP\htdocs`
2. Run the following commands - 

    `mklink /j c:\mamp\htdocs\projecta C:\Users\a-user\Documents\Projects\some-project`

    `mklink /j c:\mamp\htdocs\projectb D:\projects\web\customer-X\new-site`

3. Then in your browser go to - 

    `http://localhost/projecta/index.html`

    `http://localhost/projectb/index.html`



NOTE: The "junctions" are permanent until deleted from the `c:\mamp\htdocs` folder. You **must** use rmdir to remove the junction.

