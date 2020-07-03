---
title: "Amazon Machine Image"
linkTitle: "Amazon Machine Image"
description: >
  All about resource aws:ec2:image.
---


## Members
* **architecture**
(`string`):
The architecture of the image.
Allowed values: `i386`, `x86_64`, `arm64`, `null`
* **block_device_mappings**
(`nested[]`):
Any block device mapping entries.
    * **device_name**
(`string`):
The device name.
    * **ebs**
(`nested`):
Parameters used to automatically set up EBS volumes when the instance is launched.
        * **delete_on_termination**
(`boolean`):
Indicates whether the EBS volume is deleted on instance termination.
        * **encrypted**
(`boolean`):
Indicates whether the encryption state of an EBS volume is changed while being restored from a backing snapshot.
        * **iops**
(`number`):
The number of I/O operations per second (IOPS) that the volume supports.
        * **volume_size**
(`number`):
The size of the volume, in GiB.
        * **volume_type**
(`string`):
The volume type.
Allowed values: `standard`, `io1`, `gp2`, `sc1`, `st1`, `null`
        * **&gt;snapshot**
([aws:ec2:snapshot](../../aws/ec2/snapshot)):
The ID of the snapshot
    * **virtual_name**
(`string`):
The virtual device name.
* **creation_date**
(`date`):
The date and time the image was created.
* **ena_support**
(`boolean`):
Flag indicating ENA support.
* **hypervisor**
(`string`):
The hypervisor type of the image.
Allowed values: `ovm`, `xen`, `null`
* **image_id**
(`string`):
The ID of the AMI.
* **image_location**
(`string`):
The location of the AMI.
* **type**
(`string`):
The type of image.
Allowed values: `machine`, `kernel`, `ramdisk`, `null`
* **kernel_id**
(`string`):
The kernel associated with the image, if any. Only applicable for machine images.
* **name**
(`string`):
The name of the AMI that was provided during image creation.
* **owner_id**
(`string`):
The AWS account ID of the image owner.
* **platform**
(`string`):
This value is set to 'windows' for Windows AMIs; otherwise, it is blank.
Allowed values: `Windows`, `null`
* **product_codes**
(`nested[]`):
Any product codes associated with the AMI.
    * **id**
(`string`):
The product code.
    * **type**
(`string`):
The type of product code.
Allowed values: `devpay`, `marketplace`, `null`
* **public_launch_permissions**
(`boolean`):
Indicates whether the image has public launch permissions.
* **region**
(`string`):
The AWS region.
* **root_device_name**
(`string`):
The device name of the root device volume.
* **root_device_type**
(`string`):
The type of root device used by the AMI.
Allowed values: `ebs`, `instance-store`, `null`
* **sriov_net_support**
(`string`):
Specifies whether enhanced networking with the Intel 82599 Virtual Function interface is enabled.
* **state**
(`string`):
State of the image.
Allowed values: `pending`, `available`, `invalid`, `deregistered`, `transient`, `failed`, `error`, `null`
* **tags**
(`key_value[]`):
Any tags assigned to the image.
* **virtualization_type**
(`string`):
The type of virtualization of the AMI.
Allowed values: `hvm`, `paravirtual`, `null`
