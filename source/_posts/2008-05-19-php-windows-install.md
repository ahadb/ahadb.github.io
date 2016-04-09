---
layout: post
title: Installing APACHE 2.0.6 / PHP5.2.6 for Windows
description: Installing the Apache server coupled with PHP 5 can sometimes be a daunting task simply because open source technologies are always changing with newer releases, patches, etc, etc. 
wordcount: 1,249
manualdate: May 19, 2008
category: Other, Development
---

BRIEF HISTORY OF APACHE (As written on Wikipedia)

The Apache HTTP Server, commonly referred to simply as Apache [??pæt?i], is a web server notable for playing a key role in the initial growth of the World Wide Web. Apache was the first viable alternative to the Netscape Communications Corporation web server (currently known as Sun Java System Web Server), and has since evolved to rival other Unix-based web servers in terms of functionality and performance.

It is often said that the project’s name was chosen for two reasons: (1) out of respect for the Native American Indian tribe of Apache (Indé), well-known for their endurance and their skills in warfare, (2) and due to the project’s roots as a set of patches to the codebase of NCSA HTTPd 1.3 – making it “a patchy” server.
Apache is developed and maintained by an open community of developers under the auspices of the Apache Software Foundation. The application is available for a wide variety of operating systems, including Unix, FreeBSD, Linux, Solaris, Novell NetWare, Mac OS X, Microsoft Windows, OS/2, and eComStation. Released under the Apache License, Apache is characterized as free software and open source software.

Since April 1996 Apache has been the most popular HTTP server on the World Wide Web. However, since November 2005 it has experienced a steady decline of its market share, lost mostly to Microsoft Internet Information Services. As of April 2008 Apache served 50.42% of all websites.


BRIEF HISTORY OF PHP

The origins of PHP date back to 1995, when an independent software development contractor names Rasmus Lerdorf developed a Perl/CGI script that enabled him to know how many visitors were reading his online resume’. His script performed to tasks: logging visitor information, and displaying the count of visitors to the Web page.

Because the Web as we know it today was still young at that time, tools such as these were nonexistent, and they prompted emails inquiring about Lerdorf’s scripts. Lerdorf thus begun giving away his toolset, dubbed Personal Home Page. The clamor for the PHP toolset prompted Lerdorf to cuntinue developing the language, perhaps the most notable change early change coming when he added a feature for converting data. Ongoing additions to the PHP toolset cuminated in November 1997 with the release of PHP 2.0, or Personal Home Page – Form Interpreter (PHP-FI). As a result PHP’s rising popularity, the 2.0 release was accompanied by a number of enhancements and improvements from programmers worlwide.

The new PHP release was extremely popular, and a core team of developers soon joined Lerdorf. They kept the original concept of incorporating code directly alongside HTML and rewrote the parsing engine, giving birth to PHP 3.0, By the June 1998 release of version 3.0, more than 50,000 users were using PHP to enhance their Web Pages.

Development continued at a hectic pace over the next two years, with hundreds of functions being added and the user count growing in leaps and bounds. At the beginning of 1999, Netcrafts reported a conservative estimate of a user base surpassing 1,000,000, making PHP one of the most popular scripting languages of the world.

INSTALLING APACHE 2.0.6 FOR WINDOWS
Installing the Apache server coupled with PHP 5 can sometimes be a daunting task simply because open source technologies are always changing with newer releases, patches, etc, etc. I would like to take this time to make simplify the process of installing a working server on your local machine.There are numerous ways to install the Apache server on your local machine:

Using a bundle software such as XAMPP (Apache Friends).
Installing APACHE 2.2 / PHP5 manually.
Installing APACHE/PHP 5 through the MSI installer.
We will be focusing on installing APACHE/PHP5 on your local machine (Windows XP) with the MSI installer. Though it is most preferable to manually configure Apache / PHP5 this is a beginner tutorial to get you up and running. Hey i used to be a complete noob too so take it from me, it’s better to start off small and then build your way up. I will post another tutorial on installing manually in the next couple of weeks. Lets begin shall we?

