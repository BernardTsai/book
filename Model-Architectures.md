Domain-Architectures
====================

Architectures are a subset of the [information model](./Model.md) of a
domain describing the **desired** structure and configuration of a solution
with the help of a list configurations for solution elements and their
relationships amongst one another.

<img src="./assets/architecture.svg" alt="Catalog" width="720"/>

The configurations are "design-time" configurations. Since they can only
describe the configuration parameters which are known at the time the
solution is being designed.

Architecture
------------

An architecture is a versioned description of the desired configuration of a
solution. The name of the architecture matches the name of the solution.
It holds a general structured configuration object (with general parameters)
and a set of configurations for solution elements which can be identified by
their names.

| Attribute     | Type                         | Description                         |
|---------------|------------------------------|-------------------------------------|
| Architecture  | string                       | name of the architecture            |
| Version       | string                       | version of the architecture         |
| Configuration | object                       | architecture configuration object   |
| Elements      | map to ElementConfigurations | map of names to configurations      |

ElementConfiguration
--------------------

An ElementConfiguration describes the configuration of a solution element based
on a component type. A solution element may need to comprise several versions of
a component (Clusters) which may require their own specific configurations.

| Attribute     | Type                         | Description                         |
|---------------|------------------------------|-------------------------------------|
| Element       | string                       | name of the solution element        |
| Component     | string                       | name of the component               |
| Configuration | object                       | element configuration object        |
| Clusters      | map to ClusterConfigurations | map of names to configurations      |

ClusterConfiguration
--------------------

A ClusterConfiguration describes the configuration for a cluster within a
solution element for a specific version of a component type.
A cluster has a certain size and should be in a certain state of the lifecycle.
Due to its dependencies to other solution elements it will also have to describe
this information it its relationships attribute.

| Attribute     | Type                              | Description                         |
|---------------|-----------------------------------|-------------------------------------|
| Version       | string                            | version of the component            |
| State         | string                            | desired lifecycle state             |
| Size          | positive integer                  | desired cluster size                |
| Configuration | object                            | cluster configuration object        |
| Relationships | map to RelationshipConfigurations | map of names to configurations      |

RelationshipConfiguration
-------------------------

A RelationshipConfiguration describes the configuration for a relationship
between clusters of related solution elements.

| Attribute     | Type   | Description                       |
|---------------|--------|-----------------------------------|
| Relationship  | string | name of the dependency            |
| Element       | string | name of the referenced element    |
| Version       | string | version of the referenced element |
| Configuration | object | relationship configuration object |
