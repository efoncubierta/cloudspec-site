---
title: "Running CloudSpec"
linkTitle: "Running CloudSpec"
weight: 2
description: >
  Your first run of CloudSpec.
---

To run CloudSpec, you first need a resource in a cloud provider that you can validate. Please feel free to fit this tutorial to a real resource you own. In this example, we are using an EC2 instance in AWS, which has a tag `environment=production`. We want to prove whether the EBS volumes attached to the EC2 instance have a minimum of 100GB of space and are encrypted.

First, you create a CloudSpec `module` directory. Everything that you declare in CloudSpec is part of a module.

```
mkdir my_module
```

Now that we have a module directory, we can declare a rule to validate our EC2 instance with the requirement dictated above: _EBS volumes attached to the EC2 instance have a minimum of 100GB of space and are encrypted_. We do that by creating a file `rules.cs` within our module directory. The name of the file doesn't matter as long its extension is `.cs`:

```bash
tee my_module/rules.cs <<EOF
# My validation rule for instances
rule "EC2 instances should have enough disk space and be encrypted"
    on aws:ec2:instance
    with tags["environment"] equal to "production"
    assert block_device_mappings (
        ebs (
            > volume (
                size gte 100 and
                encryption is enabled
            )
        )
    )
end
EOF
```

Ok, that's a lot. But you probably understood everything. The beauty of the CloudSpec syntax is that you can declare validation rules using plain English language. Let's dissect all that's going on.

First, a rule declaration starts with `rule:rule_name` and ends with `end`. A rule has a scope, which is the subset of your AWS resources to validate. In our example, the scope is all EC2 instances with tag `environment=production`. You define the scope with the `on` and `with`directives. With `on` you select a resource type, and with `with` narrow down the selection to more specific resources. Comments start with a `#`, and everything from it to the end of the line is ignored.

Please refer to the [CloudSpec syntax](../../syntax) documentation for a full description of the CloudSpec logical language.

```
...
    on aws:ec2:instance
    with tags["environment"] equal to "production"
...
```

Please refer to the [providers](../../providers) documentation for a full list of supported resource types and their properties and associations.

Once you select the resources that you want to validate, you use the `assert` directive to do the actual validation. The syntax of `assert` is similar to `with`, but while the later is used to narrow down the scope, the former produces an error if any resource doesn't match the predicate.

Please refer to the [member path](../../syntax/member-path) and [predicates](../../syntax/predicates) documentation for how to address resource properties and supported predicates.

Finally, it's time to run your module. The best way to do it is via the Docker container provider. It has everything you need to run CloudSpec. Alternatively, you can build CloudSpec yourself (see the [development](../../development) documentation).

```
export AWS_ACCESS_KEY_ID=***
export AWS_SECRET_ACCESS_KEY=***
export AWS_REGION=eu-west-1
docker run -v "/my_module:/my_module" -e AWS_ACCESS_KEY_ID -e AWS_SECRET_ACCESS_KEY -e AWS_REGION efoncubierta/cloudspec run -p my_module
```

If you are running the docker container in AWS with a dedicated IAM role attached, you can omit the AWS environment variables.

```
docker run -v "/my_module:/my_module" efoncubierta/cloudspec run -p my_module
```

You should get an output report like the following.

<p align="center"><img style="max-width: 100%" src="/images/demo.gif?raw=true"/></p>

Voilà! You just run your first CloudSpec validation. Congratulations!