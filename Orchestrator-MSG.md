Message Bus
===========

<div class="subtitle">
The orchestrator notifies about events related to tasks and the status of the solution.
</div>

The message bus interface is exposed to external systems and serves as a gateway to expose:
- task related notification events and
- status information of the the solution.

<img src="./assets/images/msg.svg" alt="Message Bus" width="560"/>

---

**Events**

The orchestrator can be handed a unique topic identifier "**TOPIC1**" in the
course of the startup process. This is the topic to which it will publish its
events to a message broker.

Each event is related to a task and will notify wether:

- **Execution**: the execution of a task has been triggered
- **Termination**: the termination of a task has been triggered
- **Timeout**: a task has run into a time-out
- **Failure**: a task has failed
- **Success**: a task has completed successfully
- **Terminated**: a task has been terminated

The type of tasks to which an event may relate are:

- **Architecture**: tasks related to the instantiation or update of a solution
  based on an architecture blueprint
- **Element**: tasks related to the instantiation, modification or deletion of
  an element
- **Cluster**: tasks related to the instantiation, modification or deletion of
  a cluster
- **Instance**: tasks related to the instantiation, modification or deletion of
  an instance
- **Parallel**: a task representing a group of tasks which can be executed in
  parallel
- **Instance**: a task representing a group of tasks which need to be executed
  sequentially

The event information captures following attributes of the event and the
corresponding task:

| Attribute     | Type            | Description                     |
|---------------|-----------------|---------------------------------|
| Request       | string          | request identifier              |
| Type          | string          | type of event                   |
| UUID          | string          | unique identifier for the event |
| Source        | string          | identifier of the source task   |
| Time          | string          | time since 1.1.1970 in nsecs    |
| Task          | string          | unique identifier for the task  |
| TaskType      | string          | type of the task                |
| Parent        | string          | identifier of the parent task   |
| Subtasks      | array of UUIDs  | array of UUIDs of subtasks      |
| Status        | string          | status of the task              |
| Phase         | string          | execution phase of the task     |
| Domain        | string          | name of the domain              |
| Solution      | string          | name of the solution            |
| Element       | string          | name of the element             |
| Cluster       | string          | name of the cluster             |
| Instance      | string          | name of the instance            |
| State         | string          | desired lifecycle state         |
| Configuration | object          | runtime configuration object    |

---

**Status**

The orchestrator can be handed a second unique topic identifier "**TOPIC2**" in the course of the startup process. This is the topic to which it will publish its status information to a message broker.

The status information captures following attributes of the state of a solution, element, cluster or instance within a domain.

| Attribute     | Type            | Description                     |
|---------------|-----------------|---------------------------------|
| Time          | string          | time since 1.1.1970 in nsecs    |
| Domain        | string          | name of the domain              |
| Solution      | string          | name of the solution            |
| Element       | string          | name of the element             |
| Cluster       | string          | name of the cluster             |
| Instance      | string          | name of the instance            |
| State         | string          | current lifecycle state         |
