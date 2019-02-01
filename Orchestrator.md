Orchestrator Architecture
=========================

> A plug and play architecture to manage the lifecycle of various types of
solution elements in a consistent manner in order to provide a managed customer
service.

The diagram below shows the high-level architecture of the orchestration engine
capable of flexibly coordinating the lifecycles of interdependent solution
elements.

<img src="./assets/orchestrator.svg" alt="Orchestrator" width="620"/>

The architecture consists of three main elements:

Interfaces
----------
These allow for the interaction with the DevOps team and external systems and provide:

  - **API**: an application programming interface via REST
  - **CLI**: a command line interface for the operators
  - **BUS**: a message bus interface for sending and receiving events

Engine
------
The engine is the core element of the orchestrator which stores its state
in a model. The monitor continuously checks if the current state is matching
the desired state.

- **Model**: the data store
- **Engine**: the orchestration engine
- **Monitor**: the monitoring system


Controllers
-----------
The controllers a specific code fragments capable of managing the lifecycle
of solution elements of a specific type according to the common lifecycle
model.
