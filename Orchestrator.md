Orchestrator
============

<div class="subtitle">
A plug and play architecture to manage the lifecycle of various types of solution elements in a consistent manner in order to provide a managed customer service.
</div>

The diagram below shows the high-level architecture of the orchestration engine
capable of flexibly coordinating the lifecycles of interdependent solution
elements.

<img src="./assets/images/orchestrator.svg" alt="Orchestrator" width="400"/>

The architecture consists of three layers. The **northbound interfaces** allow for the interaction with the DevOps team and external systems and provide:

  - [**API**](Orchestrator-API.md): an application programming interface via REST
  - [**CLI**](Orchestrator-CLI.md): a command line interface for the operators
  - [**MSG**](Orchestrator-MSG.md): a message bus interface for sending and receiving events

The **core modules** of the orchestrator facilitate the closed loop automation of the lifecycle of solution elements and consist of:

- [**Engine**](Orchestrator-Engine.md): the orchestration engine,
- [**Repository**](Orchestrator-Repository.md): the data store and
- [**Monitor**](Orchestrator-Monitor.md): the monitoring system.

The [**southbound controllers**](Orchestrator-Controller.md) represent specific code fragments capable of managing the lifecycle of solution elements of a specific type according to the common lifecycle model.
