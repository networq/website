
---
draft: True
spellChecked: F
author: masterbunny@gmail.com
editor: j.faassen@linkorb.com
notes:  - Priority doc. 
---

# NetworQ Data Structure

The structure of the data managed by NetworQ falls within 3 categories:

* Graph
* Node
* Type

3 versions of the model follow (vote)

![data model version H](/images/SummaryDataModel.png) 
![data model version I](/images/SummaryModePackagesI.png) 
![data model version J](/images/SummaryModePackagesJ.png) 

By adding and removing types you reset the properties of the node. This means the system is responsive from the bottom up.

<!-- needs a Holacracy relevant example -->
If you add a new employee to your database, the tree of detail that employees should carry with them are added to the node, to allow data to be filtered, visualised, displayed, among other transformations.

For example: names, date of birth, employment date, termination date, cvFileLocation, HR records.


Creating a type creates the template for future types (y?), editing type (legacy data or gone?)




## Running Examples

Remember you may configure the `NETWORQ_GRAPH` variable in the `.env`file to use any valid NetworQ package. Setting `NETWORQ_EXAMPLES=true` loads any example nodes found in the `examples/` directory of the root package. 

Refer to the [Getting Started Guide](getting-started.md) before progressing through this example.

For this guide we are examining and editing the [Holacracy package](https://github.com/networq/holacracy-package).

### Holacracy

Holacracy is a bare bones example of a NetworQ Package. It contains domain specific Types (Circle, Partner, Role).

Graph- Circle
Node- Partner
Type- Role





<img src="https://github.com/favicon.ico" width="48"> Found a typo or error? [Create a PR](https://github.com/networq/www.networq.io).








