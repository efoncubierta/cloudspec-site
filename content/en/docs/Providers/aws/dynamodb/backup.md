---
title: "Backup"
linkTitle: "Backup"
description: >
  All about resource aws:dynamodb:backup.
---


## Members
* **backup_arn**
(`string`):
ARN associated with the backup.
* **backup_creation_date**
(`date`):
Time at which the backup was created.
* **backup_expiry_date**
(`date`):
Time at which the automatic on-demand backup created by DynamoDB will expire.
* **backup_name**
(`string`):
Name of the specified backup.
* **backup_size**
(`number`):
Size of the backup in bytes.
* **backup_status**
(`string`):
Backup state.
Allowed values: `CREATING`, `DELETED`, `AVAILABLE`, `null`
* **backup_type**
(`string`):
Backup type.
Allowed values: `USER`, `SYSTEM`, `AWS_BACKUP`, `null`
* **region**
(`string`):
The AWS region.
* **&gt;table**
([aws:dynamodb:table](../../aws/dynamodb/table)):
The source table
