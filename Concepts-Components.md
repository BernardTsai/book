Components
==========

<div class="subtitle">Everything is a component.</div>

The concept assumes that the technological elements obtained by the
[decomposition](./Concepts-Decomposition.md) of a solution share a set of common
attributes, behaviours and relationships although they may each be of very
different nature. Therefore all technological elements are regarded to be components or to be more precise instances of a component. These component instances may be of specific [type](./Concepts-Service.md) and may form [clusters](clusters)  to ensure service availability.

Structure (C4-Model)
--------------------

The C4-Model structures components into four fundamental aspects which may
evolve independently from one another and are possibly managed by different
roles.

<img src="./assets/images/c4model.svg" alt="C4-Model" width="400"/>

1. **Context:** each component requires a dedicated environment to support the
   way it can evolve along its lifecycle and provide its services.
2. **Core:** each component consists of a core structure which is capable of
   providing the required functionality.
   of the component.  
3. **Configuration:** each component may need to be configured, so that it fits
   into its context and provides its service according to the generic
   requirements of its service consumers.
4. **Content:** each component may have to make use of content information based
   on the usage of the service (in contrast to the configuration information).

The context is managed by the DevOps teams responsible for the corresponding
components. The core structure is provided by the developers of the component
itself. The configuration is defined by the DevOps team responsible for the
component and the content is generated in the course of the interaction of the
component with the service consumers.

Attributes
----------

Instances of a component share following common attributes:

- **Name:** a unique identifier for the instance within the administrative realm
- **Type:** an indicator specifying which type of component the instance has
- **Version:** an indicator following the rules as specified by
  [Semantic Versioning](https://semver.org/), describing which
  [version](./Concepts-Versioning.md) of the component type the instance relates
  to.
- **State:** [lifecycle state](./Concepts-Lifecycle.md) of the instance.
- **Endpoint:** [service interface](./Concepts-Services.md#Endpoint) via with the
[service](./Concepts-Services.md) functionality can be accessed.
- **Configuration:** the [configuration](./Concepts-Configuration.md)
  information controllers require to configure a component instance.

Behaviour
---------

Each component instance will provide a type specific
[service](Concepts-Services.md).
The common behaviour which all instances of components expose in addition to
that is related to the transitions defined in the common
[lifecycle model](Concepts-Lifecycle.md) and a status operation which allows to
determine which lifecycle state a component instance has:

- **Status:** queries the current state of a component instance
- **Create:** provision a component instance as defined in a descriptor
- **Start:** activate a component instance
- **Stop:** deactivate a component instance
- **Configure:** configure an inactive component instance
- **Reconfigure:** configure an active component instance
- **Destroy:** remove an inactive instance
- **Reset:** remove a component instance after it has failed

Relationships
-------------

There are three main types of core relationships defining how component
instances need to interact amongst one another:

- **Runtime-Context:** defining which component environment a component
  requires in order to be instantiated
- **Service-Context:** a service relationship defining which components need to
  provide services to a component so that it is able to provide its own service
- **Cluster-Context:** the component instances providing similar functionality need to coordinate their Lifecycle transitions in order to ensure overall service availability from a cluster perspective
