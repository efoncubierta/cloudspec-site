---
title: "Network ACL"
linkTitle: "Network ACL"
description: >
  All about resource aws:ec2:network_acl.
---


## Members
* **entries**
(`nested[]`):
One or more entries (rules) in the network ACL.
    * **cidr_block**
(`string`):
The IPv4 network range to allow or deny, in CIDR notation.
    * **egress**
(`boolean`):
Indicates whether the rule is an egress rule.
    * **icmp_type_code**
(`number`):
The ICMP code. A value of -1 means all codes for the specified ICMP type.
    * **ipv6_cidr_block**
(`string`):
The IPv6 network range to allow or deny, in CIDR notation.
    * **port_range**
(`nested`):
TCP or UDP protocols: The range of ports the rule applies to.
        * **from**
(`number`):
The first port in the range.
        * **to**
(`number`):
The last port in the range.
    * **protocol**
(`string`):
The protocol number. A value of "-1" means all protocols.
    * **rule_action**
(`string`):
Indicates whether to allow or deny the traffic that matches the rule.
Allowed values: `allow`, `deny`, `null`
* **is_default**
(`boolean`):
Indicates whether this is the default network ACL for the VPC.
* **network_acl_id**
(`string`):
The ID of the network ACL.
* **owner_id**
(`string`):
The ID of the AWS account that owns the network ACL.
* **region**
(`string`):
The AWS region.
* **tags**
(`key_value[]`):
Any tags assigned to the network ACL.
* **&gt;subnets**
([aws:ec2:subnet](../../aws/ec2/subnet)[]):
The subnet
* **&gt;vpc**
([aws:ec2:vpc](../../aws/ec2/vpc)):
The VPC for the network ACL
