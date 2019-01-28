Domain-Automation
=================

Tasks and events form the automation subset of the
[information model](./Model.md) of a domain describing the **current** structure
and configuration of a solution.

<img src="./assets/automation.svg" alt="Automation" width="720"/>

Task
----

A task describes an activity to manipulate the solution.

| Attribute     | Type            | Description                    |
|---------------|-----------------|--------------------------------|
| Type          | string          | type of the task               |
| UUID          | string          | unique identifier for the task |
| Parent        | string          | identifier of the parent task  |
| Subtasks      | array of UUIDs  | array of UUIDs of subtasks     |
| Status        | string          | status of the task             |
| Phase         | string          | execution phase of the task    |
| Domain        | string          | name of the domain             |
| Solution      | string          | name of the solution           |
| Element       | string          | name of the element            |
| Cluster       | string          | name of the cluster            |
| Instance      | string          | name of the instance           |
| State         | string          | desired lifecycle state        |
| Configuration | object          | runtime configuration object   |

Event
-----

An event notifies about the occurrence of a task related event.

| Attribute     | Type            | Description                     |
|---------------|-----------------|---------------------------------|
| Type          | string          | type of event                   |
| UUID          | string          | unique identifier for the event |
| Domain        | string          | name of the domain              |
| Source        | string          | identifier of the source task   |
| Task          | string          | identifier of the task          |
| Time          | string          | time since 1.1.1970 in nsecs    |
