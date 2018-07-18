
---
status: draft
spellChecked: 
author: masterbunny@gmail.com
editor: j.faassen@linkorb.com
---

# NetworQ Data Structure

The structure of the data managed by NetworQ falls within 3 categories:

* Graph
* Node
* Type


![data model version H](/images/SummaryDataModel.png) 

By adding and removing types you reset the properties of the node. This means the system is responsive from the bottom up.

## Holacracy and NetworQ

[Holocracy](https://www.holacracy.org/) is a institution organisation architecture. The process and philosophy of Hoacracy is one of flat management, providing teams with more autonomy. When an individual within an organisation is empowered to implement their own ideas, that organisation can flourish.

The creators of NetworQ apply this agile structure within their own business. Which is why one of the first packages implemented was the Holacracy package. By installing and applying this you create a simple, dynamic system to self-manage the Holacracy framework. 

# Holacracy Terminology

To be able to apply the principles of Holacracy, you must become familiar with some basic concepts integral to the philosophical framework.





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








