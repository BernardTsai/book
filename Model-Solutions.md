Domain-Solutions
================

Solutions are a subset of the [information model](./Model.md) of a
domain describing the **current** structure and configuration of a solution
with the help of a list actual configurations for solution elements and their
relationships amongst one another.

The configurations are "runtime" configurations. Since they also
describe those configuration parameters which can only be known at the time the
solution is being provisioned.

Solution
--------

A solution entity describes the current configuration and state of a solution.
Its name matches the name of the architecture describing its design.

It holds a general structured configuration object (with general parameters)
and a set of configurations for solution elements which can be identified by
their names.

| Attribute     | Type            | Description                    |
|---------------|-----------------|--------------------------------|
| Solution      | string          | name of the solution           |
| Configuration | object          | runtime configuration object   |
| Elements      | map to Elements | map of names to elements       |

Element
-------

An Element describes the runtime configuration of a solution element based
on a component type. A solution element may need to comprise several versions of
a component (Clusters) which may require their own specific configurations.

| Attribute     | Type           | Description                  |
|---------------|----------------|------------------------------|
| Element       | string         | name of the solution element |
| Component     | string         | name of the component        |
| Configuration | object         | runtime configuration object |
| Endpoint      | object         | service endpoint             |
| Clusters      | map to Cluster | map of names to clusters     |

Cluster
-------

A Cluster describes the runtime configuration for a cluster within a
solution element for a specific version of a component type.
A cluster has a certain size and should be in a certain state of the lifecycle.
Due to its dependencies to other solution elements it will also have to describe
this information it its relationships attribute.

| Attribute     | Type                 | Description                   |
|---------------|----------------------|-------------------------------|
| Version       | string               | version of the component      |
| State         | string               | desired lifecycle state       |
| Size          | positive integer     | desired cluster size          |
| Configuration | object               | runtime configuration object  |
| Endpoint      | object               | service endpoint              |
| Relationships | map to Relationships | map of names to relationships |
| Instances     | map to Instances     | map of names to instances     |

Relationship
------------

A Relationship describes the runtime configuration for a relationship
between clusters of related solution elements.

| Attribute     | Type   | Description                  |
|---------------|--------|------------------------------|
| Relationship  | string | name of the dependency       |
| Configuration | object | runtime configuration object |

Instance
--------

An Instance describes an instance of a cluster of a solution element.
This comprises it's state, runtime configuration and service endpoint.

| Attribute     | Type                 | Description                       |
|---------------|----------------------|-----------------------------------|
| UUID          | string               | unique identifier of the instance |
| State         | string               | current lifecycle state           |
| Configuration | object               | runtime configuration object      |
| Endpoint      | object               | service endpoint                  |
