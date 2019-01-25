Runtime Context
===============

> Components can provide the runtime environment for other components.

Often components require a specific environment in which they will need to be
provisioned. This is the runtime environment of a component.

Relating this constraint to the [lifecycle model](./Concepts-Lifecycle.md) of
components immediately implies that components can not be created if the
components which are providing their runtime environment are not in the active
state.

Vice versa if a runtime environment leaves the active state it is necessary to
inform the dependent components that they will have to be destroyed as well in
the course of this process.

```
PICTURE
```
