Cluster Context
===============

> Component instances interact in clusters to ensure service availability.

Several component instances of a specific type can group together to form a
[cluster](./Concepts-Cluster.md).

The service [endpoints](./Concepts-Endpoints.md) of component cluster are
exposed by a component cluster in a stable manner ensuring that changes in the
lifecycle state of individual component instances do NOT change the service
endpoint of the whole cluster.

Relating this constraint to the [lifecycle model](./Concepts-Lifecycle.md) of
component instances immediately implies that component instances can not be
activated or deactivated without informing their siblings by triggering a
corresponding reconfigure transition.

```
PICTURE
```
