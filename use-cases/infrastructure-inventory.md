---
id: infrastructure-inventory
---

# Use-case: Infrastructure inventory

Using Networq you can create a Graph that contains every detail about your infrastructure. You can define Hosts (with their ip-adresses, operating system details, tags) and HostGroups which can serve as Inventory input to common configuratino management tools like Ansible, Puppet, Chef, etc.

Holding the inventory in Networq instead of tool-specific formats allow you to re-use and single-source your infrastructure data for many other use-cases. You could attach VPS pricing information for budgeting, tags for compliance, monitoring rules as input for sensu/nagios/etc, etc etc. 

Combining these configurations into one makes sure that all your tools and services are guaranteed to be in sync.