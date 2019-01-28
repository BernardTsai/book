Domain-Catalog
==============

The catalog is a subset of the [information model](./Model.md) of a
domain which holds templates (components and their dependencies) for solution
elements along with their basic configuration.

<img src="./assets/catalog.svg" alt="Catalog" width="560"/>

Component
--------

A component is a versioned template for a solution element. It describes its
basic configuration with the help of a structured object and a set of named
dependencies to other components

| Attribute     | Type                | Description                  |
|---------------|---------------------|------------------------------|
| Component     | string              | name of the component        |
| Version       | string              | version of the component     |
| Configuration | object              | basic configuration object   |
| Dependencies  | map to dependencies | map of names to dependencies |

Dependency
----------

A dependency describes how the containing component relates to other components.
It can either be a "context" dependency which defines that the referenced
component needs to be "active" before the component can be created,
or it may be a "service" dependency which states that the referenced component
needs to be "active" before the component can be started.
The configuration attribute is a structured object with the basic configuration
for the establishing the component relationship described in the dependency.


| Attribute     | Type                     | Description                                  |
|---------------|--------------------------|----------------------------------------------|
| Name          | string                   | name of the dependency                       |
| Type          | string                   | type of dependency ("context"/"service")     |
| Component     | name of the component    | name of the referenced component             |
| Version       | version of the component | version of the referenced component          |
| Configuration | object                   | basic configuration object of the dependency |
