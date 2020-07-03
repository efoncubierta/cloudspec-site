---
title: "Transit Gateway"
linkTitle: "Transit Gateway"
description: >
  All about resource aws:ec2:transit_gateway.
---


## Members
* **creation_time**
(`date`):
The creation time.
* **options**
(`nested`):
The transit gateway options.
    * **auto_accept_shared_attachments**
(`boolean`):
Indicates whether attachment requests are automatically accepted.
    * **default_route_table_association**
(`boolean`):
Indicates whether resource attachments are automatically associated with the default association route table.
    * **default_route_table_propagation**
(`boolean`):
Indicates whether resource attachments automatically propagate routes to the default propagation route table.
    * **dns_support**
(`boolean`):
Indicates whether DNS support is enabled.
    * **multicast_support**
(`boolean`):
Indicates whether multicast is enabled on the transit gateway.
    * **vpn_ecmp_support**
(`boolean`):
Indicates whether Equal Cost Multipath Protocol support is enabled.
    * **&gt;association_default_route_table**
([aws:ec2:route_table](../../aws/ec2/route_table)):
The default association route table
    * **&gt;propagation_default_route_table**
([aws:ec2:route_table](../../aws/ec2/route_table)):
The default propagation route table
* **owner_id**
(`string`):
The ID of the AWS account ID that owns the transit gateway.
* **region**
(`string`):
The AWS region.
* **state**
(`string`):
The state of the transit gateway.
Allowed values: `pending`, `available`, `modifying`, `deleting`, `deleted`, `null`
* **tags**
(`key_value[]`):
The tags for the transit gateway.
* **transit_gateway_arn**
(`string`):
The Amazon Resource Name (ARN) of the transit gateway.
* **transit_gateway_id**
(`string`):
The ID of the transit gateway.
