---
title: "Examples"
linkTitle: "Examples"
weight: 30
description: >
  Some CloudSpec examples.
---

```
set aws:regions = ["us-east-1", "eu-west-1"]

use "my_module.cs" as my_mod

rule "Buckets must have access logs enabled"
    on aws:s3:bucket
    assert access_logs is enabled
end

rule "Instances must use 'gp2' volumes and be at least 50GiBs large."
    on aws:ec2:instance
    with tags["environment"] equal to "production"
    assert devices (
        > volume (
            type equal to "gp2" and
            size gte 50
        )
    )
end
```