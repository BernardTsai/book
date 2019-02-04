
Command Line Interface Version: 0.0.1
===============================

Documentation of the command line interface of the orchestrator.

Store model.
--------

create model from yaml data and store it into the repository

**Usage:**
```
> StoreModel -model [model data as yaml]
```


**Parameters:**

\-model [model data as yaml] (required)



**Response:**




---

Retrieve model.
--------

retrieve model from the repository as yaml data

**Usage:**
```
> RetrieveModel
```



**Response:**


Model: model data as yaml


---

Reset model.
--------

reset model in the repository to initial state

**Usage:**
```
> ResetModel
```



**Response:**




---

List domains.
--------

Retrieves list of domain names

**Usage:**
```
> ListDomains
```



**Response:**


Names: domain names as yaml


---

Store domain.
--------

create a new domain from yaml data and store it in the repository

**Usage:**
```
> StoreDomain -d [domain name] -domain [domain data as yaml]
```


**Parameters:**

\-d [domain name] (required)

\-domain [domain data as yaml] (required)



**Response:**




---

Retrieve domain.
--------

retrieve domain from the repository as yaml data

**Usage:**
```
> RetrieveDomain -d [domain name]
```


**Parameters:**

\-d [domain name] (required)



**Response:**


Domain: domain data as yaml




---

Remove domain.
--------

remove domain from the repository

**Usage:**
```
> RemoveDomain -d [domain name]
```


**Parameters:**

\-d [domain name] (required)



**Response:**






---

List components.
--------

list all the available components in a domain

**Usage:**
```
> ListComponents -d [domain name]
```


**Parameters:**

\-d [domain name] (required)



**Response:**


Names: component names as yaml


---

List versions of a component template.
--------

list all the available versions of a component in a domain

**Usage:**
```
> ListComponentVersions -d [domain name] -c [component name]
```


**Parameters:**

\-d [domain name] (required)

\-c [component name] (required)



**Response:**


Names: version names as yaml


---

Create component.
--------

create a new component from yaml data and store it in the repository

**Usage:**
```
> CreateComponent -d [domain name] -c [component name] -v [version of component] -component [component data as yaml]
```


**Parameters:**

\-d [domain name] (required)

\-c [component name] (required)

\-v [version of component] (required)

\-component [component data as yaml] (required)



**Response:**




---

Retrieve component.
--------

retrieve component from the repository as yaml data

**Usage:**
```
> RetrieveComponent -d [domain name] -c [component name] -v [version of component]
```


**Parameters:**

\-d [domain name] (required)

\-c [component name] (required)

\-v [version of component] (required)



**Response:**


Component: component data as yaml


---

Remove component.
--------

remove component from the repository

**Usage:**
```
> RemoveComponent -d [domain name] -c [component name] -v [version of component]
```


**Parameters:**

\-d [domain name] (required)

\-c [component name] (required)

\-v [version of component] (required)



**Response:**




---

List architectures.
--------

list all the available architectures in a domain

**Usage:**
```
> ListArchitectures -d [domain name]
```


**Parameters:**

\-d [domain name] (required)



**Response:**


Names: architecture names as yaml


---

List architecture versions.
--------

list all the available versions of an architecture in a domain

**Usage:**
```
> ListArchitectureVersions -d [domain name] -a [architecture name]
```


**Parameters:**

\-d [domain name] (required)

\-a [architecture name] (required)



**Response:**


Names: version names as yaml


---

Store architecture.
--------

create a new architecture from yaml data and store it in the repository

**Usage:**
```
> StoreArchitecture -d [domain name] -a [architecture name] -v [version of architecture] -architecture [architecture data as yaml]
```


**Parameters:**

\-d [domain name] (required)

\-a [architecture name] (required)

\-v [version of architecture] (required)

\-architecture [architecture data as yaml] (required)



**Response:**




---

Retrieve architecture.
--------

retrieve architecture from the repository as yaml data

**Usage:**
```
> RetrieveArchitecture -d [domain name] -a [architecture name] -v [version of architecture]
```


**Parameters:**

\-d [domain name] (required)

\-a [architecture name] (required)

\-v [version of architecture] (required)



**Response:**


Architecture: architecture data as yaml


---

Remove architecture.
--------

remove architecture from the repository

**Usage:**
```
> RemoveArchitecture -d [domain name] -a [architecture name] -v [version of architecture]
```


**Parameters:**

\-d [domain name] (required)

\-a [architecture name] (required)

\-v [version of architecture] (required)



**Response:**




---

List solutions.
--------

list all the available solutions in a domain

**Usage:**
```
> ListSolutions -d [domain name]
```


**Parameters:**

\-d [domain name] (required)



**Response:**


Names: solution names as yaml


---

Store solution.
--------

create a new solution from yaml data and store it in the repository

**Usage:**
```
> StoreSolution -d [domain name] -s [solution name] -solution [solution data as yaml]
```


**Parameters:**

\-d [domain name] (required)

\-s [solution name] (required)

\-solution [solution data as yaml] (required)



**Response:**




---

Retrieve solution.
--------

retrieve solution from the repository as yaml data

**Usage:**
```
> RetrieveSolution -d [domain name] -s [solution name]
```


**Parameters:**

\-d [domain name] (required)

\-s [solution name] (required)



**Response:**


