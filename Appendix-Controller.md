Controller API
=============

The methods which a controller needs to expose are described in the following sections. They aim to support the standard lifecycle management concept for instances and allow for monitoring their state as well.

<img src="./assets/images/controller-api.svg" alt="Controller" width="520"/>

Methods
-------

### Create {#Create}

Creates a new instance of a cluster of an element of a solution.

```
response, error = create(request)
```

The variables are:

| Variable | Type                  | Description                            |
|:---------|:----------------------|:---------------------------------------|
| request  | [Request](#Request)   | Request as issued by the orchestrator  |
| response | [Response](#Response) | Response returned by the controller    |
| error    | [Error](#Error)       | Error object if an error has occurred  |

---

### Destroy {#Destroy}

Destroys an existing instance of a cluster of an element of a solution.

```
response, error = destroy(request)
```

The variables are:

| Variable | Type                  | Description                            |
|:---------|:----------------------|:---------------------------------------|
| request  | [Request](#Request)   | Request as issued by the orchestrator  |
| response | [Response](#Response) | Response returned by the controller    |
| error    | [Error](#Error)       | Error object if an error has occurred  |

---

### Start {#Start}

Activates an instance of a cluster of an element of a solution.

```
response, error = start(request)
```

The variables are:

| Variable | Type                  | Description                            |
|:---------|:----------------------|:---------------------------------------|
| request  | [Request](#Request)   | Request as issued by the orchestrator  |
| response | [Response](#Response) | Response returned by the controller    |
| error    | [Error](#Error)       | Error object if an error has occurred  |

---

### Stop {#Stop}

Deactivates an instance of a cluster of an element of a solution.

```
response, error = stop(request)
```

The variables are:

| Variable | Type                  | Description                            |
|:---------|:----------------------|:---------------------------------------|
| request  | [Request](#Request)   | Request as issued by the orchestrator  |
| response | [Response](#Response) | Response returned by the controller    |
| error    | [Error](#Error)       | Error object if an error has occurred  |

---

### Configure {#Configure}

Configures a deactivated instance of a cluster of an element of a solution.

```
response, error = configure(request)
```

The variables are:

| Variable | Type                  | Description                            |
|:---------|:----------------------|:---------------------------------------|
| request  | [Request](#Request)   | Request as issued by the orchestrator  |
| response | [Response](#Response) | Response returned by the controller    |
| error    | [Error](#Error)       | Error object if an error has occurred  |

---

### Reconfigure {#Reconfigure}

Reconfigures an active instance of a cluster of an element of a solution.

```
response, error = reconfigure(request)
```

The variables are:

| Variable | Type                  | Description                            |
|:---------|:----------------------|:---------------------------------------|
| request  | [Request](#Request)   | Request as issued by the orchestrator  |
| response | [Response](#Response) | Response returned by the controller    |
| error    | [Error](#Error)       | Error object if an error has occurred  |

---

### Reset {#Reset}

Resets an instance of a cluster of an element of a solution.

```
response, error = reset(request)
```

The variables are:

| Variable | Type                  | Description                            |
|:---------|:----------------------|:---------------------------------------|
| request  | [Request](#Request)   | Request as issued by the orchestrator  |
| response | [Response](#Response) | Response returned by the controller    |
| error    | [Error](#Error)       | Error object if an error has occurred  |

---

### Status {#Status}

Determines the status of an instance of a cluster of an element of a solution.

```
response, error = status(request)
```

The variables are:

| Variable | Type                  | Description                            |
|:---------|:----------------------|:---------------------------------------|
| request  | [Request](#Request)   | Request as issued by the orchestrator  |
| response | [Response](#Response) | Response returned by the controller    |
| error    | [Error](#Error)       | Error object if an error has occurred  |

---


Objects
-------

### Request{#Request}

A **request** object is passed as a serialised yaml object.

{% collapse title="Schema Definition:" %}
```yaml
Request:
  type: "object"
  description: |
    The request object as passed by the orchestration engine to the controller
    when requesting a lifecycle operation on a specific instance.
  properties:
    Operation:
      type: string
      description: "The requested lifecycle operation."
      enum: ["create", "destroy","start","stop","configure","reconfigure","reset","status"]
    Solution:
      type: object
      description: "Solution"
      properties:
        Name:
          type: string
          description: "Name of the solution"
        Version:
          type: string
          description: "Version of the solution"
        Configuration:
          type: object
          description: "Configuration of the solution"
          additionalProperties: true
        RuntimeConfiguration:
          type: object
          description: "Runtime configuration of the solution"
          additionalProperties: true
    Element:
      type: object
      description: "Element of the solution"
      properties:
        Name:
          type: string
          description: "Name of the element"
        Configuration:
          type: object
          description: "Configuration of the element"
          additionalProperties: true
        RuntimeConfiguration:
          type: object
          description: "Runtime configuration of the element"
          additionalProperties: true
    Cluster:
      type: object
      description: "Cluster of the element of the solution"
      properties:
        Version:
          type: string
          description: "Version of the element"
        BaseConfiguration:
          type: object
          description: "Base configuration of the cluster"
          additionalProperties: true
        Configuration:
          type: object
          description: "Configuration of the cluster"
          additionalProperties: true
        RuntimeConfiguration:
          type: object
          description: "Runtime configuration of the cluster"
          additionalProperties: true
        Endpoint:
          type: object
          description: "Endpoint information of the cluster"
          additionalProperties: true
    Instance:
      type: object
      description: "Instance of a cluster of the element of the solution"
      properties:
        UUID:
          type: string
          description: "Universal unique identifier of the instance"
        RuntimeConfiguration:
          type: object
          description: "Runtime configuration of the instance"
          additionalProperties: true
        Endpoint:
          type: object
          description: "Endpoint information of the instance"
          additionalProperties: true
    Relationships:
      type: object
      description: "Instance of a cluster of the element of the solution"
      additionalProperties:
        $ref:
          type: object
          description: "Relationship"
          properties:
            Name:
              type: string
              description: "Name of the relationship"
            Configuration:
              type: object
              description: "Configuration of the relationship"
              additionalProperties: true
            RuntimeConfiguration:
              type: object
              description: "Runtime configuration of the relationship"
              additionalProperties: true
            Endpoint:
              type: object
              description: "Endpoint information of the relationship"
              additionalProperties: true
```
{% endcollapse %}

### Response {#Response}

A **response** object is passed back as a serialised yaml object as a result from a lifecycle operation:

{% collapse title="Schema Definition:" %}
```yaml
Response:
  type: "object"
  description: |
    A response object is passed back as a serialised yaml object as a result from a lifecycle operation.
  properties:
    Solution:
      type: object
      description: "Solution"
      properties:
        Name:
          type: string
          description: "Name of the solution"
        Version:
          type: string
          description: "Version of the solution"
        Configuration:
          type: object
          description: "Configuration of the solution"
          additionalProperties: true
        RuntimeConfiguration:
          type: object
          description: "Runtime configuration of the solution"
          additionalProperties: true
    Element:
      type: object
      description: "Element of the solution"
      properties:
        Name:
          type: string
          description: "Name of the element"
        Configuration:
          type: object
          description: "Configuration of the element"
          additionalProperties: true
        RuntimeConfiguration:
          type: object
          description: "Runtime configuration of the element"
          additionalProperties: true
    Cluster:
      type: object
      description: "Cluster of the element of the solution"
      properties:
        Version:
          type: string
          description: "Version of the element"
        BaseConfiguration:
          type: object
          description: "Base configuration of the cluster"
          additionalProperties: true
        Configuration:
          type: object
          description: "Configuration of the cluster"
          additionalProperties: true
        RuntimeConfiguration:
          type: object
          description: "Runtime configuration of the cluster"
          additionalProperties: true
        Endpoint:
          type: object
          description: "Endpoint information of the cluster"
          additionalProperties: true
    Instance:
      type: object
      description: "Instance of a cluster of the element of the solution"
      properties:
        UUID:
          type: string
          description: "Universal unique identifier of the instance"
        RuntimeConfiguration:
          type: object
          description: "Runtime configuration of the instance"
          additionalProperties: true
        Endpoint:
          type: object
          description: "Endpoint information of the instance"
          additionalProperties: true
    Relationships:
      type: object
      description: "Instance of a cluster of the element of the solution"
      additionalProperties:
        $ref:
          type: object
          description: "Relationship"
          properties:
            Name:
              type: string
              description: "Name of the relationship"
            Configuration:
              type: object
              description: "Configuration of the relationship"
              additionalProperties: true
            RuntimeConfiguration:
              type: object
              description: "Runtime configuration of the relationship"
              additionalProperties: true
            Endpoint:
              type: object
              description: "Endpoint information of the relationship"
              additionalProperties: true
```
{% endcollapse %}

### Error {#Error}

An **error** object indicating possible issues is passed as a serialised yaml object according to following schema definition:

{% collapse title="Schema Definition:" %}
```yaml
Error:
  type: "object"
  description: |
    An error indicating the issues which occurred in the context of a lifecycle operation.
  properties:
    additionalProperties: true
```
{% endcollapse %}
