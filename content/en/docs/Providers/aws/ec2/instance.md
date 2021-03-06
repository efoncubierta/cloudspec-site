---
title: "EC2 Instance"
linkTitle: "EC2 Instance"
description: >
  All about resource aws:ec2:instance.
---


## Members
* **architecture**
(`string`):
The architecture of the image.
Allowed values: `i386`, `x86_64`, `arm64`, `null`
* **block_device_mappings**
(`nested[]`):
Any block device mapping entries for the instance.
    * **device_name**
(`string`):
The device name.
    * **ebs**
(`nested`):
Parameters used to automatically set up EBS volumes when the instance is launched.
        * **attach_time**
(`date`):
The time stamp when the attachment initiated.
        * **delete_on_termination**
(`boolean`):
Indicates whether the volume is deleted on instance termination.
        * **status**
(`string`):
The attachment state.
Allowed values: `attaching`, `attached`, `detaching`, `detached`, `null`
        * **&gt;volume**
([aws:ec2:volume](../../aws/ec2/volume)):
The EBS volume
* **cpu_options**
(`nested`):
The CPU options for the instance.
    * **core_count**
(`number`):
The number of CPU cores for the instance.
    * **threads_per_core**
(`number`):
The number of threads per CPU core.
* **ebs_optimized**
(`boolean`):
Indicates whether the instance is optimized for Amazon EBS I/O.
* **elastic_inference_accelerators**
(`string[]`):
The elastic inference accelerator associated with the instance.
* **ena_support**
(`boolean`):
Specifies whether enhanced networking with ENA is enabled.
* **hibernation_configured**
(`boolean`):
Indicates whether the instance is enabled for hibernation.
* **hypervisor**
(`string`):
The hypervisor type of the instance.
Allowed values: `ovm`, `xen`, `null`
* **instance_id**
(`string`):
The ID of the instance.
* **instance_lifecycle**
(`string`):
Indicates whether this is a Spot Instance or a Scheduled Instance.
Allowed values: `spot`, `scheduled`, `null`
* **instance_type**
(`string`):
The instance type.
Allowed values: `t1.micro`, `t2.nano`, `t2.micro`, `t2.small`, `t2.medium`, `t2.large`, `t2.xlarge`, `t2.2xlarge`, `t3.nano`, `t3.micro`, `t3.small`, `t3.medium`, `t3.large`, `t3.xlarge`, `t3.2xlarge`, `t3a.nano`, `t3a.micro`, `t3a.small`, `t3a.medium`, `t3a.large`, `t3a.xlarge`, `t3a.2xlarge`, `m1.small`, `m1.medium`, `m1.large`, `m1.xlarge`, `m3.medium`, `m3.large`, `m3.xlarge`, `m3.2xlarge`, `m4.large`, `m4.xlarge`, `m4.2xlarge`, `m4.4xlarge`, `m4.10xlarge`, `m4.16xlarge`, `m2.xlarge`, `m2.2xlarge`, `m2.4xlarge`, `cr1.8xlarge`, `r3.large`, `r3.xlarge`, `r3.2xlarge`, `r3.4xlarge`, `r3.8xlarge`, `r4.large`, `r4.xlarge`, `r4.2xlarge`, `r4.4xlarge`, `r4.8xlarge`, `r4.16xlarge`, `r5.large`, `r5.xlarge`, `r5.2xlarge`, `r5.4xlarge`, `r5.8xlarge`, `r5.12xlarge`, `r5.16xlarge`, `r5.24xlarge`, `r5.metal`, `r5a.large`, `r5a.xlarge`, `r5a.2xlarge`, `r5a.4xlarge`, `r5a.8xlarge`, `r5a.12xlarge`, `r5a.16xlarge`, `r5a.24xlarge`, `r5d.large`, `r5d.xlarge`, `r5d.2xlarge`, `r5d.4xlarge`, `r5d.8xlarge`, `r5d.12xlarge`, `r5d.16xlarge`, `r5d.24xlarge`, `r5d.metal`, `r5ad.large`, `r5ad.xlarge`, `r5ad.2xlarge`, `r5ad.4xlarge`, `r5ad.8xlarge`, `r5ad.12xlarge`, `r5ad.16xlarge`, `r5ad.24xlarge`, `x1.16xlarge`, `x1.32xlarge`, `x1e.xlarge`, `x1e.2xlarge`, `x1e.4xlarge`, `x1e.8xlarge`, `x1e.16xlarge`, `x1e.32xlarge`, `i2.xlarge`, `i2.2xlarge`, `i2.4xlarge`, `i2.8xlarge`, `i3.large`, `i3.xlarge`, `i3.2xlarge`, `i3.4xlarge`, `i3.8xlarge`, `i3.16xlarge`, `i3.metal`, `i3en.large`, `i3en.xlarge`, `i3en.2xlarge`, `i3en.3xlarge`, `i3en.6xlarge`, `i3en.12xlarge`, `i3en.24xlarge`, `i3en.metal`, `hi1.4xlarge`, `hs1.8xlarge`, `c1.medium`, `c1.xlarge`, `c3.large`, `c3.xlarge`, `c3.2xlarge`, `c3.4xlarge`, `c3.8xlarge`, `c4.large`, `c4.xlarge`, `c4.2xlarge`, `c4.4xlarge`, `c4.8xlarge`, `c5.large`, `c5.xlarge`, `c5.2xlarge`, `c5.4xlarge`, `c5.9xlarge`, `c5.12xlarge`, `c5.18xlarge`, `c5.24xlarge`, `c5.metal`, `c5d.large`, `c5d.xlarge`, `c5d.2xlarge`, `c5d.4xlarge`, `c5d.9xlarge`, `c5d.12xlarge`, `c5d.18xlarge`, `c5d.24xlarge`, `c5d.metal`, `c5n.large`, `c5n.xlarge`, `c5n.2xlarge`, `c5n.4xlarge`, `c5n.9xlarge`, `c5n.18xlarge`, `cc1.4xlarge`, `cc2.8xlarge`, `g2.2xlarge`, `g2.8xlarge`, `g3.4xlarge`, `g3.8xlarge`, `g3.16xlarge`, `g3s.xlarge`, `g4dn.xlarge`, `g4dn.2xlarge`, `g4dn.4xlarge`, `g4dn.8xlarge`, `g4dn.12xlarge`, `g4dn.16xlarge`, `cg1.4xlarge`, `p2.xlarge`, `p2.8xlarge`, `p2.16xlarge`, `p3.2xlarge`, `p3.8xlarge`, `p3.16xlarge`, `p3dn.24xlarge`, `d2.xlarge`, `d2.2xlarge`, `d2.4xlarge`, `d2.8xlarge`, `f1.2xlarge`, `f1.4xlarge`, `f1.16xlarge`, `m5.large`, `m5.xlarge`, `m5.2xlarge`, `m5.4xlarge`, `m5.8xlarge`, `m5.12xlarge`, `m5.16xlarge`, `m5.24xlarge`, `m5.metal`, `m5a.large`, `m5a.xlarge`, `m5a.2xlarge`, `m5a.4xlarge`, `m5a.8xlarge`, `m5a.12xlarge`, `m5a.16xlarge`, `m5a.24xlarge`, `m5d.large`, `m5d.xlarge`, `m5d.2xlarge`, `m5d.4xlarge`, `m5d.8xlarge`, `m5d.12xlarge`, `m5d.16xlarge`, `m5d.24xlarge`, `m5d.metal`, `m5ad.large`, `m5ad.xlarge`, `m5ad.2xlarge`, `m5ad.4xlarge`, `m5ad.8xlarge`, `m5ad.12xlarge`, `m5ad.16xlarge`, `m5ad.24xlarge`, `h1.2xlarge`, `h1.4xlarge`, `h1.8xlarge`, `h1.16xlarge`, `z1d.large`, `z1d.xlarge`, `z1d.2xlarge`, `z1d.3xlarge`, `z1d.6xlarge`, `z1d.12xlarge`, `z1d.metal`, `u-6tb1.metal`, `u-9tb1.metal`, `u-12tb1.metal`, `u-18tb1.metal`, `u-24tb1.metal`, `a1.medium`, `a1.large`, `a1.xlarge`, `a1.2xlarge`, `a1.4xlarge`, `a1.metal`, `m5dn.large`, `m5dn.xlarge`, `m5dn.2xlarge`, `m5dn.4xlarge`, `m5dn.8xlarge`, `m5dn.12xlarge`, `m5dn.16xlarge`, `m5dn.24xlarge`, `m5n.large`, `m5n.xlarge`, `m5n.2xlarge`, `m5n.4xlarge`, `m5n.8xlarge`, `m5n.12xlarge`, `m5n.16xlarge`, `m5n.24xlarge`, `r5dn.large`, `r5dn.xlarge`, `r5dn.2xlarge`, `r5dn.4xlarge`, `r5dn.8xlarge`, `r5dn.12xlarge`, `r5dn.16xlarge`, `r5dn.24xlarge`, `r5n.large`, `r5n.xlarge`, `r5n.2xlarge`, `r5n.4xlarge`, `r5n.8xlarge`, `r5n.12xlarge`, `r5n.16xlarge`, `r5n.24xlarge`, `inf1.xlarge`, `inf1.2xlarge`, `inf1.6xlarge`, `inf1.24xlarge`, `null`
* **kernel_id**
(`string`):
The kernel associated with this instance, if applicable.
* **key_name**
(`string`):
The name of the key pair, if this instance was launched with an associated key pair.
* **launch_time**
(`date`):
The time the instance was launched.
* **licenses**
(`string[]`):
The license configurations.
* **monitoring**
(`nested`):
The monitoring for the instance.
    * **state**
