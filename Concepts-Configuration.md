Configuration
=============

<div class="subtitle"> Configuration customises a component to the environment and general requirements of its service consumers.</div>

The configuration of a component typically depends on the type of the component and possibly even on the version and therefore can not be handled in a generic manner but needs to be executed by the corresponding specialised controller.

<img src="./assets/images/configuration.svg" alt="Configuration" width="600"/>

Nevertheless it is possible to distinguish between following aspects of the
required configuration information:

* **Base Configuration:** the data which is provided by the vendor of a component to parametrise its generic service behaviour.
* **Design Time Configuration:** the data which is related to the architecture of the solution and is developed by the DevOps team to customise the component in such a way that it can be integrated into its runtime context and service context.
* **Run Time Configuration:** the configuration data which is determined during the run time by the orchestrator (e.g. the endpoints of services).