Solution: solution data as yaml


---

Remove solution.
--------

remove solution from the repository

**Usage:**
```
> RemoveSolution -d [domain name] -s [solution name]
```


**Parameters:**

\-d [domain name] (required)

\-s [solution name] (required)



**Response:**




---

Modify solution.
--------

 create a new solution or update an existing solution based on the information provided in an architecture blueprint

**Usage:**
```
> ModifySolution -d [domain name] -s [solution name] -v [version of the solution]
```


**Parameters:**

\-d [domain name] (required)

\-s [solution name] (required)

\-v [version of the solution] (required)



**Response:**




---

List elements.
--------

list all the available elements in a solution

**Usage:**
```
> ListElements -d [domain name] -s [solution name]
```


**Parameters:**

\-d [domain name] (required)

\-s [solution name] (required)



**Response:**


Names: element names as yaml


---

Retrieve element.
--------

retrieve element from the repository as yaml data

**Usage:**
```
> RetrieveElement -d [domain name] -s [solution name] -e [element name]
```


**Parameters:**

\-d [domain name] (required)

\-s [solution name] (required)

\-e [element name] (required)



**Response:**


Element: element data as yaml


---

Modify element.
--------

update an existing element based on the information provided in a configuration object

**Usage:**
```
> ModifyElement -d [domain name] -s [solution name] -e [element name] -configuration [configuration data as yaml]
```


**Parameters:**

\-d [domain name] (required)

\-s [solution name] (required)

\-e [element name] (required)

\-configuration [configuration data as yaml] (required)



**Response:**




---

List clusters.
--------

list all the available clusters in an element

**Usage:**
```
> ListClusters -d [domain name] -s [solution name] -e [element name]
```


**Parameters:**

\-d [domain name] (required)

\-s [solution name] (required)

\-e [element name] (required)



**Response:**


Names: cluster names as yaml


---

Retrieve cluster.
--------

retrieve cluster from the repository as yaml data

**Usage:**
```
> RetrieveCluster -d [domain name] -s [solution name] -e [element name] -c [cluster name]
```


**Parameters:**

\-d [domain name] (required)

\-s [solution name] (required)

\-e [element name] (required)

\-c [cluster name] (required)



**Response:**


Cluster: cluster data as yaml


---

Modify cluster.
--------

update an existing cluster based on the information provided in a configuration object

**Usage:**
```
> ModifyCluster -d [domain name] -s [solution name] -e [element name] -c [cluster name] -configuration [configuration data as yaml]
```


**Parameters:**

\-d [domain name] (required)

\-s [solution name] (required)

\-e [element name] (required)

\-c [cluster name] (required)

\-configuration [configuration data as yaml] (required)



**Response:**




---

List instances.
--------

list all the available instances in a cluster

**Usage:**
```
> ListInstances -d [domain name] -s [solution name] -e [element name] -c [cluster name]
```


**Parameters:**

\-d [domain name] (required)

\-s [solution name] (required)

\-e [element name] (required)

\-c [cluster name] (required)



**Response:**


Names: instance names as yaml


---

Retrieve instance.
--------

retrieve instance from the repository as yaml data

**Usage:**
```
> RetrieveInstance -d [domain name] -s [solution name] -e [element name] -c [cluster name] -i [instance name]
```


**Parameters:**

\-d [domain name] (required)

\-s [solution name] (required)

\-e [element name] (required)

\-c [cluster name] (required)

\-i [instance name] (required)



**Response:**


Instance: instance data as yaml


---

Modify instance.
--------

update an existing instance based on the information provided in a configuration object

**Usage:**
```
> ModifyInstance -d [domain name] -s [solution name] -e [element name] -c [cluster name] -i [instance name] -configuration [configuration data as yaml]
```


**Parameters:**

\-d [domain name] (required)

\-s [solution name] (required)

\-e [element name] (required)

\-c [cluster name] (required)

\-i [instance name] (required)

\-configuration [configuration data as yaml] (required)



**Response:**




---

List tasks.
--------

list all toplevel tasks in a domain (optionally matching a certain request ID)

**Usage:**
```
> ListTasks -d [domain name] -r [request name]
```


**Parameters:**

\-d [domain name] (required)

\-r [request name] (optional)



**Response:**


Names: task names as yaml


---

Retrieve task.
--------

retrieve task from the repository as yaml data

**Usage:**
```
> RetrieveTask -d [domain name] -t [task name]
```


**Parameters:**

\-d [domain name] (required)

\-t [task name] (required)



**Response:**


Task: task data as yaml


---

Terminate task.
--------

stop a task in a domain

**Usage:**
```
> TerminateTask -d [domain name] -t [task name]
```


**Parameters:**

\-d [domain name] (required)

\-t [task name] (required)



**Response:**




---

List events.
--------

list all events related to a task in a domain

**Usage:**
```
> ListEvents -d [domain name] -t [task name]
```


**Parameters:**

\-d [domain name] (required)

\-t [task name] (required)



**Response:**


Names: event names as yaml


---

Retrieve event.
--------

retrieve event from the repository as yaml data

**Usage:**
```
> RetrieveEvent -d [domain name] -e [event name]
```


**Parameters:**

\-d [domain name] (required)

\-e [event name] (required)



**Response:**


Event: event data as yaml


---
