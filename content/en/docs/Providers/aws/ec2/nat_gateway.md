---
title: "NAT Gateway"
linkTitle: "NAT Gateway"
description: >
  All about resource aws:ec2:nat_gateway.
---


## Members
* **create_time**
(`date`):
The date and time the NAT gateway was created.
* **delete_time**
(`date`):
The date and time the NAT gateway was deleted, if applicable.
* **failure_code**
(`string`):
If the NAT gateway could not be created, specifies the error code for the failure..
* **nat_gateway_addresses**
(`nested[]`):
Information about the IP addresses and network interface associated with the NAT gateway.
    * **allocation_id**
(`string`):
The allocation ID of the Elastic IP address that's associated with the NAT gateway.
    * **private_ip**
(`string`):
The private IP address associated with the Elastic IP address.
    * **public_ip**
(`string`):
The Elastic IP address associated with the NAT gateway.
    * **&gt;network_interface**
([aws:ec2:network_interface](../../aws/ec2/network_interface)):
The ID of the network interface associated with the NAT gateway
* **nat_gateway_id**
(`string`):
The ID of the NAT gateway.
* **region**
(`string`):
The AWS region.
* **state**
(`string`):
The state of the NAT gateway.
Allowed values: `pending`, `failed`, `available`, `deleting`, `deleted`, `null`
* **tags**
(`key_value[]`):
The tags for the NAT gateway.
* **&gt;subnet**
([aws:ec2:subnet](../../aws/ec2/subnet)):
The subnet in which the NAT gateway is located
* **&gt;vpc**
([aws:ec2:vpc](../../aws/ec2/vpc)):
The VPC in which the NAT gateway is located
