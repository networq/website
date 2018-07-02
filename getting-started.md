
---
draft: True
author: masterbunny@gmail.com
editor: j.faassen@linkorb.com
spellChecked: F
notes:  - Priority doc, can't get second local host to render on gh as sub-bullet (!)
---

# Getting started

## Prerequisites for Installing NetworQ

The following prerequisites must be met before undertaking the installation:

1) You are familiar with using [Git](https://git-scm.com/)

2) You are familiar with editing [YAML](https://wikipedia.org/wiki/YAML)

3) You are able to run ([minimum version 7](http://php.net/downloads.php)) [PHP](https://php.net) applications on your machine.

4) You are able to run [Composer](https://getcomposer.org/)
NB further system-dependent instructions for installing composer are available [here](https://getcomposer.org/doc/00-intro.md)

If one or more of these conditions are not met, don't worry. Rather, check out the [demo](demo.html) installation instead!


## Install

Two items are required:

* "NetworQ Web" is our web-based viewer application. You can configure it to load a Graph of your choice and browse it.

* "NetworQ Cli" is a command-line utility used to:
	- inspect graphs (list packages, types, nodes)
	- install package dependencies

### 1) Install NetowrQ Web

* To install, use a command prompt to run:

```
  $ git clone https://github.com/networq/networq-web
  $ cd networq-web # move to the directory
  $ composer install # Install this projects dependencies
  $ cp .env.dist .env # Copy the included `.env.dist` file to `.env`
  
```
### 2) Install NetworQ Cli

Next, install the command-line utilities + package manager.

* Use a command prompt to run:

```
  $ git clone https://github.com/networq/networq-cli
  $ cd networq-cli
  $ composer install

```

## Apply a Package

A NetworQ package must exist. For this example we will use the [Holacracy Package](https://github.com/networq/holacracy-package).

### 1) Clone the package

* Clone the package from Git using a command window directed at the folder location you want to store the clone in:

```
$ git clone https://github.com/networq/holacracy-package

```

### 2) Install NetworQ

Install NetworQ to run this package. 

* Change directory of the command window, to the folder containing your package, in this example the holacracy-package and run:

```
$ networq install # install dependencies into packages

```


## 3) Configure NewtorQ to use the package

You may configure the `NETWORQ_GRAPH` variable in the `.env` file to any valid NetworQ package.


* The environmental settings may be adjusted using the command prompt: 

```
$ edit .env # Adjust for your setup
```

<!-- Joost this is from your email, I assume that it is valid for Linux/Macs --->

* Define the settings via the command prompt:

```
ini
NETWORQ_GRAPH=C:\Users\bunny\Documents\GitHub\holacracy-package
NETWORQ_EXAMPLES=true

```
* Or edit the file directly. Browse to the file:


![edit .env](/images/edit_envWin.PNG) 

	- Set the value of NETWORQ_GRAPH to the folder containing the package.
	- Set the NETWORQ_EXAMPLES to true.
	- Save and close the file.


![edit .env](/images/Install4_Holacracy.PNG) 

Setting `NETWORQ_EXAMPLES=true` loads any example nodes found in the `examples/` directory of the root package.



### Start the server

* Using a command prompt pointed at the directory **networq-web** run the server using:

```
    $ php -S 0.0.0.0:8080 -t public/
```
* Open http://localhost:8080/ in a browser to start browsing the graph.

	- As ports may be pre-assigned you may use this alternative:

```
    $ php -S localhost:54321 -t public/

```
  - Open http://localhost:54321 in a browser to start browsing the graph.

### Quick start with example data


You should now be able to browse the example nodes in the holacracy package.

![example nodes](/images/Holacracy1.PNG) 

To work with the data structure and learn more about the different components continue with this [Holacracy](exampleHolacracy.md) example.

Or, take an [abstract overview](concepts.md) of the components involved.

<img src="https://github.com/favicon.ico" width="48"> Found a typo or error? [Create a PR](https://github.com/networq/www.networq.io).








