---
title: "Volume"
linkTitle: "Volume"
description: >
  All about resource aws:ec2:volume.
---


## Members
* **attachments**
(`nested[]`):
Information about the volume attachments.
    * **attach_time**
(`date`):
The time stamp when the attachment initiated.
    * **delete_on_termination**
(`boolean`):
Indicates whether the EBS volume is deleted on instance termination.
    * **device**
(`string`):
The device name.
    * **state**
(`string`):
The attachment state of the volume.
Allowed values: `attaching`, `attached`, `detaching`, `detached`, `busy`, `null`
    * **&gt;instance**
([aws:ec2:instance](../../aws/ec2/instance)):
The instance
    * **&gt;volume**
([aws:ec2:volume](../../aws/ec2/volume)):
The volume
* **availability_zone**
(`string`):
The Availability Zone for the volume.
* **create_time**
(`date`):
The time stamp when volume creation was initiated.
* **encrypted**
(`boolean`):
Indicates whether the volume is encrypted.
* **fast_restored**
(`boolean`):
Indicates whether the volume was created using fast snapshot restore.
* **iops**
(`number`):
The number of I/O operations per second (IOPS) that the volume supports.
* **multi_attach_enabled**
(`boolean`):
Indicates whether Amazon EBS Multi-Attach is enabled.
* **outpost_arn**
(`string`):
The Amazon Resource Name (ARN) of the Outpost.
* **region**
(`string`):
The AWS region.
* **size**
(`number`):
The size of the volume, in GiBs.
* **state**
(`string`):
The volume state.
Allowed values: `creating`, `available`, `in-use`, `deleting`, `deleted`, `error`, `null`
* **tags**
(`key_value[]`):
Any tags assigned to the volume.
* **volume_id**
(`string`):
The ID of the volume.
* **volume_type**
(`string`):
The volume type.
Allowed values: `standard`, `io1`, `gp2`, `sc1`, `st1`, `null`
* **&gt;snapshot**
([aws:ec2:snapshot](../../aws/ec2/snapshot)):
The snapshot from which the volume was created, if applicable
