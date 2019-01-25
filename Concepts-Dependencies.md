Dependencies
============

> Components interact along well defined interaction patterns.

There are three main types of relationships between components or instances of
components. These define the rules of how these elements need to interact with
one another and the main reason for requiring an orchestrator to synchronise the
activities of the controllers as type specific management components.

* [Runtime Context:](./Concepts-Dependencies-Runtime.md)
  runtime environment for components
* [Service Context:](./Concepts-Dependencies-Service.md)
  client-service relationships between components
* [Cluster Context:](./Concepts-Dependencies-Cluster.md)
  interactions within a component cluster

These concepts are detailed in the corresponding subchapters and also together
determine the design of the orchestration algorithm.
