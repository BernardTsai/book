Controller
==========

<div class="subtitle">
A controller is a component type specific management component capable of applying the changes to component instances according to the standardised component lifecycle model and providing information about the status of these instances.
</div>

The diagram shows how the orchestrator engine and the monitor system interact with the controller:

<img src="./assets/images/controller.svg" alt="Controller" width="520"/>

1. The controller can either receive lifecycle management instructions from the orchestration engine or be triggered by the monitoring system to determine the status of instances of solution elements.
2. The controller then executes these requests and deliver the results to the requesting module of the orchestrator.

The interface specification of the controller is listed in the appendix [Controller API](Appendix-Controller.md).
