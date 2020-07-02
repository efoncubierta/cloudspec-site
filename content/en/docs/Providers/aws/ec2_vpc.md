---
title: "Virtual Private Cloud"
linkTitle: "Virtual Private Cloud"
description: >
  All about resource aws:ec2:vpc.
---


## Members
* **cidr_block**
(`string`):
The primary IPv4 CIDR block for the VPC.
* **cidr_block_associations**
(`nested[]`):
Information about the IPv4 CIDR blocks associated with the VPC.
    * **cidr_block**
(`string`):
The IPv4 CIDR block.
    * **cidr_block_state**
(`string`):
Information about the state of the CIDR block.
Allowed values: `associating`, `associated`, `disassociating`, `disassociated`, `failing`, `failed`, `null`
* **instance_tenancy**
(`string`):
The allowed tenancy of instances launched into the VPC.
Allowed values: `default`, `dedicated`, `host`, `null`
* **ipv6_cidr_block_associations**
(`nested[]`):
Information about the IPv6 CIDR blocks associated with the VPC.
    * **ipv6_cidr_block**
(`string`):
The IPv6 CIDR block.
    * **ipv6_cidr_block_state**
(`string`):
Information about the state of the CIDR block.
Allowed values: `associating`, `associated`, `disassociating`, `disassociated`, `failing`, `failed`, `null`
    * **ipv6_pool**
(`string`):
The ID of the IPv6 address pool from which the IPv6 CIDR block is allocated.
    * **network_border_group**
(`string`):
The name of the location from which we advertise the IPV6 CIDR block.
* **is_default**
(`boolean`):
Indicates whether the VPC is the default VPC.
* **owner_id**
(`string`):
The ID of the AWS account that owns the VPC.
* **region**
(`string`):
The AWS region.
* **state**
(`string`):
The current state of the VPC.
Allowed values: `pending`, `available`, `null`
* **tags**
(`key_value[]`):
Any tags assigned to the VPC.
* **vpc_id**
(`string`):
The ID of the VPC.
* **&gt;dhcp_options**
([aws:ec2:dhcp_options](../../aws/ec2_dhcp_options)):
The ID of the set of DHCP options you've associated with the VPC
