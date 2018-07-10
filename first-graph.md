
---
draft: True
author: masterbunny@gmail.com
editor: j.faassen@linkorb.com
spellChecked: F
notes:  - Priority doc. Part of Task 1 (Task 1 bleeding through to Task 2)
---

# Create your first Graph

[Getting Started](getting-started.md) guides you through the installation of NetworQ. The terms used are covered in [concepts](concepts.md). Assuming that you are familiar with the terms, and have the setup completed, you are ready to create a Graph. A Graph is a container for one or more Packages and their contents, creating the functioning interface for your data.


## Worked example

This work-through will create an imaginary traditional school headed by Barak Obama.

### 1. Create a directory 

The school name provides our package name; `old-skool-nqp` 
(following the convention to name a package with the tail "NetworQ package": `nqp`).

### 2. Create the YAML

The [YAML](https://en.wikipedia.org/wiki/YAML) files in NetworQ are used as your data store, and for configuration. Create a YAML in your directory called package.yaml.

![Create YAML](/images/createYaml.PNG) 

### 3. Populate the YAML relevant details 

For example: 
* name
* description
* license

### 4. Set up dependencies

The ability to use existing packages is a key functionality of NetworQ. For the sake of brevity this example will use a minimal dependency list. A real Graph may adopt many packages.
					
![Set up YAML](/images/createYAML2.PNG)


## Next Steps

<!-- stay DRY where possible, maybe after getting started is approved and proofed copy through? --->

* Set directory to networq-web and run command, in this example the directory containing the old-skool-nqp and follow [2-4](getting-started.md#2.-Install-NetworQ) of installing networq in getting started.

If you followed the [getting started guide]((getting-started.md), these steps should be familiar:

2) [set up the dependencies](getting-started.md#2.-Install-NetworQ).
3) [configure NetworQ to use this old-skool-nqp](getting-started.md#3.-Configure-NewtorQ) as the local package. 


<!-- I had trouble getting old-skool going until I set examples = true, did not test fully to see if this was the fix.

My assumption was that as we are setting up our own graph there is no example data therefore the switch `NETWORQ_EXAMPLES=false`, may be left untouched. --->


4) [start the server](getting-started.md#4.-Start-the-server).

Success will look something like this:
![My First Graph Example Skool](FG_BaseSystem1.PNG)

### 5. Create your first entity


<!--- suggest that when `networq install` grabs packages and creates folder that an 5.1 done at the same time. --->

5.1 Create dir called nodes
5.2 Create nodes to describe our first entity: Barack Obama. Barack

Barak Obama will be the head teacher for our imaginary school. That concepts requires 3 nodes within our package.

![One entity may require many nodes to describe them](/images/FG_1Entity3Nodes.PNG)			

Creating these nodes may be achieved by:

* Creating 3 YAML files in the nodes directory. 

![3 nodes, 3 YAML files](/images/FG_3Nodes3YAML.PNG).

* Or by running a local instance of networq-web and browsing via local host. The `New Node` button provides this functionality:

![Create a new node](/images/FG_CreatingNodeInterface.PNG)


<!-- This example must be wrapped up by reiterating the naming conventions for this example- using same format as the concepts.md --->


## Working Here

			add his links:
			name: 
			image: (linkedin image link give image)
			networq:organization:member
			memberships:
				barack-obama-managemenet:
				management
				networq:organization:membership[]
					group: old-skool:organization:managment
					member: old-skool:organization:barak-obama
					focus: Head Teacher


		NB the [] allows multiple

membership links member to the group (gym card links you to the gym)

10. copied management group - to use - teaching group set up UNDER management group i.e. parent group of teaching group is managment - 
group = teaching
member= sarah-palin ($ is short hand notation to use name)
focus: math

11. Added her as management- Head of Math



<img src="https://github.com/favicon.ico" width="48"> Found a typo or error? [Create a PR](https://github.com/networq/www.networq.io).








