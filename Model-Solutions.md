Domain-Solutions
================

Solutions are a subset of the [information model](./Model.md) of a
domain describing the **current** structure and configuration of a solution
with the help of a list actual configurations for solution elements and their
relationships amongst one another.

<img src="./assets/solution.svg" alt="Solution" width="720"/>

The configurations are "run-time" configurations. Since they also
describe those configuration parameters which can only be known at the time the
solution is being provisioned.

Solution {#Solution}
--------

A solution entity describes the current configuration and state of a solution.
Its name matches the name of the architecture describing its design.

It holds a general structured configuration object (with general parameters)
and a set of configurations for solution elements which can be identified by
their names.

| Attribute     | Type            | Description                    |
|---------------|-----------------|--------------------------------|
| Solution      | string          | name of the solution           |
| Version       | string          | version of the solution        |
| Target        | string          | target state of the solution   |
| State         | string          | state of the solution          |
| Configuration | object          | runtime configuration object   |
| Elements      | map to Elements | map of names to elements       |

Element {#Element}
-------

An Element describes the runtime configuration of a solution element based
on a component type. A solution element may need to comprise several versions of
a component (Clusters) which may require their own specific configurations.

| Attribute     | Type           | Description                  |
|---------------|----------------|------------------------------|
| Element       | string         | name of the solution element |
| Component     | string         | name of the component        |
| Target        | string         | target state of the element  |
| State         | string         | state of the element         |
| Configuration | object         | runtime configuration object |
| Endpoint      | object         | service endpoint             |
| Clusters      | map to Cluster | map of names to clusters     |

Cluster {#Cluster}
-------

A Cluster describes the runtime configuration for a cluster within a
solution element for a specific version of a component type.
A cluster has a certain size and should be in a certain state of the lifecycle.
Due to its dependencies to other solution elements it will also have to describe
this information it its relationships attribute.

| Attribute     | Type                 | Description                   |
|---------------|----------------------|-------------------------------|
| Version       | string               | version of the component      |
| Target        | string               | target state of the cluster   |
| State         | string               | state of the cluster          |
| Min           | positive integer     | minimum cluster size          |
| Max           | positive integer     | maximum cluster size          |
| Size          | positive integer     | desired cluster size          |
| Configuration | object               | runtime configuration object  |
| Endpoint      | object               | service endpoint              |
| Relationships | map to Relationships | map of names to relationships |
| Instances     | map to Instances     | map of names to instances     |

Relationship {#Relationship}
------------

A Relationship describes the runtime configuration for a dependency
between clusters of related solution elements.

| Attribute     | Type   | Description                        |
|---------------|--------|------------------------------------|
| Relationship  | string | name of the dependency             |
| Element       | string | name of the referenced element     |
| Version       | string | version of the referenced element  |
| Target        | string | target state of the relationship   |
| State         | string | state of the relationship          |
| Configuration | object | runtime configuration object       |
| Endpoint      | object | endpoint of the referenced element |

Instance {#Instance}
--------

An Instance describes an instance of a cluster of a solution element.
This comprises it's state, runtime configuration and service endpoint.

| Attribute     | Type                 | Description                       |
|---------------|----------------------|-----------------------------------|
| UUID          | string               | unique identifier of the instance |
| Target        | string               | target state of the instance      |
| State         | string               | state of the instance             |
| Configuration | object               | runtime configuration object      |
| Endpoint      | object               | service endpoint                  |
