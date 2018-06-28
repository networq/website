---
draft: True
author: masterbunny@gmail.com
editor: j.faassen@linkorb.com
notes: - This is a fairly ad-hoc document. A compile bin of issues that may need full documentation at some point.
---


# Trouble Shooting

## Step 1

Verify that all prerequisite components are installed as per the [getting started guide](getting-started.md)

## Step 2

Identify the component that is failing. The PHP runtime environment must work with Composer.
The two components NetworQ Web and NetworQ Cli must both be present.

To use NetworQ web locally, your machine must have firewall settings to allow ports to be accessed.

### Need to know

* In windows directory slashes are `\` while on Linux and Mac they are `/`. If something doesn't work, try using the "other" option. 
* Editing a PATH variable only takes effect the next time bash starts. It is possible that the command line needs restarting or if all else fails, try restarting the whole machine.


Browse the list below for some common issues.

### No Local NetowrQ Package

A screen such as this is expected when there are no Graphs available to display in the current directory.

![No local package available](/images/TS_NoPackage.PNG) 

### Issues Starting the Server

On the directory networq-web you may run the server using:

```
    $ php -S 0.0.0.0:8080 -t public/
```

Open http://localhost:8181/ in a browser to start browsing the graph.

If this does not work try:

```
	$ php -S localhost:54321 -t public/

```
Open http://localhost:54321 in a browser to start browsing the graph.

### Other issues

![Needs write up](/images/TS_ComposerError.PNG) 
![Needs write up](/images/TS_composerFail.PNG) 
![Needs write up](/images/TS_ComposerFail_PoorPHPLibSet.PNG) 

<img src="https://github.com/favicon.ico" width="48"> Found a typo or error? [Create a PR](https://github.com/networq/www.networq.io).








