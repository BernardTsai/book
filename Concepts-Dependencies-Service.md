Service Context
===============

> Components can provide backend services for other components.

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

```
PICTURE
```
