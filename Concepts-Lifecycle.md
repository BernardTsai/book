Lifecycle
=========

<div class="subtitle"> All components and component clusters follow the exactly same lifecycle model.</div>

Each component regardless of type or version and every component cluster is
governed by a generic lifecycle model which defines in which states these
entities may be and which transitions are allowed between these aforementioned
states.

These states and transitions are depicted in the following diagram:

<img src="./assets/lifecycle-model.svg" width="400" />

The lifecycle of the components and clusters runs through following states:

* __Initial State:__

  In the __initial__ state the definition of the component has been stored in a
  repository or catalogue system which maintains the descriptor along with all
  corresponding software artefacts to bring this component to life with the help
  of an orchestrator and the type specific controllers.

  **Create transition**

  The orchestrator may be triggered to __create__ the component and initiate
  the __creation__ procedure for an instance of the component.

  It will have to ensure that the components runtime context is already
  available and __active__ so that this transition can be conducted.

  If the transition is successful within a certain time period the component is
  regarded to be __inactive__.

  In the case the component cannot be installed due to time-outs or other errors
  even after a limited set of repetitions the component is regarded to be in the
  __failure__ state.

* __Inactive State:__

  In the __inactive__ state the component already resides in its runtime context
  although it might not be configured and activated to provide services to its
  consumers

  The orchestrator may also be triggered to either __configure__, __start__  or
  __destroy__ the component instance.

  **Configure Transition**

  The orchestrator may now be triggered to __configure__ the component instannce
  and initiate the __configuration__ procedure. It will have to ensure that all
  of the components service dependencies at least have already been configured
  so that the corresponding endpoint information is available and that this
  transition can be conducted with the help of this information.

  If the transition is successful within a certain time period the component
  instance is still regarded to be __inactive__.

  In the case the component instance cannot be configured due to time-outs or
  other errors even after a limited set of repetitions the component is regarded
  to be in the __failure__ state.

  **Start Transition**

  In the case of the __start__ trigger the orchestrator initiates the
  __starting__ procedure which will after successful termination change the
  state of the component instance to __active__.

  In the case the component instance cannot be started due to time-outs or
  other errors even after a limited set of repetitions the component is regarded
  to be in the __failure__ state.

  **Destroy Transition**

  If the trigger was __destroy__ the orchestrator destroys the component
  instance. This will change the state if the component instance to __initial__
  again.

  In the case the component instance cannot be destroyed due to time-outs or
  other errors even after a limited set of repetitions the component is regarded
  to be in the __failure__ state.

* __Active State:__

  In the __active__ state the component instance has been deployed into its
  runtime context, has obtained all the information it requires to access the
  services of all the components it depends upon and now actively exposes its
  services to the service consumers.

  The orchestrator may now be triggered to either __stop__ or __reconfigure__
  the component instance.

  **Stop Transition**

  In the case of the __stop__ trigger the orchestrator notifies the service
  consumers that the component instance will cease to provide its services
  and initiate the __stopping__ procedure which will after successful
  termination change the state of the component instance to __inactive__.

  In the case the component instance cannot be stopped due to time-outs or
  other errors even after a limited set of repetitions the component is
  regarded to be in the __failure__ state.

  **Reconfigure Transition**

  If the trigger was __update__ the orchestrator will reapply the new
  configuration to the component in the course of the  __updating__ procedure
  which will after successful termination again lead the component to the
  __active__ state. During the updating of the component will still maintain
  the availability of its services.

  Depending on the nature of the component this behaviour might or might not be
  supported. This behaviour is required for clusters which need to provide a
  24x7 service, whereas components which serve as a part of a cluster should
  either be created anew with the correct configuration and then integrated into
  the cluster or first be stopped and taken out of the cluster, then
  reconfigured and after that started and taken into the cluster again.

  In both cases, if the transition is not successful due to time-outs or other
  errors even after a limited set of repetitions the component is regarded to be
  in the __failure__ state.

* __Failure State:__

  There may be several reasons for a component instance to have reached the
  __failure__ state in which the status of the component instance is
  undetermined and therefore regarded to be unusable.

  **Reset Transition**

  As soon as the orchestrator has identified that a component has reached
  this state it needs to inform all of its service consumers and then initiate a
  __reset__ procedure which should free any bound resources and as a result
  transfer the component into the __initial__ state again.
