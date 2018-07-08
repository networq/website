
---
draft: True
author: j.faassen@linkorb.com
editor: masterbunny@gmail.com
spellChecked: F
notes:  - Priority doc
id: concepts
---

# Concepts

NetworQ uses a few concepts you need to understand in order to build your own graphs. An example organisation "OldSkool", an imaginary School with students, teachers, suppliers, parents etc. serves as a model for this explanation.

## Node

All data in NetworQ is contained within a "Node". A node has a name, for example our School has an IT supplier called `SoltechIT`. Every node is part of a package, our School's package is `School:OldSkool`. 

![Node Naming](/images/ConceptsSlide2.PNG) 

The node name and the package name combined give a Fully Qualified Node Name (FQNN), in this case `School:OldSkool:SoltechIT`. Thus this supplier now exists as an entity. Other than the having its own unique identifier, its FQNN, a node doesn't have any other properties of it's own. 

By tagging a node with one or more "Types", the node is given properties. 

## Types

A "Type" defines what properties a node can have. For example, tagging the `School:OldSkool:SoltechIT` node with the `Supplier:Management:SupplierContracts` type allows you to specify the field `contractEndDate` for `SoltechIT`, allowing the contract agreement end date to be linked to that supplier.

Notice that our organisation OldSkool has reached out to use a type held within a different package (`Supplier:Management`). Now that the node SoltechIT is associated with this type all the architecture that comes with this type is now linked to the node. This means that every aspect of supplier management provided by this package, is now available to the School to use.


## Type Names
A type has a name (i.e. `SupplierContracts`) and is part of a package (i.e. `Supplier:Managment`). Combining the Type name and Package Name gives you a Fully Qualified Type Name (FQTN) (i.e. `Supplier:Management:SupplierContracts`).

![Type Naming](/images/ConceptsSlide3.PNG) 

## Managing Types
Types are defined by creating `.yaml` files in the `types/` directory of a package. These are loaded with the package.

Types optionally define a list of Fields for the type. <!-- Types can also be objects held within the database - yes?--->

Nodes tagged with this type will then adopt the listed fields.

![Graphs link Packages](/images/ConceptsSlide4.PNG) 

A Field can be either a `string` (simple text), or a FQTN. When you specify a FQTN for a Field, you
can only assign nodes that are tagged with this type.

A Field can be a single value (default), or a list of values (by appending [] to the end of the Field type definition).

![Fields with single and multiple values](/images/TypesFields.PNG) 

## Tags

A "Tag" is simply the link between a Node and a Type. One Node can contain multiple Tags.

## Package

A "Package" is a reusable set of Types and Nodes. Packages can be shared and live in their own Git Repository.

A Package defines Types (in the package's `types/` directory) using YAML files.

A Package can optionally define a set of `Nodes`. Nodes in packages are therefore, are also reusable allowing you to share reference data or standardized lists (like countries, operating systems, etc.).

A Package can optionally define `Widgets`, which are simple HTML templates (in the `templates/` directory) which get injected into the User Interface when a user is viewing a Node of a given Type.

A Package always has a `package.yaml` file in the root of it's repository. The `package.yaml` file defines the Package's name, description, license etc. And lists an optional set
of dependencies: other packages that this package depends on.

## Graph

When using Networq, you'll almost always interact with a "Graph". A Graph is a container for one or more Packages and their contents (Nodes, Types, Widgets).

A Graph always has exactly 1 "Root Package" which is the main package of your project. For our example this is School:OldSkool. Additionally the graph recursively loads and holds all packages that a parent package has a dependency on. 

![Graphs link Packages](/images/ConceptsSlide5.PNG) 

## Dependencies

For our example we added the Supplier Contract Types that comes as part of the Supplier:Management package, however an institution as complicated as a school will pull in many packages and their dependents.

When one package requires/builds on another, it is called a “Dependency”. Package A depends on Package B. Each package defines it’s own dependencies so that when the package is installed, it’s required dependencies are also automatically installed.

![Packages may depend upon other Packages](/images/ConceptsSlide6.PNG)

For example, the "StudentBody" package would need to hold fields within the type such as student home address. By making use of an existing postal system address package for the country the School is based in, school adminstrators can find each student's full address including post code (zip code), in the address package. 

Similarly the GDPR package may be applied to the parent body, student body, staff and suppliers.

 
