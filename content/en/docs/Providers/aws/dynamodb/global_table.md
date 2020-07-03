---
title: "Global Table"
linkTitle: "Global Table"
description: >
  All about resource aws:dynamodb:global_table.
---


## Members
* **creation_date**
(`date`):
The creation time of the global table.
* **table_arn**
(`string`):
The unique identifier of the global table.
* **table_name**
(`string`):
The global table name.
* **table_status**
(`string`):
The current state of the global table.
Allowed values: `CREATING`, `ACTIVE`, `DELETING`, `UPDATING`, `null`
* **replicas**
(`nested[]`):
The Regions where the global table has replicas.
    * **global_secondary_indexes**
(`nested[]`):
Replica-specific global secondary index settings.
        * **index_name**
(`string`):
The name of the global secondary index.
        * **provisioned_throughput_override**
(`nested`):
If not described, uses the source table GSI's read capacity settings.
            * **read_capacity_units**
(`number`):
Replica-specific read capacity units.
    * **provisioned_throughput_override**
(`nested`):
Replica-specific provisioned throughput.
        * **read_capacity_units**
(`number`):
Replica-specific read capacity units.
    * **region**
(`string`):
The name of the Region.
    * **replica_status**
(`string`):
The current state of the replica.
Allowed values: `CREATING`, `CREATION_FAILED`, `UPDATING`, `DELETING`, `ACTIVE`, `null`
    * **replica_progress**
(`string`):
Specifies the progress of a Create, Update, or Delete action on the replica as a percentage.
* **tags**
(`key_value[]`):
The tags attached to the table.
