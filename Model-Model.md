Entity: Model
=============

> The model entity comprises all information required to manage the lifecycle of inter-dependent components.

Attributes
----------

- **Schema**: a string describing the schema of the model
- **Name**: a string identifying the model
- **Domains**: a map of [domain](./Model-Domain.md) entities

Methods
-------

**Factory methods**

- **GetModel**: central entry point to retrieve the model entity
- **NewModel**: creates a new model

**Instance methods**

- **Reset**: reset a model to its initial values
- **Show**: displays the model information as json
- **Load**: loads the model from a yaml file
- **ListDomains**: lists the names of all domains of a model
- **GetDomain**: get a domain by name
- **AddDomain**: adds a domain to the model
- **DeleteDomain**: deletes a domain (identified by its name) of the model
