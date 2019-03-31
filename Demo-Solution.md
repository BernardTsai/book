Demo
====

The concepts presented in the previous chapters will be demonstrated with the help of a simple example.

In this example a simple application server hosted together with a database backend in a tenant is providing it's service via a firewall to users in the internet as shown in the diagram below.

<img src="./assets/images/solar/demo.svg" alt="Demo Application" width="440"/>

The solution makes use of four networks for establishing communication amongst the applications, the users and administrators according to following considerations:

* users can access the application services from the internet (pub) via the firewall
* administrators can manage the firewall, the application server and the database from the internet (pub) via the firewall
* the firewall forwards external user requests via the machine-to-machine network (ext)
* the firewall forwards external administrative requests via the operation, administration and maintenance network (oam)
* the application server persists its information to the database via the machine-to-machine network (int)

All applications need to be hosted on their corresponding servers which belong together with the networks listed above to a tenant context.

Step 1: Administration
----------------------

The first step is to create a domain in which to embed the solution by opening the web interface of SOLAR (URL: http://localhost/solar/index.html).

<img src="./assets/images/solar/administration.png" alt="Administration" width="440"/>

The administration view of SOLAR will appear offering the possibility to conduct the following five administrative tasks:

1. **Create Domain:** allows to define a new administrative domain with an independent catalog and set of architecture blueprints and solutions,
2. **Remove Domain:** provides the possibility to completely remove a domain from the repository,
3. **Reset Model:** removes all domains from the repository,
4. **Import Model:** imports a repository by uploading the contents of a local file and
5. **Export Model:** exports a repository by downloading the contents of the repository into a file.

Clicking on "Create Domain" will prompt the user to enter the name of a new domain. For this example enter "demo" and press "OK".

<img src="./assets/images/solar/create-domain.png" alt="New Domain" width="440"/>

A new domain with the name "demo" will be created and SOLAR will present the catalog view of the domain. A different domain can be selected at any time by picking one of the domains offered in the selection at top right of the navigation bar at the top of the screen.

Step 2: Sourcing
----------------

The catalog view allows to define the components which may serve as the building blocks for solutions. It can be selected by clicking on the catalog icon in the navigation bar at the top of the screen. Initially the catalog is empty.

<img src="./assets/images/solar/catalog-1.png" alt="Administration" width="440"/>

This example requires four types of components:

1. **Tenant:** representing a virtual datacenter containing servers and networks
2. **Network:** a communication domain
3. **Server:** a host for applications which may be connected to networks
4. **Application:** software processes which are deployed to servers and may depend on the services exposed by other hosts.

The components will be listed on the left side whereas details of a component will be presented on the right side of the screen.

### Creating a new component

Pressing the "+" button on the left side will open the detail view for a new component. Initially the attributes of the new component are set to default values and need to be redefined.

<img src="./assets/images/solar/catalog-2.png" alt="New Component" width="440"/>

The main attributes for a component are:

* the **name** of the component (this corresponds to the type of a solution instance),
* the **version** represented by a string starting with a 'V' and followed by a version number which complies to the rules for semantic versioning (e.g. V1.10.3) and
* a **base configuration**, which can be a component specific configuration string.

The screenshot below displays the information of a "tenant" component:

<img src="./assets/images/solar/catalog-3.png" alt="Tenant" width="440"/>

The component is added to the catalog by pressing the "Create" button on the top right of the details view.

<img src="./assets/images/solar/catalog-4.png" alt="Tenant" width="440"/>

The component which have been stored in the catalog appear on the left side of the screen.

A "network" component can be defined in the similar way. It is assumed that a "network" has a runtime context dependency to a "tenant", i.e. it can only be created within the context of a tenant.

A new dependency is added by clicking on the "+" icon on the right of the dependencies list which is initially empty. A prompt will appear asking for the name of the dependency.

<img src="./assets/images/solar/catalog-5.png" alt="New Dependency" width="440"/>

Each dependency is described by:
* the **type** of dependency (runtime context or service context),
* the **component** type which can fulfil the dependency as well as
* the required **version** of the component type and an optional dependency specific **base configuration**.

<img src="./assets/images/solar/catalog-6.png" alt="Tenant Dependency of a Network" width="440"/>

Dependencies which are not needed can be removed by pressing the "-" icon to the left of each dependency.

It is important to note that changes to the repository will only be made if the "Create" button is pressed.

The following screenshots display the definition for the "server" component. The assumption is that "servers" require a "tenant" and "networks" as their runtime context.

<img src="./assets/images/solar/catalog-7.png" alt="Server Component" width="440"/>

### Updating a component

"Applications" require "servers" as their runtime context and other "applications" as their service context. Since the "application" component has a self-referential service dependency to itself it is necessary to first create the component without this dependency and then later update the component by adding the missing dependency. This can be achieved by pressing the icon to the left of a component in the list, which will open the details view for the component again.

<img src="./assets/images/solar/catalog-8.png" alt="Application Component" width="440"/>

The changes made will only be synchronised with the repository after pressing the "Update" button on the top right of the details view. It is recommended to not change a component definition after having referred to it in the context of dependencies or architecture blueprints.

### Duplicating a component

In some cases it might be helpful to make a copy of an existing component definition without having to reenter all the information, e.g. when creating a new version of a component definition. The detail view of a component offers a "Duplicate" button for this purpose, which when pressed copies the definitions of the component and updates the minor number of the version indicator. The "Update" button will allow to then persist any required modifications.

### Deleting a component

The "Delete" button of the component detail view allows to remove the component definition from the repository in the case this definition is not be required any longer.

At this point all required components have been defined and can now be used for designing an architecture which will serve as a solution blueprint.

Step 3: Designing
-----------------


### Creating an architecture for a new solution

### Selecting an existing architecture


### Adding an architecture element

### Editing an architecture element

### Duplicating an architecture element

### Deleting an architecture element


### Updating an architecture

### Deploying an architecture

### Duplicating an architecture

### Deleting an architecture
