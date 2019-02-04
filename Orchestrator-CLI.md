Command Line Interface
======================

<div class="subtitle">
The orchestrator CLI exposes all required capabilities for the lifecycle automation of solutions covering the sourcing, design and operations phase to the DevOps team with console access.
</div>

The command line interface is exposed to the DevOps team and serves as a gateway to expose the capabilities of the orchestration engine.

<img src="./assets/images/cli.svg" alt="Command Line Interface" width="560"/>

The CLI provides commands to

- support the administration,
- manage templates in a catalog,
- manage architectures and configurations and
- manage the lifecycle of solutions.

---

**Administration**

The API will need to support following administrative use cases to facilitate
the management of independent domains by a DevOps team:

- **ResetModel**: reset model in the repository to initial state
- **StoreModel**: create model from yaml data and store it into the repository
- **RetrieveModel**: retrieve model from the repository as yaml data
- **ListDomains**: list all the available domains
- **StoreDomain**: create a new domain from yaml data and store it in the repository
- **RetrieveDomain**: retrieve domain from the repository as yaml data
- **RemoveDomain**: remove domain from the repository

---

**Catalog Management**

Catalog management is conducted in the context of a specific domain.
The API will need to support the following use cases for the sourcing phase
to support the management of templates for components.

- **ListComponents**: list all the available components in a domain
- **ListComponentVersions**: list all the available versions of a component in a domain
- **StoreComponent**: create a new component from yaml data and store it in the repository
- **RetrieveComponent**: retrieve component from the repository as yaml data
- **RemoveComponent**: remove component from the repository

Component templates are regarded to be immutable. Therefore no update operations
are provided for components.

It is regarded to be an error if:
- an unknown domain is referenced,
- a component references unknown components,
- an attempt is made to redefine a component or
- an unknown component is referenced when intending to show or delete a
  component.

---

**Architecture Management**

Architecture Management is also conducted in the context of a specific domain.
The API will need to support the following use cases for the design phase
to support the management of solution architectures.

- **ListArchitectures**: list all the available architectures in a domain
- **ListArchitectureVersions**: list all the available versions of an architecture in a domain
- **StoreArchitecture**: create a new architecture from yaml data and store it in the repository
- **RetrieveArchitecture**: retrieve architecture from the repository as yaml data
- **RemoveArchitecture**: remove architecture from the repository

Architectures are regarded to be immutable. Therefore no update operations
are provided for architectures.

It is regarded to be an error if:
- an unknown domain is referenced,
- an architecture definition is inconsistent,
- an attempt is made to redefine an architecture or
- an unknown architecture is referenced when intending to show or delete an
  architecture.

---

**Solution Management**

Solution Management is also conducted in the context of a specific domain.
The API will need to support the following use cases for the operations phase
to support the management of solutions.

- **ListSolutions**: list all the available solutions in a domain
- **StoreSolution**: create a new solution from yaml data and store it in the repository
- **RetrieveSolution**: retrieve solution from the repository as yaml data
- **RemoveSolution**: remove solution from the repository
- **ModifySolution**: create a new solution or update an existing solution based on the information provided in an architecture blueprint
- **ListElements**: list all the available elements in a solution
- **RetrieveElement**: retrieve element from the repository as yaml data
- **ModifyElement**: update an existing element based on the information provided in a configuration object
- **ListClusters**: list all the available clusters of an element
- **RetrieveCluster**: retrieve cluster from the repository as yaml data
- **ModifyCluster**: update an existing cluster based on the information provided in a configuration object
- **ListInstances**: list all the available instances of a cluster
- **RetrieveInstance**: retrieve instance from the repository as yaml data
- **ModifyInstance**: update an existing instance based on the information provided in a configuration object

It is regarded to be an error if:
- an unknown domain is referenced,
- an unknown architecture blueprint is referenced,
- an unknown solution is referenced when intending to retrieve or update a
  solution,
- an unknown element is referenced when intending to retrieve or update an
  element,
- an unknown cluster is referenced when intending to retrieve or update a
  cluster or
- an unknown instance is referenced when intending to retrieve or update an
  instance.

---

**Automation**

Automation is also conducted in the context of a specific domain.
The API will need to provide visibility and operational control over all the tasks being executed in order to manage the lifecycle of a solution.

- **ListTasks**: list all toplevel tasks in a domain (optionally matching a certain request ID)
- **RetrieveTask**: retrieve task from the repository as yaml data
- **TerminateTask**: stop a task in a domain
- **ListEvents**: list all events related to a task in a domain
- **RetrieveEvent**: retrieve event from the repository as yaml data

It is regarded to be an error if:
- an unknown domain is referenced,
- an unknown reference ID is used,
- an unknown task is referenced when intending to retrieve or terminate a
  task or list the corresponding events or
- an unknown event is referenced when intending to retrieve an
  event.
