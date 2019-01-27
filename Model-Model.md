Model-Overview
==============

Model
-----

The model entity is the central entry point to the information required by the
closed-loop automation procedures. It is subdivided into a set of subdomains
which can be administrated independently from one another.

| Attribute | Type           | Description             |
|-----------|----------------|-------------------------|
| Schema    | string         | schema of the model     |
| Name      | string         | name of the model       |
| Domains   | map to Domains | map of names to domains |


Domain
------

A domain is an administrative realm which can be managed independently from
other domains and may serve as a context for sharding the model.

| Attribute     | Type                 | Description                   |
|---------------|----------------------|-------------------------------|
| Name          | string               | name of the model             |
| Catalog       | map to Components    | map of names to components    |
| Architectures | map to Architectures | map of names to architectures |
| Solutions     | map to Solutions     | map of names to solutions     |
| Tasks         | map to Tasks         | map of uuids to tasks         |
| Events        | map to Events        | map of uuids to events        |
