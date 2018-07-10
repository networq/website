
---
draft: True
author: masterbunny@gmail.com
editor: j.faassen@linkorb.com
spellChecked: F
notes:  - Priority doc. Part of Task 1
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

<!--- stay DRY where possible, maybe after getting started is approved and proofed copy through? --->

* Follow 2-4 of [getting started](getting-started.md)



### 5. **********

Run the `networq install` command on your local directory, in this example old-skool-nqp. The installation will create a directory "packages" and import all the dependency packages for your Graph.
				

5. Use nework-web to view the newly created package
				edit files as per 3 in getting started


 = Created a Graph


(NB so far there are no nodes- there are types that came in with the packages)

6. create dir called nodes
7. add old-skool yaml file
8. set up details for organisation in yaml
			name
			description
			Made old-skool organisation AND a group

	by pulling in "group" - then had to define the parent group old-skool:organization:old-skool


	[every group has memberships]

9. Create node Barrack Obama
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








