Monitoring
==========

> The monitoring system continuously compares the current state of instances with the desired target state and if needed triggers compensating measures.

The following diagram depicts the basic functionality provided by the monitoring system.

<img src="./assets/images/monitoring.svg" alt="Monitoring" width="400"/>

The monitoring system will conduct in regular intervals the following steps:

1. acquire from the model database all the instances of solution elements which need to be monitored  
2. trigger the corresponding controllers to obtain the status of an instance of the solution elements
3. the controllers evaluate the status of the instances of solution elements
4. the monitoring system notifies external systems via message bus about the status of an instance of the solution elements
5. the monitoring system checks if the desired state matches the current state
6. the monitoring triggers if required a compensating measure to align the current state of an instance of a solution element with the desired state
