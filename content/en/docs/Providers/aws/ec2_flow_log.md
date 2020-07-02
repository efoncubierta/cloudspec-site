---
title: "VPC Flow Log"
linkTitle: "VPC Flow Log"
description: >
  All about resource aws:ec2:flow_log.
---


## Members
* **creation_time**
(`date`):
The date and time the flow log was created.
* **deliver_logs_error_message**
(`string`):
Information about the error that occurred.
* **deliver_logs_permission_arn**
(`string`):
The ARN of the IAM role that posts logs to CloudWatch Logs.
* **deliver_logs_status**
(`string`):
The status of the logs delivery.
* **flow_log_id**
(`string`):
The flow log ID.
* **flow_log_status**
(`string`):
The status of the flow log.
* **log_destination**
(`string`):
Specifies the destination to which the flow log data is published.
* **log_destination_type**
(`string`):
Specifies the type of destination to which the flow log data is published.
Allowed values: `cloud-watch-logs`, `s3`, `null`
* **log_format**
(`string`):
The format of the flow log record.
* **log_group_name**
(`string`):
The name of the flow log group.
* **max_aggregation_interval**
(`number`):
The maximum interval of time, in seconds, during which a flow of packets is captured and aggregated into a flow log record.
* **region**
(`string`):
The AWS region.
* **resource_id**
(`string`):
The ID of the resource on which the flow log was created.
* **tags**
(`key_value[]`):
The tags for the flow log.
* **traffic_type**
(`string`):
The type of traffic captured for the flow log.
Allowed values: `ACCEPT`, `REJECT`, `ALL`, `null`
