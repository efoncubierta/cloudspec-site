---
title: "Member Path"
linkTitle: "Member Path"
weight: 10
description: >
  Full details about member paths.
---

A resource have two types of members: property and association. A property has a value, while an association is a
reference to another resource. Both `with` and `assert` statements works on properties and associations. A property
can also hold nested properties. So `:member_path` can have different shapes, but it must always end with a property
as it is its value what gets validated against the predicate.

**Single property**

`my_property :predicate`

**Key-Value property**

`my_property["my_key"] :predicate`

**Nested property**

```
my (
    nested (
        property :predicate
    )
)
```

**Properties in an associated resource**

```
> my_association (
    my_property :predicate
)
```

**Nested property in an associated resource**

```
> my_association (
    my (
        nested (
            property :predicate
        )
    )
)
```

**Property in an associated resource in an associated resource**

```
> my_association (
    > another_association (
        my_property :predicate
    )
)
```

**Property in an associated resource in a nested property**

```
my (
    nested (
        > association (
            my_property :predicate
        )
    )
)
```

**Complex nested properties with associations**

```
my (
    nested (
        my_property :predicate
        and my_other_property :predicate
        and > my_association (
            one_property["key"] :predicate
            and another (
                nested (
                    property :predicate
                )
            )
        )
        and > my_other_association (
            one_property :predicate
            and > another_association (
                property :predicate
            )
        )
    )
)
```