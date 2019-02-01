Application Programming Interface
=================================

> The orchestrator API exposes all required capabilities for the lifecycle
  automation of solutions covering the sourcing, design and operations phase
  to external systems via REST interface.

 Management
-----------

The API will need to support following administrative use cases to facilitate
the management of independent domains by a DevOps team:

- **DomainList**: list all the available domains
- **DomainCreate**: create a new domain
- **DomainDelete**: delete a domain
- **DomainShow**: display domain information

Catalog Management
------------------

Catalog management is conducted in the context of a specific domain.
The API will need to support the following use cases for the sourcing phase
to support the management of templates for components.

- **ComponentList**: list all the available components in a domain
- **ComponentCreate**: define a new component for a domain
- **ComponentDelete**: delete a component from a domain
- **ComponentShow**: display information of a component in a domain

Component templates are regarded to be immutable. Therefore no update operations
are provided for components.

It is regarded to be an error if:
- an unknown domain is referenced,
- a component references unknown components,
- an attempt is made to redefine a component
- an unknown component is referenced when intending to show or delete a
  component

Architecture Management
-----------------------

Architecture Management is also conducted in the context of a specific domain.
The API will need to support the following use cases for the design phase
to support the management of solution architectures.

- **ArchitectureList**: list all the available architectures in a domain
- **ArchitectureCreate**: define a new architecture for a domain
- **ArchitectureDelete**: delete an architecture from a domain
- **ArchitectureShow**: display information of an architecture in a domain

Architectures are regarded to be immutable. Therefore no update operations
are provided for architectures.

It is regarded to be an error if:
- an unknown domain is referenced,
- an architecture definition is inconsistent,
- an attempt is made to redefine an architecture
- an unknown architecture is referenced when intending to show or delete an
  architecture

Solution Management
-----------------------

Solution Management is also conducted in the context of a specific domain.
The API will need to support the following use cases for the operations phase
to support the management of solutions.

- **SolutionList**: list all the available solutions in a domain
- **SolutionCreate**: define a new solution for a domain from an architecture
  blueprint
- **SolutionUpdate**: update an existing solution of a domain based on the
  information provided in an architecture blueprint
- **SolutionDelete**: delete a solution from a domain
- **SolutionShow**: display information of a solution in a domain
- **ElementList**: list all the available elements of a solutions in a domain
- **ElementUpdate**: update an existing element of a solution in a domain
  based on the information provided in a configuration object
- **ElementDelete**: delete an element of a solution from a domain
- **ElementShow**: display information of an element of a solution in a domain
- **ClusterList**: list all the available clusters of an element of a solutions
  in a domain
- **ClusterUpdate**: update an existing cluster of an element of a solution in a
  domain based on the information provided in a configuration object
- **ClusterDelete**: delete a cluster of an element of a solution from a domain
- **ClusterShow**: display information of a cluster of an element of a solution
  in a domain
- **InstanceList**: list all the available instances of a clusters of an element
  of a solutions in a domain
- **InstanceUpdate**: update an existing instance of a cluster of an element of
  a solution in a domain based on the information provided in a configuration
  object
- **InstanceDelete**: delete an instance of a cluster of an element of a solution f
  rom a domain
- **InstanceShow**: display information of an instance of a cluster of an element
  of a solution in a domain

It is regarded to be an error if:
- an unknown domain is referenced,
- an unknown architecture blueprint is referenced,
- an unknown solution is referenced when intending to show, delete or update a
  solution
- an unknown element is referenced when intending to show, delete or update an
  element
- an unknown cluster is referenced when intending to show, delete or update a
  cluster
- an unknown instance is referenced when intending to show, delete or update an
  instance
