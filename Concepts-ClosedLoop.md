Closed Loop Automation
======================

> Control loop to converge the current state towards the desired target state.

A set of actors are involved in the closed loop automation procedure described
in this subchapter.

Actors
------

**DevOps**

It is a assumed that the administration of the solution providing customer
services is handled by a DevOps team which understands the design of the
solution and can trigger required administrative changes.

This team will also serve as escalation path if the automation procedures
are not able to handle configuration requests even after reiterating the
request a limited amount of times.

**Controllers**

In reality it will be impossible to implement a single automation engine
capable of handling all lifecycle transitions for every component type.
Therefore it is assumed that a set of type specific controllers will be
available which can transition component instances along the transition paths
defined in the [lifecycle model](./Concepts-Lifecycle.md).

These controllers will receive intent based requests which specify the desired
lifecycle state for a component instance. These requests need to to handled in
an fault-tolerant idempotent way so that issues which may have occurred during  
the execution could as a first option be addressed by restating the request.

**Orchestrator**

Controllers specialise on the managing the lifecycle of component instances of
a specific type. Since the components need to interact it is necessary to have
an automation element which aligns the automation procedures between the
various controllers, i.e. the orchestrator.

**Catalog and Repository System**

The solution designers describe the structure of the solution with the help of
a set of descriptors. These also specify which software artefacts are required
by the controllers in the course of the closed loop automation.

The descriptors are stored in the catalog system and the artefacts need to be
uploaded to the repository system.

**Monitoring**

The monitoring system continuously captures the status of the defined component
instances by querying the corresponding controllers and forwarding this
information to the orchestrator.

Closed Loop
-----------

```
Picture
```

Model based closed loop automation makes use of following process steps in order
to implement an intent based solution management approach.

1. **Service Design:** DevOps __onboards__ a service descriptor along with all
   of its corresponding artefacts into a catalog/repository system. It is
   assumed for simplicity reasons that the validity of the service description
   has been ensured by test procedures before the onboarding takes place.
2. **Service Provisioning:**
   DevOps triggers the __provisioning__ of a service
   by detailing parameters for the component instances and passing this way the
   intent, i.e. desired __target state__ of the solution to the orchestrator.
3. **Delta Calculation:**
   The orchestrator compares the desired
   __target state__ with the __current state__, i.e. the current information it
   has of the solution. The differences for each component instance are
   identified and passed as delta list containing information about which
   component instances need to be created, reconfigured or destroyed.
4. **Sequencing:**
   The orchestrator triggers all required lifecycle state
   changes in parallel for each component instance of the delta list.
   The orchestrator calculates the prerequisites for each transition based on
   the relationship information captured in the descriptor and triggers the
   corresponding required transitions.
   This may lead to additional ripple effects as further prerequisites may have
   to be met.
5. **Transitions:**
   The transition requests are forwarded from the orchestrator to the
   corresponding type specific controllers which then transition the component
   instance along the path of the [lifecycle model](./Concepts-Lifecycle.md).
   During this operation the orchestrator informs the monitoring system as well,
   that the specific component instance has a new desired target state and
   should be monitored accordingly.
6. **Monitoring:**
   The monitoring system continuously retrieves state information of each
   component instance by querying their controllers and forwards this
   information to the orchestrator so that it can update its status information
   of the instance specific __current state__ and trigger a new delta
   calculation.

This automation approach constantly compares the __current state__ with a
desired __target state__ and will eventually converge the solution in a fault
tolerant way to the state specified by the intent of the DevOps team.
