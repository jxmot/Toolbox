# MAMP Set Up (*Windows*)

This file describes how to set up MAMP and folder "junctions" for use with folders that are located elsewhere. This is particularly useful when keeping project folders organized in separate and possibly unrelated locations and you want to serve them with MAMP during development. 

For Example - 

Let's say you're working on to separate projects and want to test them locally using MAMP. And they're found in the following paths - 

**Project A** - C:\Users\a-user\Documents\Projects\some-project

**Project B** - D:\projects\web\customer-X\new-site

## Prerequisites

* MAMP - <https://www.mamp.info/en/>
* Windows OS - these instructions are specific to Windows.

### MAMP Installation :

If you have MySQL installed prior to this point, or if you are planning on installing it for use without a HTTP server then either MAMP or MySQL will need to have their listening port changed. The default for an SQL server is 3306. And since I always have the MySQL server running I've change the MAMP SQL port to 3307.

If you aren't going to use MySQL then you can just install MAMP with it's default settings and skip changing the port number.

1. Install MAMP
2. Run MAMP and - 
     * Go to "Preferences"
     * Go to the "Ports" tab and change the MySQL Port to 3307.  
     * Save the change

### After MAMP is Installed and Running :

Here we'll use the example project paths from above - 

1. Open a command window and go to `C:\MAMP\htdocs`
2. Run the following command - 

        mklink /j c:\mamp\htdocs\projecta C:\Users\a-user\Documents\Projects\some-project

    NOTE: Do NOT create `c:\mamp\htdocs\NEWFOLDER`!! And where you see `some-project` that folder is where you have stored the files that you're working on.

3. Then in your browser go to - 

        http://localhost/projecta/index.html

NOTE: The "junctions" are permanent until deleted from the `c:\mamp\htdocs` folder. You **must** use rmdir to remove the junction.

