# ToolBox - as of September, 2017

Greetings!

In this repository is nothing more than this file and any tool related files such as configurations that I've modified for my use. 

Feel free to use any of the modified configuration files, however I do not support any of the programs I've listed here. So if you run into trouble with them or with configuring them you may have to contact the authors of the related software.

Please keep in mind that all of the programs I've listed below are *free* and are  installed in **_Windows_**. And at the least there's a *free* version available and it's the one I'm using. If I've *paid* for one it will be noted below.

Unless something specific needs to be noted I will not be providing any installation instructions. As they would eventually become out of date when the associated application is updated.

# Table of Contents

* [My Development Platform](#my-development-platform)
    * [Node](#node)
    * [MySQL](#mysql)
    * [MongoDB](#mongodb)
* [Editing Tools](#editing-tools)
* [File Grep and File Search](#file-grep-and-file-search)
* [File Difference and Merge](#file-difference-and-merge)
* [Version Control](#version-control)
* [IDE Software](#ide-software)
* [Other Useful Tools](#other-useful-tools)
    * [API Tester](#api-tester)
    * [Wire Frame and Diagram Editors](#wire-frame-and-diagram-editors)
    * [Image Editors](#image-editors)
    * [Virtual Machine](#virtual-machine)
        * [ISO Installations](#iso-installations)
        * [ISO Sources](#iso-sources)
        * [64 vs 32 Bit Guests](#64-vs-32-bit-guests)
        * [Things to Note](#things-to-note)
    * [Terminal Emulators](#terminal-emulators)
    * [HTTP Servers](#http-servers)
    * [Database Managers](#database-managers)
        * [MySQL Workbench](#mysql-workbench)
        * [Robomongo](#robomongo)
* [Tools That I Do Not Use](#tools-that-i-do-not-use)
    * [Sublime Editor](#sublime-editor)
    * [Eclipse](#eclipse)

# My Development Platform

I'm a *Windows* guy, never used an *Apple* and probably never will. If you (*the reader*) are using an *Apple* then a lot of what's in this document may not apply to you. However some of the tools *might* be available for the Apple. Check out the links I've provided and look around.

Windows Details :

* Windows 10
    * Home and Pro Editions
    * 64 bit
* Windows 7
    * Professional
    * 64 bit

## Node

Another piece of my development platform is *NodeJS*. I'm currently using **v6.10.2 LTS**. I've found that *Node* can be quite useful for developing code *prior* to integration into a *browser* project.

## MySQL

The version I'm using is **5.7**. SQL has been around for quite a long time. It has clear advantages in regards to it wide spread use. And technically speaking MySQL is robust *and* secure. Many businesses use it, and it can be found in most hosting service packages. Mainstream web applications like *Wordpress* use it, and most e-commerce packages also make use of it.

## MongoDB

I like this database for a few reasons - 

* Data is stored in JSON / BSON (<https://www.mongodb.com/json-and-bson>)
* If your hosting service doesn't provide it you can sign up for an mLab account (<https://mlab.com/>) and have your data stored on their servers. The free account has enough capacity for most applications.
* When paired with Mongoose (<http://mongoosejs.com/>) and the Bluebird promise API MongoDB becomes a very reasonable alternative to SQL databases.
* In my opinion it's much easier to implement than MySQL.

# Editing Tools

**Notepad++** : <https://notepad-plus-plus.org/>

This is my **primary** editor, and I've been using it for quite a number of years. It has a lot of features and I use most of them on a regular basis. I've tried other editors but found them to be lacking in regards to the features I use. For example in Notepad++ I use :

* Column cut/copy and past - Until you use this feature you won't know what your missing. By holding `ALT` plus `SHIFT` and moving with the arrow keys you can do things like -
    * Insert on all lines selected, this includes tabs and spaces.
    * Replace or delete.
* Macro recording - Another very useful feature! You can *record* keystrokes and play them back. This is very useful when you want to repeat a series of editing steps.
* **Notes for Windows Users:** 
    * Changing editor settings - This can be a problem. At least it is in v7.2.2. You might discover that your changed settings aren't *permanent*. This is because you need to run the editor as an *administrator* when changing the options.

**Markdown Edit** : <http://markdownedit.com/>

A handy program to have for editing *markdown* files. I've tried a number of them and this one works best for **Git** style markdown files. I also use it for *Bitbucket* markdown, but should be noted that Git and Bitbucket are slightly different in regards to the markdown that's recognized. This editor has the following features that I find to be useful - 

* Side-by-side editing and WYSIWYG - the left side of the program's window is where you do your editing. It *highlights* markdown elements for you and has some "smarts" in regards to bulleted lists as it will create a new bullet on the next line when you hit `Enter` and the new line will be *at the same level* as the previous line.
* Re-opens last file automatically when started.
* Installation associates it with `*.md` files.

*I used it to create and edit this file.*

# File Grep and File Search

**AstroGrep** : <http://astrogrep.sourceforge.net/>

Anyone who has been working in *Linux* (*or Unix for some of us "old timers"*) you have probably use the command-line utility `grep`. It is useful, but a *gui* version is so much better! And that's what this is. It's a GUI grep tool with the ability to tie in to your editor. For example you can configure *AstroGrep* to open a found file in your editor *on the line* you've double-clicked on in the results pane.

**Windows Search**: Admittedly, definitely **not** the best. But it works. If I find a better file search I'll be sure to note it here.

# File Difference and Merge

**Winmerge** : <http://winmerge.org/>

What's the *difference*? Being able to see the differences between two source files can mean the difference between finding the bug quickly or potentially taking a real long time. 

This application will allow you to edit or copy changes from one file to another. It can also be used to compare the contents of a folder against another. 

# Version Control

**Gitkraken** : <https://www.gitkraken.com/>

This is my favorite Git UI tool. It works perfectly for Github and Bitbucket. It's free for non-commercial use. And it also runs on Mac and Linux.

# IDE Software

**Netbeans 8.x** : <https://netbeans.org/features/index.html>

A very full featured IDE that allows you to edit, debug, and manage (*i.e. Git*) HTML5/JavaScript, Node, and PHP applications. I use it with *Chrome*, which requires a plugin to be installed.

**Visual Studio Code** : <https://code.visualstudio.com/>

I've recently started using *Visual Studio Code* and so far I **really** like it. And compared to *Netbeans* it certainly has some advantages. Here's the ones I've found so far - 

* The *Visual Studio Code* IDE loads quickly, much faster than *Netbeans*.
* No cumbersome "projects", just open a folder and have at it!
* IDE extensions are managed better than Netbeans.

**Bootstrap Studio** : <https://bootstrapstudio.io/>

This is one of the few programs that I've paid for. And this one has proven to be worth beyond the $25 I spent. Basically it's a WYSIWYG Bootstrap editor within an IDE.

They don't offer a *trial* version but they do provide a web version that you can tinker with. And there are a **lot** of video tutorials, and a users' forum.

But it is **not** an HTML editor. You create Bootstrap pages by inserting or drag-n-drop *elements* in to the page. I found it to be a better and quicker means to create a layout than using just a text editor (*such as Notepad++*).

Some aspects of the UI can be a little quirky, as it does not always let you insert tags or blocks where *you* want them. And it will make some assumptions for you. For example, for modularity reasons I like to have my HTML files associated with a single and individually named CSS file rather than pile every page's specific CSS into one huge file. But the program assumes that all HTML files will reference all CSS files. So I don't use this program to create deployment ready content.

There are some really great features - 

* Preview - you can preview the page your working on in *real time*. In other words, as you make changes and save them the preview will update automatically.
* Export - even though your project is saved in a proprietary format it's easy to export it as HTML, CSS, JS and image files.
* Add to Library - this makes reuse of blocks really simple. You can export as little, or as as much as you like and it ends up your own library.
* Element navigation - they've made it very intuitive for navigating through the elements and they provide a really good UI for changing attributes.

# Other Useful Tools

## API Testers

**Postman** : <https://www.getpostman.com/>

This is another one of those multi-use tools. So far I've used it for - 

* Typical API development and testing.
* Analyzing web based hardware (*such as IP cameras*) APIs.

A very useful feature is the ability to *share* Postman collections. Collections are saved URLs that you can create and add to a named collection. And they can be shared! You only need to sign-in to Postman. 

## Wire Frame and Diagram Editors

**Evolus Pencil** : <http://pencil.evolus.vn/>

This is a free and open-source GUI prototyping tool. I use it for wire-framing and for creating diagrams. It can export to PNG files which makes it useful for creating images for markdown and other types of documents.

**Microsoft Visio** : <https://products.office.com/en-us/visio/flowchart-software>

Definitely **not** free. But it is an *excellent* diagramming tool with lots of features. If you can afford it I'd recommend Visio over Pencil.

## Image Editors

**PaintDOTNet** : <http://www.getpaint.net/index.html>

An excellent image editing tool, it's my favorite. It supports all common formats and you can work in *layers* which makes compositing very easy.

## Virtual Machine

**Oracle VirtualBox** : <https://www.virtualbox.org/>

HAve you ever run into a situation where you needed a *real server* and didn't have the hardware for it, or hosting? Then a *virtual machine* might be the solution. During development on some projects I've found it best to run the code on a VM *first* before deploying to a hosted server.

### ISO Installations

Installing from an ISO is simple. Especially in Windows 10 Pro because mounting an ISO as a virtual drive can be done by right clicking on the ISO file an clicking "Mount".

Then run Virtualbox and as the VM is coming up you will be given a chance to select the mount ISO.

### ISO Sources

* Turnkey Linux : <https://www.turnkeylinux.org/>

A very good source for **free** Linux/Debian images. Most are pre-configured with other free software components and generally do not require much (if any) configuration.

* Others : Any of the Linux distro sites will have ISOs for download. 

### 64 vs 32 Bit Guests

When I was running VirtualBox on Windows 7 Pro / 64 bit I was able to install 64 bit *guests*. However when I switched to Windows 10 Pro / 64 bit that ability *went away*.

There are a couple of reasons why it happened. First, you need to enable the Intel virtualization in your BIOS. And you may (*or may not*) have to install VirtualBox as an *administrator*. I had tried reinstalling VirtualBox before I tried the BIOS change and had no luck. But when I changed my BIOS and then ran VirtualBox the 64 bit guest options reappeared.

Here's a link that found useful in fixing this issue - 

<https://forums.virtualbox.org/viewtopic.php?f=1&t=62339>

### Things to Note

**Networking :**
Late last year one of the *Windows 10 Home 64 bit* updates "broke" networking with the virtual machines. Prior to the breakage my virtual machines were able to make DHCP requests and obtain their IP address from my router. But no more. I've read some complaints about this at that time, however there were no solutions. 

However, running on Windows 10 **Pro 64 bit** the problem appears to have been either fixed, or non-existent. I'll have to try my laptop again (*running Win 10 Home 64 bit*) and see if the issue is still there.

In order for the VM to make the DHCP request a VM network setting must be changed. This can be done prior to installing from the ISO. By default the VM network adapter is set to NAT. Change to "Bridged Adapter" and your VM will be able to obtain its IP address.

**Hyper-V :**

After recently installing *Microsoft Visual Studio Community* I noticed that their virtual machine software called *Hyper-V* was installed. And afterwards when I ran VirtualBox it failed to start the virtual machine. After some research and reading I determined that Hyper-V was the cause of the problem. Just to be clear the symptoms manifest as the virtual machine window closing abruptly and a dialog contain the message **VT-x is not available (VERR_VMX_NO_VMX)**.

The fix I used was to disable Hyper-V. And the most useful information I found was at [How to Enable and Disable Hyper-V in Windows 10 & 8](http://www.poweronplatforms.com/enable-disable-hyper-v-windows-10-8/).

After Hyper-V was disabled VirtualBox worked without any issues. **Success!**

## Terminal Emulators

**Bitvise** : <https://www.bitvise.com/>

This is a much nicer terminal emulator than PuTTY. In addition to the terminal there's also an SFTP client. And I think it does a much better job of managing the SSH keys than other terminal programs. It allows you to create *profiles* for each server that you connect to. And those profiles can be copied between separate PCs that have Bitvise installed.

## HTTP Servers

**MAMP** (**not** Pro) : <https://www.mamp.info/en/>

If a VM isn't what you want to use, but if instead you need something that's relatively light weight then a local server might be a better choice. You won't have complete control or flexibility as you would with a VM. But for a lot of applications *less is better*.

For additional information on setting up MAMP please see [Mamp Setup](./MAMP.md)

**XAMPP** : <https://www.apachefriends.org/index.html>

Recently I was trying to see if I could *debug* my PHP code using *Visual Studio Code*. Along the way I had determined that MAMP was not going to work out. So I tried XAMPP and had *limited* success. However I like the XAMPP UI better than MAMP. It provides an easier access to the configuration files and longs when compared to MAMP. The XAMPP version I'm using comes with PHP Version 5.6.31, which is a very close match to the hosted servers that I deploy to.

Please note that as described in [Mamp Setup](./MAMP.md) I'm using *folder junctions*. You can find the details under the **Folder Junctions** section in that file.

## Database Managers

Currently I've been developing for **MySQL** and **MongoDB**. There are managers available for each, which is handy to have around.

When it comes to SQL vs NOSQL each has its advantages. When developing an application that requires a database I make my choice based on *what is best for the application and its end-use*.

### MySQL Workbench

The specific version I'm using is - 

* MySQL Workbench Community (GPL) for Windows, version 6.3.7 CE build 1199 (64 bit)

It can connect to the *local* MySQL installation, and connect to remote ones. Such as *Heroku* or other hosted servers.

### Robomongo

This app has a similar look and feel to *MySQL Workbench* and pretty much does the same type things as MySQL Workbench. 

# Tools That I Do Not Use

These are developer tools that I've tried for a while and subsequently decided that they were not going to work out for *me*. 

*Your mileage may vary....*

## Sublime Editor

I first heard about this editor in a class I had taken. It was a good choice for anyone who is *new* to the world of software development and it's available for the mac as well as the PC. However by comparison to *Notepad++* it is missing a number of the key features that I use regularly. 

## Eclipse

I'm not a fan of Eclipse. I've tried to use it, and tried. But I find it to be cumbersome in regards to it's installation and use. 


