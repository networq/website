

## Windows 10 prerequesites run through

If you want to set up a Windows 10 machine to run NetworQ, then you may use the following guide to assist you.


### 1. Download the executable Git Installer for [windows](https://git-scm.com/download/win) 
This provides you with Git bash to use as a command line. Run the executable.

### 2. Download the PHP libraries [latest version](http://php.net/downloads.php)

Select the "Windows downloads".
This will download a zip file which should be extracted to a folder such as:

```
C:\PHP7

```

2a) The PHP.ini file does not come ready to use, out of the box. Select one of these files
![PHP.ini rename for Windows](/images/PHP_ini_2FilesToEdit.PNG) 
and rename your choice to:

```
 PHP.ini
```

2b) Removing the ";" uncomments code in the PHP.ini files. Identify and turn on the switch:
```
extention_dir = "ext"
```
by deleting the semicolon and saving the file.

![PHP.ini edit for Windows](/images/PHP_ini_WindowsSwitch.PNG) Removing the ; uncomments the setting


2c) In the same way switch:
```
 extension=openssl 

 ```
 to active, by deleting the semi colon and saving your change.

2d) Now the PHP libraries must be added to the Windows Path

In the Windows control panel navigate to or search for "advanced system settings"

![PHP Path settings for Windows](/images/PHP_Windows_VariablesSettings.PNG) Navigate to the path settings for Windows

Browse to your PHP library location (the folder where the libraries were unzipped to) and add that to the environment variable path. If you have old PHP libraries this will replace the outdated path.

![Browse your PHP Path](/images/PHP_Windows_VariablesSettings2.PNG) Add the path settings to the Windows environment.

### 3) Download and install composer
Composer can be installed as an [executable](https://getcomposer.org/doc/00-intro.md)

## Run some checks
It is a good idea to check that your setup attempts are working.
In a command window run
```
$ php --ini
```

and you should be provided with the path for the php.ini file that the system is using.


## Congratulations, you are ready to run NetworQ on your windows machine

Return to the main [Set Up](/getting-started.md) flow.



