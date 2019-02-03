Extensions
==========

<div class="subtitle">
Enhancing closed loop automation in a well defined way with custom code.
</div>

Managing the lifecycle of a complex solution may have to include sophisticated
procedures which can not be covered by a closed-loop automation framework in a
generic manner.

<img src="./assets/images/extensions.svg" alt="Extensions" width="400"/>


Therefore an extension mechanism is required to include these procedures in a
well defined way. Following options could be made available:

1. **Controller:** writing a custom controller for a specific component type is the most obvious way to include custom code into the orchestration framework
2. **Hook:** custom code could subscribe to monitoring information published by the monitoring system via the message bus interface and trigger actions which could include interactions with the orchestrator via its API. The same applies to the task related events issued by the orchestrator engine via the message bus interface.
3. **Component Specific Task Handlers:** the orchestrator code could invoke component specific task handlers which would overwrite the generic handlers defined in the core orchestration engine.
