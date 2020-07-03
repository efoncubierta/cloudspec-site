---
title: "Capacity Reservation"
linkTitle: "Capacity Reservation"
description: >
  All about resource aws:ec2:capacity_reservation.
---


## Members
* **availability_zone**
(`string`):
The Availability Zone in which the capacity is reserved.
* **available_instance_count**
(`number`):
The remaining capacity. Indicates the number of instances that can be launched in the Capacity Reservation.
* **capacity_reservation_arn**
(`string`):
The Amazon Resource Name (ARN) of the Capacity Reservation.
* **capacity_reservation_id**
(`string`):
The ID of the Capacity Reservation.
* **create_date**
(`date`):
The date and time at which the Capacity Reservation was created.
* **ebs_optimized**
(`boolean`):
Indicates whether the Capacity Reservation supports EBS-optimized instances.
* **end_date**
(`date`):
The date and time at which the Capacity Reservation expires.
* **end_date_type**
(`string`):
Indicates the way in which the Capacity Reservation ends.
Allowed values: `unlimited`, `limited`, `null`
* **ephemeral_storage**
(`boolean`):
Indicates whether the Capacity Reservation supports instances with temporary.
* **instance_match_criteria**
(`string`):
Indicates the type of instance launches that the Capacity Reservation accepts.
Allowed values: `open`, `targeted`, `null`
* **instance_platform**
(`string`):
The type of operating system for which the Capacity Reservation reserves capacity.
Allowed values: `Linux/UNIX`, `Red Hat Enterprise Linux`, `SUSE Linux`, `Windows`, `Windows with SQL Server`, `Windows with SQL Server Enterprise`, `Windows with SQL Server Standard`, `Windows with SQL Server Web`, `Linux with SQL Server Standard`, `Linux with SQL Server Web`, `Linux with SQL Server Enterprise`, `null`
* **instance_type**
(`string`):
The type of instance for which the Capacity Reservation reserves capacity.
* **owner_id**
(`string`):
The ID of the AWS account that owns the DHCP options set.
* **region**
(`string`):
The AWS region.
* **state**
(`string`):
The current state of the Capacity Reservation.
Allowed values: `active`, `expired`, `cancelled`, `pending`, `failed`, `null`
* **tags**
(`key_value[]`):
Any tags assigned to the Capacity Reservation.
* **tenancy**
(`string`):
Indicates the tenancy of the Capacity Reservation.
Allowed values: `default`, `dedicated`, `null`
* **total_instance_count**
(`number`):
The total number of instances for which the Capacity Reservation reserves capacity.
