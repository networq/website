
---
draft: True
author: masterbunny@gmail.com
editor: j.faassen@linkorb.com
spellChecked: Y
notes:  - Priority doc. Part of Task 1
---

# Create your first Graph

[Getting Started](getting-started.md) guides you through the installation of NetworQ. The terms used are covered in [concepts](concepts.md). Assuming that you are familiar with the terms, and have the setup completed, you are ready to create a Graph. A Graph is a container for one or more Packages and their contents, creating the functioning interface for your data.


## Worked example

This work-through will create an imaginary school headed by Barack Obama.

### 1. Create a directory 

The school name provides our package name; `old-skool-nqp` 
(following the convention to name a package with the tail "NetworQ package": `nqp`).

### 2. Create the YAML package file

The [YAML](https://en.wikipedia.org/wiki/YAML) files in NetworQ are used as your data store, and for configuration. Create a YAML in your directory called package.yaml.

![Create YAML](/images/createYaml.PNG) 

### 3. Populate the YAML relevant details 

For example: 
* name
* description
* license

### 4. Set up dependencies

The ability to use existing packages is a key functionality of NetworQ. For the sake of brevity, this example will use a minimal dependency list. A real Graph may adopt many packages.

* Complete as shown:

  ```yaml
  name: old-skool:organization
	description: Old Skool Organization Graph
	license: MIT
	dependencies:
  networq:core: latest # essential
  networq:resource: latest
  networq:organization: latest
  networq:linkedin: latest
  networq:skype: latest
  networq:contract: latest
  ```
* Set directory to old-skool-nqp and run the command `networq install`.

### 5. Configure NetworQ to run your package

<!-- This section is repetition from getting started - need a DRY methodology applied here --->

Using the directory containing your old skool package, following [2-4](getting-started.md#Apply-a-Package) of Applying a Package in Getting Started.
5.1) [set up the dependencies](getting-started.md#2.-Install-NetworQ).
5.2) [configure NetworQ](getting-started.md#3.-Configure-NewtorQ) to use this old-skool-nqp as the local package. 
5.3) [start the server](getting-started.md#4.-Start-the-server).

Success will look something like this:
![My First Graph Example Skool](/images/FG_BaseSystem1.PNG)


### 6. Git Ignore

NetworQ installed dependent packages into a package directory. Rather than push these back to git hub it is best to set up a git ignore. In the old-skool-nqp directory, set up a git ignore file for the packages directory:
`packages/`.

### 7. Create your first entity

#### 7.1 Create a directory called `nodes`.


#### 7.2 Create nodes to describe our first entity: Barack Obama. 

<!-- NB this flow does not include creation of types- this must be dealt with in another flow --->

Barack Obama will be the head teacher for our imaginary school. That concept requires 3 nodes within our package.

Barack is an individual. Management is a group and School is an organization. The management and organisation nodes are inherited from existing packages and so provide various types.

	
Creating these nodes may be achieved by applying the following techniques:

* Creating 3 YAML files in the nodes directory. 

![3 nodes, 3 YAML files](/images/FG_3Nodes3YAML.PNG).

* Or by running a local instance of networq-web and browsing via localhost. The `New Node` button provides this functionality:

![Create a new node](/images/FG_CreatingNodeInterface.PNG)

#### 7.3 Populate the YAML Node files

* old-skool.yaml

	- This YAML must describe the organization
	- Complete as shown:

```yaml
networq:core:node:
name: Old Skool
  description: This is the Old Skool organization
networq:organization:organization: ~
networq:organization:group: ~
```

* management.yaml

	- This YAML must describe the management group
	- Complete as shown:

```yaml

networq:core:node:
name: Management group
networq:organization:group:
  parentGroup: old-skool:organization:old-skool

```


* barack-obama.yaml

	- This YAML must describe Barack Obama and his position in the school
	- Complete as shown:

```yaml
  networq:core:node:
  name: Barack Obama
  image: (enter URL)
networq:organization:member:
  memberships:
    barack-obama-management:
      networq:organization:membership:
        group: old-skool:organization:management
        member: old-skool:organization:barack-obama
        focus: Head teacher
 ```

### 8. Create your second entity

To reinforce the concept, and introduce some shortcodes, let's give the school a teacher. Sarah Palin will be our Head of Mathematics and Barack Obama's assistant head. Sarah will, therefore, belong to more than one group, the management group, and the teaching group.

#### 8.1 Create the nodes for your entity
The management group already exists for Sarah to join however, we need to create a teaching group. The teaching group, as per a traditional school hierachy, sits under the management group.

* teaching.yaml

	- This YAML must describe the teaching group
	- Complete as shown:

```yaml
networq:core:node:
name: Teaching group
networq:organization:group:
  parentGroup: old-skool:organization:management
 ```

* sarah-palin.yaml

	- This YAML must describe Sarah Palin and her position within the school
	- Complete as shown:

```yaml
networq:core:node:
  name: Sarah Palin
  image: (enter URL)
networq:organization:member:
  memberships:
    ~teaching:
      networq:organization:membership:
        group: old-skool:organization:teaching
        member: $
        focus: Math
    ~management:
      networq:organization:membership:
        group: old-skool:organization:management
        member: $
        focus: Head of Math
```

Notice the use of $ here as shortcode to apply the document name. Similarly [] signifies many.
networq:organization:membership[], for example, denotes multiple memberships.

## Congratulations

You have created your first graph and applied some of the basic concepts involved in making use of existing packages. This system may be used for myriad purposes. One of the early applications developed is for institutional management applying the [Holacracy](https://github.com/networq/holacracy-nqp) architecture.

<img src="https://github.com/favicon.ico" width="48"> Found a typo or error? [Create a PR](https://github.com/networq/www.networq.io).








