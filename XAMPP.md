# XAMPP Set Up (*Windows*)

* [Overview](#overview)
* [Prerequisites](#prerequisites)
    * [XAMPP Configuration and MySQL](#XAMPP-configuration-and-mysql)
        * [Additional Configuration Changes](#additional-configuration-changes)
* [Folder Junctions](#folder-junctions)
    * [Example](#example)

# Overview

This document describes how to set up XAMPP when MySQL is present and may be running *outside* of XAMPP. It also describes the use of folder **"junctions"** when content is located elsewhere during development.

# Prerequisites

* XAMPP is installed (*includes its own MySQL server*) - <https://www.apachefriends.org/>
* MySQL (*Community Edition*) may, or may not be installed - <https://www.mysql.com/>. However, the benefits to installing MySQL independently are:
  * It's bundled with Workbench which is extremely useful for managing databases 
  * You can work on databases without running XAMPP
  * 
* Windows OS - these instructions are specific to Windows 10 Home or Pro.

**NOTE**: At the time when this document was created (2022-07-29) and When XAMPP installed on Windows 10 (21H2) it may be necessary to run it as *administrator*.

## XAMPP Configuration and MySQL



# Folder Junctions

You might be familiar with a Linux *hard link*. The Window's equivalent is a *junction*. And they are particularly useful when keeping project folders organized in separate and possibly unrelated locations but you want to serve them with XAMPP during development. 

Some alternatives to this method are - 

* Change XAMPP's document root path to the project's path, works for only one project at a time.
* Copy the project files into the document root after one or more edits. 

Neither of those methods are easy to work with. But junctions are a lot easier and since they look like folders you can have as many (*within the limits of Windows*) as you need. 

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

    `http://localhost/projectb/`


NOTE: The "junctions" are permanent until deleted from the `c:\XAMPP\htdocs` folder. You **must** use rmdir to remove the junction.

