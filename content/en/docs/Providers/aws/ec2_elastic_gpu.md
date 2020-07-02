---
title: "Elastic Graphics Accelerator"
linkTitle: "Elastic Graphics Accelerator"
description: >
  All about resource aws:ec2:elastic_gpu.
---


## Members
* **availability_zone**
(`string`):
The Availability Zone in the which the Elastic Graphics accelerator resides.
* **elastic_gpu_health**
(`string`):
The status of the Elastic Graphics accelerator.
Allowed values: `OK`, `IMPAIRED`, `null`
* **elastic_gpu_id**
(`string`):
The ID of the Elastic Graphics accelerator.
* **elastic_gpu_state**
(`string`):
The state of the Elastic Graphics accelerator.
Allowed values: `ATTACHED`, `null`
* **elastic_gpu_type**
(`string`):
The type of Elastic Graphics accelerator.
* **region**
(`string`):
The AWS region.
* **tags**
(`key_value[]`):
The tags assigned to the Elastic Graphics accelerator.
* **&gt;instance**
([aws:ec2:instance](../../aws/ec2_instance)):
The instance to which the Elastic Graphics accelerator is attached
