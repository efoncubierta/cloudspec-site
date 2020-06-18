---
title: "Overview"
linkTitle: "Overview"
weight: 1
description: >
  A first glance of CloudSpec!
---

## Introduction
CloudSpec is an open source tool for validating your resources in your cloud providers using a logical language that everybody can understand. With its reasonably simple syntax, you can validate the configuration of your cloud resources, avoiding mistakes that can lead to availability or confidentiality issues. 

```
plan "Production environment"
    set aws:regions = ["us-east-1", "eu-west-1"]

    use module "my_module.csm"

    group "S3 validations"
        use rule "my_s3_rule.csr"

        rule "Buckets must have access logs enabled"
        on aws:s3:bucket
        assert access_logs is enabled
    end group

    group "EC2 validations"
        use rule "my_ec2_rule.csr"

        rule "Instances must use 'gp2' volumes and be at least 50GiBs large."
        on aws:ec2:instance
        with tags["environment"] equal to "production"
        assert devices (
            > volume (
                type equal to "gp2" and
                size gte 50
            )
        )
    end group
end plan
```

## Providers

CloudSpec itself does not support any resource. The core of CloudSpec is the syntax interpreter for the specification files and its validation engine. However, CloudSpec does use providers, which are extensions to CloudSpec supporting each different type of resource.

A provider defines the shape of each resource type, properties and associations, and the logic to load those resources.

You can find the available providers and resources they provide in the CloudSpec Reference documentation.

