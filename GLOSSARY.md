## [Architecture](Model-Architectures.md#Architecture)
An architecture is a versioned description of the desired configuration of a
solution.

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

## [Element](Model-Solutions.md#Element)
An Element describes the runtime configuration of a solution element based on a component type. A solution element may need to comprise several clusters which resemble versions of a component.

## [Event](Model-Automation.md#Event)
An event notifies about the occurrence of a task related event.

## [Instance](Model-Solutions.md#Instance)
An Instance describes an instance of a cluster of a solution element.

## [Relationship](Model-Solutions.md#Relationship)
A Relationship describes the runtime configuration for a dependency between clusters of related solution elements.

## [Solution](Model-Solutions.md#Solution)
A solution entity describes the current configuration and state of a solution which may consist of a number of elements.

## [Task](Model-Automation.md#Task)
A task describes an activity to manipulate a solution or parts of a solution.
