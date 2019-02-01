Model
=====

> Intent based automation requires a well structured information model.

The following diagram provides an overview of the information model:

<img src="./assets/entities.svg" alt="Information Model" width="400"/>

The information model or **Model** is divided into administration realms or
**domains**. This allows for sharding the information model into substructures
which can be managed independently from one another if needed.

Model
-----

The model entity is the central entry point to the information required by the
closed-loop automation procedures. It is subdivided into a set of subdomains
which can be administrated independently from one another.

| Attribute | Type           | Description             |
|-----------|----------------|-------------------------|
| Schema    | string         | schema of the model     |
| Name      | string         | name of the model       |
| Domains   | map to Domains | map of names to domains |


Domain
------

A domain is an administrative realm which can be managed independently from
other domains and may serve as a context for sharding the model.

| Attribute     | Type                 | Description                   |
|---------------|----------------------|-------------------------------|
| Name          | string               | name of the model             |
| Catalog       | map to Components    | map of names to components    |
| Architectures | map to Architectures | map of names to architectures |
| Solutions     | map to Solutions     | map of names to solutions     |
| Tasks         | map to Tasks         | map of uuids to tasks         |
| Events        | map to Events        | map of uuids to events        |

A **domain** holds four types of information:

- [**Catalog**](./Model-Catalog.md):
  the catalog holds the templates for all components including
  their version information, their dependencies amongst one another and
  a basic generic configuration. The catalog can therefore be regarded as a
  repository of building blocks for the elements of a solution.

- [**Architectures**](./Model-Architectures.md):
  The architectures are designed to depict what a solution
  should look like and in this way resemble the desired target state of a
  solution. They describe the structure of the solutions by listing the
  required solution elements (which are of a specific component type),
  their element specific configurations including which element will need to
  fulfill the dependencies as defined in the component templates.
  Each solution architecture maintains version information since they will need
  to evolve over time.

- [**Solutions**](./Model-Solutions.md):
  the actual runtime information (current state) of a solution
  and its elements is registered here to allow for closed loop automation.
  It includes information related to the runtime configuration, the status and
  the service endpoints of the elements.

- [**Automation**](./Model-Automation.md):
  For a closed-loop automation it is also necessary to maintain
  information regarding which **tasks** need to be conducted to align the
  current state with the desired target state and react to **events** which are
  triggered by the execution of tasks.

The schema file in swagger: <a href="assets/swagger-model.yaml" target="_blank">swagger-model.yaml</a>
