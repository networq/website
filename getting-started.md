
---
draft: True
author: masterbunny@gmail.com
editor: j.faassen@linkorb.com
notes:  - Priority doc. 
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

"NetworQ Web" is our web-based viewer application. You can configure it to load a Graph of your choice and browse it.

"NetworQ Cli" is a command-line utility used to:
* inspect graphs (list packages, types, nodes)
* install package dependencies

### 1) NetowrQ Web

To install

```
  $ git clone https://github.com/networq/networq-web
  $ cd networq-web # move to the directory
  $ composer install # Install this projects dependencies
  $ cp .env.dist .env # Copy the included `.env.dist` file to `.env`
  
```
The environmental settings may be adjusted in Linux using: 

```
$ edit .env # Adjust for your setup
```
Or by editing the file directly in Windows.

![edit .env](/images/edit_envWin.PNG) 

### 2) Installing NetworQ Cli

Next you must install the command-line utilities + package manager.

To install

```
  $ git clone https://github.com/networq/networq-cli
  $ cd networq-cli
  $ composer install

```


### Starting the server

On the directory networq-web you may run the server using:

```
    $ php -S 0.0.0.0:8080 -t public/
```

Open http://localhost:8181/ in a browser to start browsing the graph.


Alternatively, on the directory networq-web you may run the server using:

```
    $ php -S localhost:54321 -t public/
```

Open http://localhost:54321 in a browser to start browsing the graph.


### Quick start with example data

You can configure the `NETWORQ_GRAPH` variable in the `.env` file to any valid NetworQ package.

If you set `NETWORQ_EXAMPLES=true`, it will also load any example nodes found in the `examples/` directory of the root package.

    $ cd /tmp
    $ git clone git@github.com:networq/holacracy.git
    $ cd holacracy
    $ networq install # install dependencies into packages/

Now configure `NETWORQ_GRAPH` in `.env` of networq-web to `/tmp/holacracy` and start your server.

You should now be able to browse the example nodes in the holacracy package.


<img src="https://github.com/favicon.ico" width="48"> Found a typo or error? [Create a PR](https://github.com/networq/www.networq.io).








