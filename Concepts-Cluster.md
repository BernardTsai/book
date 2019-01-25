Cluster
========

> Clusters prevent single points of failure for services.

Several component instances of a specific type can group together to form a
cluster. These clusters follow the same [lifecycle model](./Concepts-Lifecycle)
as individual components instances.

The service [endpoints](./Concepts-Endpoints.md) of component instances are
exposed by a component cluster in a stable manner ensuring that changes in the
lifecycle state of individual component instances do NOT change the service
endpoint of the whole cluster.

This allows service consumers to access a service independent of the
availability of a single component instance. Service consumers should therefore
only bind to the service endpoints of a component cluster and not to the
endpoints of individual component instances.

The only times a service endpoint of a component cluster changes is when it
transitions to or from the **active** state.

```

PICTURE

```
