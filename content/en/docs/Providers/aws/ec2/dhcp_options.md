---
title: "DHCP Options"
linkTitle: "DHCP Options"
description: >
  All about resource aws:ec2:dhcp_options.
---


## Members
* **dhcp_configurations**
(`nested[]`):
One or more DHCP options in the set.
    * **key**
(`string`):
The name of a DHCP option.
    * **values**
(`string[]`):
One or more values for the DHCP option.
* **dhcp_options_id**
(`string`):
The ID of the set of DHCP options.
* **owner_id**
(`string`):
The ID of the AWS account that owns the Capacity Reservation.
* **region**
(`string`):
The AWS region.
* **tags**
(`key_value[]`):
Any tags assigned to the DHCP options set.
