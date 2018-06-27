
## Windows 10 prerequisites run through

To set up a Windows 10 machine to run NetworQ, use the following guide.


### 1. Install Git 

[Git Installer for Windows](https://git-scm.com/download/win) 
Download and run the executable.
This provides you with Git bash to use as a command line. 


### 2. Install the PHP Runtime

Use the [latest version](http://php.net/downloads.php)
Select the "Windows downloads".
This will download a zip file which should be extracted to a folder such as:

```
C:\PHP7

```

2a) The PHP.ini file does not come ready to use, out of the box. 

Select either one of these files:

![PHP.ini rename for Windows](/images/PHP_ini_2FilesToEdit.PNG) 

and rename your choice to:

```
 PHP.ini
```

2b) Removing the semicolon uncomments code in the PHP.ini files. 

Identify and turn on the switch:
```
extention_dir = "ext"
```
by deleting the semicolon and saving the file.

![PHP.ini edit for Windows](/images/PHP_ini_WindowsSwitch.PNG) 

Removing the ";"" uncomments the setting.


2c) In the same way switch:
```
 extension=openssl 

 ```
 to active, by deleting the semicolon and saving your change.


2d) Now add the PHP runtime to the Windows Path.

In the Windows control panel navigate to or search for "advanced system settings"

![PHP Path settings for Windows](/images/PHP_Windows_VariablesSetings.PNG) 

Navigate to the path settings for Windows

Browse to your PHP runtime location (the folder where you unzipped to), and add that to the environment variable path. If you have older PHP versions this will replace the outdated path.

![Browse your PHP Path](/images/PHP_Windows_VariablesSetings2.PNG) 

Add the path settings to the Windows environment.

### 3) Install composer

Download Composer as an [executable](https://getcomposer.org/doc/00-intro.md).
Run the .exe to install.

## Run some checks
It is a good idea to check that your setup attempts are working.

### PHP check
In a command window run:
```
$ php --ini
```

To see the path for the php.ini file that the system is using.

### Composer check

In a command window run:
```
$ composer -v

```
The response should look something like this:

![Verify Composer Install](/images/CheckYourComposerVersion.PNG) 


## Congratulations, you are ready to run NetworQ on your windows machine

Return to the main [Set Up](/getting-started.md) flow.


![Octocat](/images/Octocat.png){:height="360px" width="360px"} Found a typo or error? Fork and edit this document.