(`string`):
Indicates whether detailed monitoring is enabled. Otherwise, basic monitoring is enabled.
Allowed values: `disabled`, `disabling`, `enabled`, `pending`, `null`
* **network_interfaces**
(`nested[]`):
[EC2-VPC] The network interfaces for the instance.
    * **interface_type**
(`string`):
Describes the type of network interface.
    * **ipv6_addresses**
(`string[]`):
One or more IPv6 addresses associated with the network interface.
    * **owner_id**
(`string`):
The ID of the AWS account that created the network interface.
    * **private_dns_name**
(`string`):
The private DNS name.
    * **private_ip_address**
(`string`):
The IPv4 address of the network interface within the subnet.
    * **private_ip_addresses**
(`nested[]`):
One or more private IPv4 addresses associated with the network interface.
        * **primary**
(`boolean`):
Indicates whether this IPv4 address is the primary private IP address of the network interface.
        * **private_dns_name**
(`string`):
The private IPv4 DNS name.
        * **private_ip_address**
(`string`):
The private IPv4 address of the network interface.
    * **source_dest_check**
(`boolean`):
Indicates whether to validate network traffic to or from this network interface.
    * **status**
(`string`):
The status of the network interface.
Allowed values: `available`, `associated`, `attaching`, `in-use`, `detaching`, `null`
    * **&gt;groups**