STEP 1: Start by getting all the resources for the installation. By resources i mean all the downloads from the APACHE and PHP Websites. Goto the Apache Website (http://httpd.apache.org – ScreenShot 1) – and download the Win32 Binary without crypto (no mod_ssl) (MSI Installer) (http://httpd.apache.org/download.cgi – ScreenShot 2).apache_org1.jpg

apache_msi1.jpg
STEP 2: Double Click on the MSI Installer Icon and you will be taken to the welcome screen . Take a moment to read it and click next.apache_welcome.jpg
STEP 3: Accept the terms of the license agreement and click next.

STEP 4: You will be prompted for various items pertinent to the server’s operation, including the Network Domain, Server Name, and Administrators Email address. If you know the information fill it in, otherwise just use localhost for the first two items, and put in your email address for the last. Keep for all users on Port 80, as a service Checked. This allows Apache to initialize on startup of your computer.
apache_local.jpg

STEP 5: You will be prompted to select a setup type. For right now choose Typical.

STEP 6: Lastly you will be prompted for the destination folder. By default this is C:\Program Files\Apache Software Foundation, but you may choose install anywhere you like, just make sure you avoid spaces. Click install to complete the installation
Thats it for Apache. Easy wasn’t it? You should see an Apache icon in your system tray (Bottom Right).

apache_systray.jpg

Make sure that you stop and restart Apache to make sure it is running properly. If you fail to do so then later when you install PHP5 it won’t work.

INSTALLING PHP5.2.6 FOR WINDOWS:
 

 

 

STEP 1: Just as you did for the Apache Installation obtain all the resources from the PHP website (http://www.php.net). Make sure that you download the latest version of PHP 5 which is PHP 5.2.6.php1.jpg php_installer1.jpg
STEP 2: Once downloaded Double Click the PHP-5.2.6 Win-32 Installer and you will see a welcome Screen.

php_welcome.jpg
STEP 3: Click Next and Agree to the Terms of the License.

STEP 4: You will be prompted to select the Web Server you wish to setup. Choose Apache 2.2x Module since you have already installed the Apache 2.2+ Server. Click Next.

php_module1.jpg
STEP 5: In the Apache Confiuration Directory choose C:\Program Files\Apache Software Foundation\Apache2.2\, or the install directory where you installed Apache. Click Next and in the choose items to install prompt click next and install PHP on your machine.
Thats it for installing PHP 5.2.6 on your local computer using the MSI installer. Now its time to test and see if the installations actually worked.

Locate the directory where you installed Apache 2.2. By default that directory is C:\Program Files\Apache Software Foundation, but choose the location where you installed it if it was different than the default. Open that folder and look for a folder named htdocs.

Once you have navigated to that folder successfully open up a text editor such as Notepad or Notepad ++ and type in the these lines:

<?php
phpinfo();
?>

Save the page as phpinfo.php in the htdocs folder where you installed Apache. The phpinfo() function offers a plethora of useful information pertinent to your php installation. Lastly open your browser and type: http://localhost/phpinfo.php and if all went well you should see this webpage appear in the browser.

phpinfo.jpg

If you are seeing error messages or nothing at all for the output it is duew to one or more of the following reasons:

Apache was not started or restarted after the build process was complete.
A typing error was introduced into the code in the phpinfo.php file. If a parse error message is resulting in the browers input, then this is almost certainly the case.
Something went wrong during the build process. Consider rebuilding, carefully monitoring for errors.
If you navigate to your start menu, under the Apache HTTP Server 2 menu item you will see that you can test your configuration and monitor the service.

Notes: I have not touched on the php.ini file or the Apache httpd.conf files in this tutorial. In the next tutorial i will help you to understand these two files and how to use them to your advantage.
