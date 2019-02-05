# Introduction

<div class="subtitle">
How can we constantly change and optimise customer services which require the well-aligned interaction of various technologies and at the same time maintain overall service quality according to the customers needs?
</div>

Context{#Context}
-------

Typical solutions nowadays consist of a multitude of different solution elements which need to interact consistently in order to provide the desired services. These services are typically provided to the users as managed services in the sense that the user need not be concerned of how to assemble and maintain the various solution elements. This task can be handled by a DevOps teams which has partnered with a set of vendors providing the solution components from which the solution architecture with its elements can be derived.

It is not a trivial task for the DevOps team and this book will list a couple of the issues they will encounter when attempting to provide high quality services in a constantly evolving context.

The main expertise which a DevOps team needs to acquire is the capability of managing the solution according to the varying demand of it's users and the handling the required changes related to the lifecycle of its solution elements.

The value chain for a solution shown in the following diagram depicts how vendors of solution components and the DevOps team need to work together in order to provide a managed service to the users.

<img src="./assets/process.svg" alt="Process" width="440"/>

In the sourcing phase the vendors provide the components for the customer solutions. These serve as building blocks for the architecture which the DevOps teams design for their users in the development phase. The architecture is then instantiated in the operations phase and continuously updated in order to support the lifecycle of the managed service.

Motivation{#Motivation}
----------

Customer services nowadays make use of a vast amount of different technologies.
Ensuring service quality for the customers therefore needs to align the
various corresponding management concepts in such a way that a customer
requirement is broken down into a sequence of changes on the appropriate
technological components.

Technological evolution and the rapid increase of automation capabilities has
lead in the previous years to a plethora of heterogenous management concepts
which require rather immense integration efforts due to the complexity of the
possible interaction patterns.

Taking into account that technological change is part of the game a core dilemma
as stated above becomes obvious.

There is no golden bullet solution for solving this dilemma in the context of
highly automated technology based services. Each approach has its advantages and
disadvantages.

There are two traditional approaches of how to tackle this dilemma and an
alternative concept which will be introduced in this book.

**Approach A: Don't touch a running system**

This approach is favoured by many Telco operators who need to guarantee a
service quality of 99,999% service availability and often reduce the
introduction of new technical features to an absolute minimum.

**Approach B: Throw away**

Why try to ensure compatibility with old hardware? Simply throw away
the old technology and make use of the advantages of the new one.
This has been the motto for the introduction of many storage technologies
ranging from magnetic tapes, hard drives, solid state disks and
cloud storage facilities. Each of the technological options addressed different
qualities and found their own market leaving the consumer with the task to
tackle the actual migration.

**Approach C: Choreography of Managed Components and Services**

This book presents a third approach of how to bridge the requirements related to
change and in parallel maintaining a well defined service quality based on a
choreography of managed components and services.

The disadvantage being that the various management and automation concepts need
to adhere to a common way of interacting with one another.
The benefits of this approach allow for the continuous integration of ever
changing technological services in a seamless manner thereby focussing on the
need of the customers in a consistent way.

Challenges{#Challenges}
==========

These are the main abilities which need to be taken into consideration when
addressing the dilemma:

**Hyper Convergence**

The ability to consistently manage a diverse variety of technologies and align
possibly different functional and non-functional requirements.

**Lifecycle Automation**

The ability to manage the full lifecycle of all technological components and
services in an automated manner.

**Closed Loop Control**

The ability to continuously evaluate the lifecycle state and configurations of
components and services and triggering policies as needed in order to fulfill
the customer requirements.

**Model-Driven Automation**

The ability to manage automation procedures with the help of models which
define the desired outcome instead of having to provide custom code which
describes for each type of requirement how to apply the needed changes.

**Dependency Management**

The ability to consistent handle the dependencies between different components
and services when applying changes.

**Fault Tolerance**

The ability to recover from unforeseen errors and reestablish a comprehensive
lifecycle management for all components and services.

**Reconciliation**

The ability to recover from manual interventions and reestablish a comprehensive
lifecycle management for all components and services.

**Concurrency**

The ability to consistently handle multiple concurrent customer requests and
changes in a well-defined manner.

**Scalability**

The ability to seamlessly scale with the number of managed component, services
as well with the number of changes regardless of the location of the managed
elements.

**Continuous Integration/Continuous Deployment**

The ability to continuously roll-out or roll-back versions of components and
services in a well-defined manner.

**Near Real Time**

The ability to manage changes in a close to real time timescale.


**High Availability**

The ability to provide highly available services even when applying changes.
