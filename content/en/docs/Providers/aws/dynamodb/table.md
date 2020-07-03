---
title: "Table"
linkTitle: "Table"
description: >
  All about resource aws:dynamodb:table.
---


## Members
* **archival_summary**
(`nested`):
Contains information about the table archive.
    * **archival_backup_arn**
(`string`):
The Amazon Resource Name (ARN) of the backup the table was archived to, when applicable in the archival reason.
    * **archival_date**
(`date`):
The date and time when table archival was initiated by DynamoDB, in UNIX epoch time format.
    * **archival_reason**
(`string`):
The reason DynamoDB archived the table.
* **billing_mode_summary**
(`nested`):
Contains the details for the read/write capacity mode.
    * **billing_mode**
(`string`):
Controls how you are charged for read and write throughput and how you manage capacity.
Allowed values: `PROVISIONED`, `PAY_PER_REQUEST`, `null`
    * **last_update_to_pay_per_request**
(`date`):
Represents the time when `PAY_PER_REQUEST` was last set as the read/write capacity mode.
* **creation_date**
(`date`):
The date and time when the table was created, in UNIX epoch time format..
* **global_secondary_indexes**
(`nested[]`):
he global secondary indexes, if any, on the table.
    * **backfilling**
(`boolean`):
Indicates whether the index is currently backfilling.
    * **index_arn**
(`string`):
The Amazon Resource Name (ARN) that uniquely identifies the index.
    * **index_name**
(`string`):
The name of the global secondary index.
    * **index_size**
(`number`):
The total size of the specified index, in bytes.
    * **index_status**
(`string`):
The current state of the global secondary index.
Allowed values: `CREATING`, `UPDATING`, `DELETING`, `ACTIVE`, `null`
    * **item_count**
(`number`):
The number of items in the specified index.
    * **key_schema**
(`nested[]`):
The complete key schema for a global secondary index, which consists of one or more pairs of attribute names and key types.
        * **attribute_name**
(`string`):
The name of a key attribute.
        * **key_type**
(`string`):
The role that this key attribute will assume.
Allowed values: `HASH`, `RANGE`, `null`
    * **projection**
(`nested`):
Represents attributes that are copied (projected) from the table into the global secondary index.
        * **non_key_attributes**
(`string[]`):
Represents the non-key attribute names which will be projected into the index.
        * **projection_type**
(`string`):
The set of attributes that are projected into the index.
Allowed values: `ALL`, `KEYS_ONLY`, `INCLUDE`, `null`
    * **provisioned_throughput**
(`nested`):
Represents the provisioned throughput settings for the specified global secondary index.
        * **last_decrease_date**
(`date`):
The date and time of the last provisioned throughput decrease for this table.
        * **last_increase_date**
(`date`):
The date and time of the last provisioned throughput increase for this table.
        * **number_of_decreases_today**
(`number`):
The number of provisioned throughput decreases for this table during this UTC calendar day.
        * **read_capacity_units**
(`number`):
The maximum number of strongly consistent reads consumed per second before DynamoDB returns a `ThrottlingException`.
        * **write_capacity_units**
(`number`):
The maximum number of writes consumed per second before DynamoDB returns a `ThrottlingException`.
* **global_table_version**
(`string`):
Represents the version of global tables in use, if the table is replicated across AWS Regions.
* **item_count**
(`number`):
The number of items in the specified table.
* **key_schema**
(`nested[]`):
The primary key structure for the table.
    * **attribute_name**
(`string`):
The name of a key attribute.
    * **key_type**
(`string`):
The role that this key attribute will assume.
Allowed values: `HASH`, `RANGE`, `null`
* **latest_stream_arn**
(`string`):
The Amazon Resource Name (ARN) that uniquely identifies the latest stream for this table.
* **latest_stream_label**
(`string`):
A timestamp, in ISO 8601 format, for this stream.
* **local_secondary_indexes**
(`nested[]`):
Represents one or more local secondary indexes on the table.
    * **index_arn**
