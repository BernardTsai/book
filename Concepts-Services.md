Services
========

> Services are the purpose of a component

Components as technological elements provide a type specific functionality to
other components and/or users (service consumers).
This functionality is the actual purpose of a component and is called its
"**service**".

Which kind of functionality is provided is determined by the type and
[version](Concepts-Versions.md) of the component following the rules of
[Semantic Versioning](https://semver.org).

The interactions between components is governed by the services and the graph of
service relationships between different components will be named
"service-network". It is essential for the service quality from a user
perspective that the service network is always kept in a consistent state
(i.e. no failing service interactions).  

```

PICTURE

```
