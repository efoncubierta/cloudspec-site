---
title: "Running CloudSpec"
linkTitle: "Running CloudSpec"
weight: 2
description: >
  Your first run of CloudSpec.
---

To run CloudSpec, you first need a resource in a cloud provider that you can validate. Please feel free to fit this tutorial to a real resource you own. In this example, we are using an EC2 instance in AWS, which has a tag `environment=production`. We want to prove whether the EBS volumes attached to the EC2 instance have a minimum of 100GB of space and are encrypted.

First, you define a CloudSpec `plan`. A plan is your validation project. Everything that you declare in CloudSpec is part of a plan or a module. A plan can have modules, groups or rules. For simplicity, we are not covering modules, groups and many other directives in this tutorial. Please refer to the [CloudSpec syntax](../../syntax) documentation for a full description of the CloudSpec logical language.

A plan is a block that starts with `plan:plan_name` and ends with `end plan`.

```
plan "My production environment"
# TODO add validation directives
end plan
```

Comments start with a `#`, and everything from it to the end line is ignored.

Now that we have a plan, we can declare a rule to validate our EC2 instance with the requirement dictated above: _EBS volumes attached to the EC2 instance have a minimum of 100GB of space and are encrypted_. We do that as follows:

```
plan "My production environment"
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
    end rule
end plan
```

Ok, that's a lot. But you probably understood everything. The beauty of the CloudSpec syntax is that you can declare validation rules using plain English language. Let's dissect all that's going on.

First, a rule declaration starts with `rule:rule_name` and ends with `end rule`. A rule has a scope, which is the subset of your AWS resources to validate. In our example, the scope is all EC2 instances with tag `environment=production`. You define the scope with the `on` and `with`directives. With `on` you select a resource type, and with `with` narrow down the selection to more specific resources.

```
...
        on aws:ec2:instance
        with tags["environment"] equal to "production"
...
```

Please refer to the [providers](../../providers) documentation for a full list of supported resource types and their properties and associations.

Once you select the resources that you want to validate, you use the `assert` directive to do the actual validation. The syntax of `assert` is similar to `with`, but while the later is used to narrow down the scope, the former produces an error if any resource doesn't match the predicate.

Please refer to the [member path](../../syntax/member-path) and [predicates](../../syntax/predicates) documentation for how to address resource properties and supported predicates.

Finally, it's time to run your plan. The best way to do it is via the Docker container provider. It has everything you need to run CloudSpec. Alternatively, you can build CloudSpec yourself (see the [development](../../development) documentation). Save your plan in a `specs/myplan.csplan` file and run the following command.

```
export AWS_ACCESS_KEY_ID=***
export AWS_SECRET_ACCESS_KEY=***
export AWS_REGION=eu-west-1
docker run -v "./specs:/specs" -e AWS_ACCESS_KEY_ID -e AWS_SECRET_ACCESS_KEY -e AWS_REGION efoncubierta/cloudspec run -p specs/my.csplan
```

If you are running the docker container in AWS with a dedicated IAM role attached, you can omit the AWS environment variables.

You should get an output report like the following.

```
|                        Test                        | #Re  | %RS  | #Va  | %VS  |
|----------------------------------------------------|------|------|------|------|
| My production environment                          |  1   | 100% |  1   | 100% |
| [R]  EC2 instances should have enough disk spac... |  1   | 100% |  1   | 100% |
|----------------------------------------------------|------|------|------|------|
```

Voilà! You just run your first CloudSpec plan. Congratulations!