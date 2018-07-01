---
id: concepts
---

# Concepts

NetworQ uses a few concepts you need to understand in order to build your own graphs.

Below you'll find definitions for NetworQ's terms:

## Node

All data in NetworQ is a "Node". A node has a name (i.e. `mario`). Every node is part of a package (i.e. `acme:example`). The node name and the package name combined give a Fully Qualified Node Name (FQNN) (i.e. `acme:example:mario`).

Other than the name/FQNN, a node doesn't have any properties of it's own. A Node can be tagged with one or more Types, which give the node it's available properties. For example, tagging the `acme:example:mario` node with the `acme:example:character` type allows you to specify the `debut` field for Mario, linking it to the game that Mario debuted in.

## Types

A "Type" defines what properties a Node can have. A type has a name (i.e. `vegetable`) and is part of a package (i.e. `acme:food`). Combining the Type name and Package Name gives you a Fully Qualified Type Name (FQTN) (i.e. `acme:food:vegetable`).

Types are defined by creating `.yaml` files in the `types/` directory of a package. They are automatically loaded when the package is loaded.

Types optionally define a list of Fields for the type. Only nodes tagged with this type will have the listed fields.

A Field can be either a `string` (simple text), or a FQTN. When you specify a FQTN for a Field, you
can only assign nodes that are tagged with this type.

A Field can be a single value (default), or a list of values (by appending [] to the end of the Field type definition).

## Tags

A "Tag" is simply the link between a Node and a Type. One Node can contain multiple Tags.

## Package

A "Package" is a reusable set of Types and Nodes. Packages can be shared and live in their own Git Repository.

A Package defines Types (in the package's `types/` directory) using YAML files.

A Package can optionally define a set of `Nodes`. Nodes in packages are therefor also reusable and lets you share reference data or standardized lists (like countries, operating systems, etc).

A Package can optionally define `Widgets`, which are simple HTML templates (in the `templates/` directory) which get injected into the User Interface when a user is viewing a Node of a given Type.

A Package always has a `package.yaml` file in the root of it's repository.
The `package.yaml` file defines the Package's name, description, license etc. And lists an optional set
of dependencies: other packages that this package depends on.

## Graph

When using Networq, you'll almost always interact with a "Graph". A Graph is a container for one or more Packages and their contents (Nodes, Types, Widgets).

A Graph always has exactly 1 "Root Package" which is the main package of your project. Additionally the graph recursively loads and holds all packages that a parent package has a dependency on.