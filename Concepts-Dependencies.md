Dependencies
============

<div class="subtitle">
Components interact along well defined interaction patterns
</div>

There are three main types of relationships between components or instances of
components. These define the rules of how these elements need to interact with
one another and the main reason for requiring an orchestrator to synchronise the
activities of the controllers as type specific management components.

<img src="./assets/images/dependencies.svg" alt="Dependencies" width="360"/>

* [Runtime Context:](./Concepts-Dependencies-Runtime.md)
  runtime environment for components
* [Service Context:](./Concepts-Dependencies-Service.md)
  client-service relationships between components
* [Cluster Context:](./Concepts-Dependencies-Cluster.md)
  interactions within a component cluster

**Runtime Context**

Often components require a specific environment in which they will need to be
provisioned. This is the runtime environment of a component.

Relating this constraint to the [lifecycle model](./Concepts-Lifecycle.md) of
components immediately implies that components can not be created if the
components which are providing their runtime environment are not in the active
state.

Vice versa if a runtime environment leaves the active state it is necessary to
inform the dependent components that they will have to be destroyed as well in
the course of this process.

**Service Context**

Often components require a services from other components in order to be
capable of providing their own service. These backend components are the
service environment of these components.

Relating this constraint to the [lifecycle model](./Concepts-Lifecycle.md) of
components immediately implies that components can not be activated if the
components which are providing their service environment are not in the active
state.

Vice versa if a component of a service environment leaves the active state it is
necessary to inform the dependent components that they will have to be
deactivated as well in the course of this process.

**Cluster Context**

Several component instances of a specific type can group together to form a
[cluster](./Concepts-Cluster.md).

The service [endpoints](./Concepts-Services.md#Endpoint) of component cluster are
exposed by a component cluster in a stable manner ensuring that changes in the
lifecycle state of individual component instances do NOT change the service
endpoint of the whole cluster.

Relating this constraint to the [lifecycle model](./Concepts-Lifecycle.md) of
component instances immediately implies that component instances can not be
activated or deactivated without informing their siblings by triggering a
corresponding reconfigure transition.
