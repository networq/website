
---
draft: True
author: masterbunny@gmail.com
editor: j.faassen@linkorb.com
spellChecked: F
notes:  - Priority doc. Part of Task 1
---

# Create your first Graph

[Getting Started](getting-started.md) will guide you through the installation of NetworQ. With that complete you are ready to create a Graph.


## Worked example

For a work-through example we will create an imaginary school headed by Barak Obama.


1. Create a directory with the name `old-skool-nqp` 
(following the convention to name a package with the tail NetworQ package `nqp`).

2. Create the yaml for this package.

![Create Yaml](/images/createYaml.PNG) 

		populate this with the details e.g.
					name
					description
					license
		dependencies
					neworq:core
					neworq:resource
4. NetworQ install

				will create a dir. packages
				pulled in all the dependencies
				associating existing packages with old-skool 

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








