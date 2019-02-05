Services
========

<div class="subtitle">Services are the purpose of a component.</div>

Instances of components as technological elements provide a type specific functionality to other components and/or users (service consumers). This functionality is the actual purpose of a component and is called its
"**service**".

<img src="./assets/images/service.svg" alt="Service and Endpoint" width="250"/>

Which kind of functionality is provided is determined by the type and [version](Concepts-Versions.md) of the component following the rules for [Semantic Versioning](https://semver.org).

The interactions between components is governed by the services and the graph of service relationships between different components will be named "**service-network**". It is essential for the service quality from a user
perspective that the service network is always kept in a consistent state
(i.e. no failing service interactions).  

Endpoint{#Endpoint}
-------------------

An Endpoint describes how a service provided by a component can be accessed.
The service consumers need to able to interpret this information in order to
access the [service](./Concepts-Services.md) of the service providing component.

Endpoints may change over time and the distribution of any changes to the
endpoint information needs to be well organised in order to ensure a consistent
service network.