([aws:ec2:security_group](../../aws/ec2/security_group)[]):
One or more security groups
    * **&gt;network_interface**
([aws:ec2:network_interface](../../aws/ec2/network_interface)):
The network interface
    * **&gt;subnet**
([aws:ec2:subnet](../../aws/ec2/subnet)):
The subnet
    * **&gt;vpc**
([aws:ec2:vpc](../../aws/ec2/vpc)):
The VPC
* **outpost_arn**
(`string`):
The Amazon Resource Name (ARN) of the Outpost.
* **placement**
(`nested`):
The location where the instance launched, if applicable.
    * **affinity**
(`string`):
The affinity setting for the instance on the Dedicated Host.
    * **availability_zone**
(`string`):
The Availability Zone of the instance.
    * **group_name**
(`string`):
The name of the placement group the instance is in.
    * **partition_number**
(`number`):
The number of the partition the instance is in.
    * **tenancy**
(`string`):
The tenancy of the instance (if the instance is running in a VPC).
Allowed values: `default`, `dedicated`, `host`, `null`
* **platform**
(`string`):
The value is `Windows` for Windows instances; otherwise blank.
Allowed values: `Windows`, `null`
* **private_dns_name**
(`string`):
(IPv4 only) The private DNS hostname name assigned to the instance.
* **private_ip_address**
(`string`):
The private IPv4 address assigned to the instance.
* **product_codes**
(`nested[]`):
The product codes attached to this instance, if applicable.
    * **id**
(`string`):
The product code.
    * **type**
(`string`):
The type of product code.
Allowed values: `devpay`, `marketplace`, `null`
* **public_dns_name**
(`string`):
(IPv4 only) The public DNS name assigned to the instance.
* **public_ip_address**
(`string`):
The public IPv4 address assigned to the instance, if applicable.
* **region**
(`string`):
The AWS region.
* **root_device_name**
(`string`):
The device name of the root device volume.
* **root_device_type**
(`string`):
The root device type used by the AMI.
Allowed values: `ebs`, `instance-store`, `null`
* **source_dest_check**
(`boolean`):
Specifies whether to enable an instance launched in a VPC to perform NAT.
* **sriov_net_support**
(`string`):
Specifies whether enhanced networking with the Intel 82599 Virtual Function interface is enabled.
* **state**
(`string`):
The current state of the instance.
Allowed values: `pending`, `running`, `shutting-down`, `terminated`, `stopping`, `stopped`, `null`
* **tags**
(`key_value[]`):
Any tags assigned to the instance.
* **virtualization_type**
(`string`):
The virtualization type of the instance.
Allowed values: `hvm`, `paravirtual`, `null`
* **&gt;capacity_reservation**
([aws:ec2:capacity_reservation](../../aws/ec2/capacity_reservation)):
The Capacity Reservation
* **&gt;elastic_gpus**
([aws:ec2:elastic_gpu](../../aws/ec2/elastic_gpu)[]):
The Elastic GPU associated with the instance
* **&gt;iam_instance_profile**
([aws:iam:iam_instance_profile](../../aws/iam/iam_instance_profile)):
The IAM instance profile associated with the instance, if applicable
* **&gt;image**
([aws:ec2:image](../../aws/ec2/image)):
The AMI used to launch the instance
* **&gt;security_groups**
([aws:ec2:security_group](../../aws/ec2/security_group)[]):
The security groups for the instance
* **&gt;subnet**
([aws:ec2:subnet](../../aws/ec2/subnet)):
[EC2-VPC] The subnet in which the instance is running
* **&gt;vpc**
([aws:ec2:vpc](../../aws/ec2/vpc)):
[EC2-VPC] The VPC in which the instance is running
