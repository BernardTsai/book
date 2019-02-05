Glossary
========

## [Architecture](Model-Architectures.md#Architecture)
An architecture is a versioned description of the desired configuration of a
solution.

## [Catalog](Model-Catalog.md)
The catalog is a subset of the information model of a domain which holds templates (components and their dependencies) for solution elements along with their basic configuration.

## [Cluster](Model-Solutions.md#Cluster)
A Cluster describes the runtime configuration for a cluster within a solution element for a specific version of a component type.  

## [Component](Model-Catalog.md#Component)
A component is a versioned template for a solution element. It describes its basic configuration with the help of a structured object and a set of named dependencies to other components

## [Configuration](Concepts-Configuration.md)
A  configuration describes how to setup a [Solution](Model-Solutions.md#Solution), [Element](Model-Solutions.md#Element), [Cluster](Model-Solutions.md#Cluster), [Relationship](Model-Solutions.md#Relationship) or [Instance](Model-Solutions.md#Instance). A basic configuration is provided by the defintion of a [Component](Model-Catalog.md#Component) in the catalog. Architectures capture design time configurations in the entities: [ElementConfiguration](Model-Architectures.md#ElementConfiguration), [ClusterConfiguration](Model-Architectures.md#ClusterConfiguration) and [RelationshipConfiguration](Model-Architectures.md#RelationshipConfiguration). The actual run-time configuration is held in the entities themselves.

## [Controller](Orchestrator-Controller.md)
A component type specific management component capable of applying the changes to component instances according to the standardised component life cycle model.

## [Orchestrator](Orchestrator.md)
An automation tool which coordinates the versions, configurations and lifecycle states of a set of interdependent components so that a desired target version, configuration and lifecycle state of these components is achieved.

## [Depedency](Model-Catalog.md#Dependency)
A  dependency describes how the containing component relates to other components. It can either be a "context" dependency which defines that the referenced component needs to be "active" before the component can be created, or it may be a "service" dependency which states that the referenced component needs to be "active" before the component can be started.

## [Domain](Model.md#domain)
A domain is an administrative realm which can be managed independently from other domains

## [Element](Model-Solutions.md#Element)
An Element describes the runtime configuration of a solution element based on a component type. A solution element may need to comprise several clusters which resemble versions of a component.

## [Endpoint](Concepts-Services.md#Endpoint)
An Endpoint describes how a service provided by a component can be accessed.

## [Engine](Orchestrator-Engine.md)
The orchestrator engine is responsible for coordinating the lifecycle management activities of the various component specific controllers.

## [Event](Model-Automation.md#Event)
An event notifies about the occurrence of a task related event.

## [Extensions](Orchestrator-Extensions.md)
Extensions enhance the functionality of the orchestrator by augmenting it with custom code.

## [Hook](Orchestrator-Extensions.md)
A hook subscribes to lifecycle events and status information coming from the message bus interface and triggers custom code.

## [Instance](Model-Solutions.md#Instance)
An Instance describes an instance of a cluster of a solution element.

## [Lifecycle Model](Concepts-Lifecycle.md)
A lifecycle model can be represented as a directed graph of states and transitions describing how an instance of a component may evolve in the course of its existence.

## [Model](Model.md)
The information required for the closed-loop automation procedures for managing the lifecycle of solutions.

## [Monitor](Orchestrator-Monitor.md)
The monitoring system is a module of the orchtestrator and continuously compares the current state of instances with the desired target state and if needed triggers compensating measures.

## [Relationship](Model-Solutions.md#Relationship)
A Relationship describes the runtime configuration for a dependency between clusters of related solution elements.

## [Repository](Orchestrator-Repository.md)
The repository is a module of the orchestrator and holds the information required for the closed-loop automation procedures.

## [Solution](Model-Solutions.md#Solution)
A solution entity describes the current configuration and state of a solution which may consist of a number of elements.

## [Task](Model-Automation.md#Task)
A task describes an activity to manipulate a solution or parts of a solution.
