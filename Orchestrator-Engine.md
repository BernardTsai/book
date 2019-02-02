Orchestration Engine
====================

> The orchestrator engine is responsible for coordinating the lifecycle management activities of the various component specific controllers.

The following diagram provides an overview of the algorithm of the orchestration engine:

<img src="./assets/images/algorithm.svg" alt="Engine" width="970"/>

The algorithm splits up into several distinct layers:

Layer A: Main Routine
---------------------

The main routine:
- registers all controllers,
- starts the internal communication channel,
- starts the monitoring system,
- starts the task dispatcher and finally
- initiates all external interfaces (application programming interface, command line interface and message bus interface).

The interfaces collect the requests coming in from DevOps or external systems and publish these requests to the internal channel.

Layer B: Task Dispatcher
------------------------

The task dispatcher listens to requests published to the internal channel these requests are evaluated in order to identify what kind of task needs to be executed. The task dispatcher then spawns an appropriate subprocess and waits for the next request.

Layer C: Task Execution
-----------------------

The task to be executed depends on type of the task context and the state of the task:

**Task Context**:

The context of a task can be:

- **Architecture**: the instantiation/update of a solution based on architectural blueprint,
- **Cluster**: the resizing, status update or reconfiguration of a cluster,
- **Instance**: the status update or reconfiguration of an instance.

**Task State**:

The task states are related to the influencing events:

- **Execution**: indicates that a task should be executed/reexecuted
- **Completed**: indicates that a task has completed successfully and that all finalising activities need to be conducted
- **Failed**: indicates that a task has failed and that all required cleanup activities need to be conducted
- **Timeout**: indicates that a task has run into a timeout and that all required recovery or cleanup activities need to be conducted
- **Terminate**: indicates that a task needs to be terminated

The component type specific controllers are invoked synchronously when executing tasks in the context of instances.

The task may trigger subtasks depending on the information provided in the catalog and architecture section of the model by issuing corresponding requests.

Layer D: Controller
-------------------

Controllers are capable of transitioning instances of a specific component type along the paths defined in the common [lifecycle model](Concepts-Lifecycle.md).

This includes the capabilities to:

- **Create**: create an instance,
- **Destroy**: destroy an instance,
- **Start**: start an instance,
- **Stop**: stop an instance,
- **Configure**: configure or reconfigure an instance and
- **Reset**: cleanup an instance.
