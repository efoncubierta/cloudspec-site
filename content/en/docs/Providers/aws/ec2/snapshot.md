---
title: "Snapshot"
linkTitle: "Snapshot"
description: >
  All about resource aws:ec2:snapshot.
---


## Members
* **encrypted**
(`boolean`):
Indicates whether the snapshot is encrypted.
* **owner_id**
(`string`):
The AWS account ID of the EBS snapshot owner.
* **progress**
(`string`):
The progress of the snapshot, as a percentage.
* **region**
(`string`):
The AWS region.
* **snapshotId**
(`string`):
The ID of the snapshot. Each snapshot receives a unique identifier when it is created.
* **start_time**
(`date`):
The time stamp when the snapshot was initiated.
* **state**
(`string`):
The snapshot state.
Allowed values: `pending`, `completed`, `error`, `null`
* **tags**
(`key_value[]`):
Any tags assigned to the snapshot.
* **volume_size**
(`number`):
The size of the volume, in GiB.
* **&gt;volume**
([aws:ec2:volume](../../aws/ec2/volume)):
The volume that was used to create the snapshot
