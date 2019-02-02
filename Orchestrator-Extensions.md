Extensions
==========

<div class="subtitle">
Enhancing closed loop automation in a well defined way with custom code.
</div>

Managing the lifecycle of a complex solution may have to include sophisticated
procedures which can not be covered by a closed-loop automation framework in a
generic way.

Therefore an extension mechanism is required to include these procedures in a
well defined way. Following options could be made available:

- **Controllers:** writing a custom controller for a specific component type is
  the most obvious way to include custom code into the orchestration framework
- **Monitoring Events:** custom code could subscribe to monitoring information
  published by the monitoring on an message bus and trigger actions which could
  include interactions with the orchestrator via its API.
- **Lifecycle Hooks:** the orchestrator code invoke custom code
  when certain lifecycle management related events occur. The custom code could
  itself again invoke the orchestrator via its API.

```
PICTURE
```
