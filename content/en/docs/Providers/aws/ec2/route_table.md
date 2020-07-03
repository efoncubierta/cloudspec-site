---
title: "Route Table"
linkTitle: "Route Table"
description: >
  All about resource aws:ec2:route_table.
---


## Members
* **associations**
(`nested[]`):
The associations between the route table and one or more subnets or a gateway.
    * **state**
(`string`):
The state of the association.
Allowed values: `associating`, `associated`, `disassociating`, `disassociated`, `failed`, `null`
    * **main**
(`boolean`):
Indicates whether this is the main route table.
    * **route_table_association_id**
(`string`):
The ID of the association.
    * **&gt;gateway**
([aws:ec2:internet_gateway](../../aws/ec2/internet_gateway)):
The internet gateway or virtual private gateway
    * **&gt;route_table**
([aws:ec2:route_table](../../aws/ec2/route_table)):
The route table
    * **&gt;subnet**
([aws:ec2:subnet](../../aws/ec2/subnet)):
The subnet
* **owner_id**
(`string`):
The ID of the AWS account that owns the route table.
* **propagating_gateway**
(`string[]`):
Any virtual private gateway (VGW) propagating routes.
* **region**
(`string`):
The AWS region.
* **route_table_id**
(`string`):
The ID of the route table.
* **routes**
(`nested[]`):
The routes in the route table.
    * **destination_cidr_block**
(`string`):
The IPv4 CIDR block used for the destination match.
    * **destination_ipv6_cidr_block**
(`string`):
The IPv6 CIDR block used for the destination match.
    * **destination_prefix_list_id**
(`string`):
The prefix of the AWS service.
    * **instance_owner_id**
(`string`):
The AWS account ID of the owner of the instance.
    * **origin**
(`string`):
Describes how the route was created.
Allowed values: `CreateRouteTable`, `CreateRoute`, `EnableVgwRoutePropagation`, `null`
    * **state**
(`string`):
The state of the route.
Allowed values: `active`, `blackhole`, `null`
    * **&gt;egress_only_internet_gateway**
([aws:ec2:internet_gateway](../../aws/ec2/internet_gateway)):
The egress-only internet gateway
    * **&gt;gateway**
([aws:ec2:internet_gateway](../../aws/ec2/internet_gateway)):
The gateway attached to your VPC
    * **&gt;instance**
([aws:ec2:instance](../../aws/ec2/instance)):
The ID of a NAT instance in your VPC
    * **&gt;local_gateway**
([aws:ec2:local_gateway](../../aws/ec2/local_gateway)):
The local gateway
    * **&gt;nat_gateway**
([aws:ec2:nat_gateway](../../aws/ec2/nat_gateway)):
The NAT gateway
    * **&gt;network_interface**
([aws:ec2:network_interface](../../aws/ec2/network_interface)):
The network interface
    * **&gt;transit_gateway**
([aws:ec2:transit_gateway](../../aws/ec2/transit_gateway)):
The transit gateway
    * **&gt;vpc_peering_connection**
([aws:ec2:vpc_peering_connection](../../aws/ec2/vpc_peering_connection)):
The VPC peering connection
* **tags**
(`key_value[]`):
Any tags assigned to the route table.
* **&gt;vpc**
([aws:ec2:vpc](../../aws/ec2/vpc)):
The ID of the VPC
