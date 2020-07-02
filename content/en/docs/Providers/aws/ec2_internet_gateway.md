---
title: "Internet Gateway"
linkTitle: "Internet Gateway"
description: >
  All about resource aws:ec2:internet_gateway.
---


## Members
* **attachments**
(`nested[]`):
Any VPCs attached to the internet gateway.
    * **state**
(`string`):
The current state of the attachment.
Allowed values: `attaching`, `attached`, `detaching`, `detached`, `null`
    * **&gt;vpc**
([aws:ec2:vpc](../../aws/ec2_vpc)):
The VPC
* **internet_gateway_id**
(`string`):
The ID of the internet gateway.
* **owner_id**
(`string`):
The ID of the AWS account that owns the internet gateway.
* **region**
(`string`):
The AWS region.
* **tags**
(`key_value[]`):
Any tags assigned to the internet gateway.
