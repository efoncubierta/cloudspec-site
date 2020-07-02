---
title: "Network Interface"
linkTitle: "Network Interface"
description: >
  All about resource aws:ec2:network_interface.
---


## Members
* **association**
(`nested`):
The association information for an Elastic IP address (IPv4) associated with the network interface.
    * **ip_owner_id**
(`string`):
The ID of the Elastic IP address owner.
    * **public_dns_name**
(`string`):
The public DNS name.
    * **public_ip**
(`string`):
The address of the Elastic IP address bound to the network interface.
* **attachment**
(`nested`):
The network interface attachment.
    * **attach_time**
(`date`):
The timestamp indicating when the attachment initiated.
    * **delete_on_termination**
(`boolean`):
Indicates whether the network interface is deleted when the instance is terminated.
    * **instance_owner_id**
(`string`):
The AWS account ID of the owner of the instance.
    * **status**
(`string`):
The attachment state.
Allowed values: `attaching`, `attached`, `detaching`, `detached`, `null`
    * **&gt;instance**
([aws:ec2:instance](../../aws/ec2_instance)):
The instance
* **availability_zone**
(`string`):
The Availability Zone.
* **interface_type**
(`string`):
The type of network interface.
Allowed values: `interface`, `natGateway`, `efa`, `null`
* **ipv6_addresses**
(`string[]`):
The IPv6 addresses associated with the network interface.
* **network_interface_id**
(`string`):
The ID of the network interface.
* **outpost_arn**
(`string`):
The Amazon Resource Name (ARN) of the Outpost.
* **owner_id**
(`string`):
The AWS account ID of the owner of the network interface.
* **private_dns_name**
(`string`):
The private DNS name.
* **private_ip_address**
(`string`):
The IPv4 address of the network interface within the subnet.
* **private_ip_addresses**
(`nested[]`):
The private IPv4 addresses associated with the network interface.
    * **association**
(`nested`):
The association information for an Elastic IP address (IPv4) associated with the network interface.
        * **ip_owner_id**
(`string`):
The ID of the Elastic IP address owner.
        * **public_dns_name**
(`string`):
The public DNS name.
        * **public_ip**
(`string`):
The address of the Elastic IP address bound to the network interface.
    * **primary**
(`boolean`):
Indicates whether this IPv4 address is the primary private IPv4 address of the network interface.
    * **private_dns_name**
(`string`):
The private DNS name.
    * **private_ip_address**
(`string`):
The private IPv4 address.
* **region**
(`string`):
The AWS region.
* **source_dest_check**
(`boolean`):
Indicates whether traffic to or from the instance is validated.
* **status**
(`string`):
The status of the network interface.
Allowed values: `available`, `associated`, `attaching`, `in-use`, `detaching`, `null`
* **tags**
(`key_value[]`):
Any tags assigned to the network interface.
* **&gt;groups**
([aws:ec2:security_group](../../aws/ec2_security_group)[]):
Any security groups for the network interface
* **&gt;subnet**
([aws:ec2:subnet](../../aws/ec2_subnet)):
The subnet
* **&gt;vpc**
([aws:ec2:vpc](../../aws/ec2_vpc)):
The VPC
