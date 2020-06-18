---
title: "Examples"
linkTitle: "Examples"
weight: 30
description: >
  Some CloudSpec examples.
---

```
plan "Production environment"
    set aws:regions = ["us-east-1", "eu-west-1"]

    use module "my_module.csm"

    group "S3 validations"
        use rule "my_s3_rule.csr"

        rule "Buckets must have access logs enabled"
            on aws:s3:bucket
            assert access_logs is enabled
        end rule
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
        end rule
    end group
end plan
```