(`string`):
The Amazon Resource Name (ARN) that uniquely identifies the index.
    * **index_name**
(`string`):
Represents the name of the local secondary index.
    * **index_size**
(`number`):
The total size of the specified index, in bytes.
    * **item_count**
(`number`):
The number of items in the specified index.
    * **key_schema**
(`nested[]`):
The complete key schema for the local secondary index, consisting of one or more pairs of attribute names and key types.
        * **attribute_name**
(`string`):
The name of a key attribute.
        * **key_type**
(`string`):
The role that this key attribute will assume.
Allowed values: `HASH`, `RANGE`, `null`
    * **projection**
(`nested`):
Represents attributes that are copied (projected) from the table into the global secondary index.
        * **non_key_attributes**
(`string[]`):
Represents the non-key attribute names which will be projected into the index.
        * **projection_type**
(`string`):
The set of attributes that are projected into the index.
Allowed values: `ALL`, `KEYS_ONLY`, `INCLUDE`, `null`
* **provisioned_throughput**
(`nested`):
The provisioned throughput settings for the table, consisting of read and write capacity units, along with data about increases and decreases.
    * **last_decrease_date**
(`date`):
The date and time of the last provisioned throughput decrease for this table.
    * **last_increase_date**
(`date`):
The date and time of the last provisioned throughput increase for this table.
    * **number_of_decreases_today**
(`number`):
The number of provisioned throughput decreases for this table during this UTC calendar day.
    * **read_capacity_units**
(`number`):
The maximum number of strongly consistent reads consumed per second before DynamoDB returns a `ThrottlingException`.
    * **write_capacity_units**
(`number`):
The maximum number of writes consumed per second before DynamoDB returns a `ThrottlingException`.
* **region**
(`string`):
The AWS region.
* **replicas**
(`nested[]`):
Represents replicas of the table.
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
* **restore_summary**
(`nested`):
Contains details for the restore.
    * **restore_date**
(`date`):
Point in time or source backup time.
    * **restore_in_progress**
(`boolean`):
Indicates if a restore is in progress or not.
    * **source_backup_arn**
(`string`):
The Amazon Resource Name (ARN) of the backup from which the table was restored.
    * **source_table_arn**
(`string`):
The ARN of the source table of the backup that is being restored.
* **sse_description**
(`nested`):
The description of the server-side encryption status on the specified table.
    * **inaccessible_encryption_date**
(`date`):
Indicates the time, in UNIX epoch date format, when DynamoDB detected that the table's AWS KMS key was inaccessible.
    * **sse_type**
(`string`):
Server-side encryption type.
Allowed values: `AES256`, `KMS`, `null`
    * **status**
(`string`):
Represents the current state of server-side encryption.
Allowed values: `ENABLING`, `ENABLED`, `DISABLING`, `DISABLED`, `UPDATING`, `null`
* **stream_specification**
(`nested`):
The current DynamoDB Streams configuration for the table.
    * **stream_enabled**
(`boolean`):
Indicates whether DynamoDB Streams is enabled (true) or disabled (false) on the table.
    * **stream_view_type**
(`string`):
When an item in the table is modified, `StreamViewType` determines what information is written to the stream for this table.
Allowed values: `NEW_IMAGE`, `OLD_IMAGE`, `NEW_AND_OLD_IMAGES`, `KEYS_ONLY`, `null`
* **table_arn**
(`string`):
The Amazon Resource Name (ARN) that uniquely identifies the table.
* **table_id**
(`string`):
Unique identifier for the table for which the backup was created.
* **table_name**
(`string`):
The name of the table.
* **table_size**
(`number`):
The total size of the specified table, in bytes.
* **table_status**
(`string`):
The current state of the table.
Allowed values: `CREATING`, `UPDATING`, `DELETING`, `ACTIVE`, `INACCESSIBLE_ENCRYPTION_CREDENTIALS`, `ARCHIVING`, `ARCHIVED`, `null`
* **tags**
(`key_value[]`):
The tags attached to the table.
