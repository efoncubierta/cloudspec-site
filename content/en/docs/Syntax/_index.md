---
title: "Syntax"
linkTitle: "Syntax"
weight: 10
description: >
  The CloudSpec logical language syntax.
---

At a high-level, it all starts with a `module`. A `module` is a directory contains one or more `.cs` files. Each file can declare one or many `input` variables, configuration parameters for the module using `set`, validation `rule`s, or even import other module directories using `use`. A `rule` defines a validation scope using `on` and `with`. `rule` defines validations using `assert`.

All keywords are case-insensitive (e.g. both `rule` and `RULE` are valid).

## `module` directory

A module is a directory containing one or more CloudSpec files. Modules are designed to be reusable. CloudSpec runs on an initial module that can use other modules, and those modules can use other modules.

```
my_module/
  - modules.cs
  - inputs.cs
  - rules.cs
```

A module must have at least one `rule`, either declared in the same module or imported from another module.

## `.cs` file

```
(input ...)*
(set ...)*
(use ...)*
(rule ...)*
```

Within a `.cs` file you can declare one or many of the following:

- Zero or more `input`: an input variable (see: [input declaration](#input-declaration))
- Zero or more `set`: set a global configuration (see: [set declaration](#set-declaration))
- Zero or more `use`: import a module from a file (see: [use declaration](#use-declaration))
- Zero or more `rule`: a validation rule (see: [rule declaration](#rule-declaration))

## `rule` declaration

Validation rules are the essential ingredient of CloudSpec. At least one rule must exist in a `module`. Without rules there are not validations.

```
rule :rule_name
    on :resource_reference
    (with ...)?
    assert ...
end
```

Where `:rule_name` is a quoted `"string"`. for example `"My rule"`, and `:resource_reference` is a unique resource definition reference (e.g. aws:ec2:instance).

Rules are defined within a scope. The scope is the set of resources that will be validated. A scope if defined as follows:

- The `on` statement selects all resources of a kind. For example, all EC2 instances.
- The `with` statements narrow down the selected resources. For example, all EC2 instances of type m5.large.

`with` statements are optional. If absent, all resources of a kind will be validated. At least one `assert` must be declared on each rule.

Within a `rule` you can declare the following:

- Zero or more `with`: filters to narrow down the scope (see: [with declaration](#with-declaration))
- Zero or more `assert`: validations (see: [assert declaration](#assert-declaration))

## `with` declaration

A `with` statement narrows down the scope of the rule. It is similar in essence to the `WHERE` clause in SQL.

```
with :member_path :predicate
(and :member_path :predicate)*
```

Where `:member_path` (see [member paths](members-path)) is a path to a property in the resource, and `:predicate` (see [predicates](predicates)) is the actual validation upon that property. If all `with` statements were true on a resource, the resource would be added to the validation scope.

Multiple `with` declarations can be concatenated with `and`.

## `assert` declaration

An `assert` statement does the actual validation of the resources in the scope. Its syntax is similar to `with`, but its purpose is completely different. While `with` narrows down the validation scope, `assert` validates that the resources in the validation scope are correctly configured, or it will produce an error.

```
assert :member_path :predicate
(and :member_path :predicate)*
```

Where `:member_path` (see [member paths](members-paths)) is a path to a property in the resource, and `:predicate` (see [predicates](predicates)) is the actual validation upon that property. If any `assert` statement was true on a resource, an error would be produced.

Multiple `assert` declarations can be concatenated with `and`.

## `use` declaration

This is used to import other modules.

```
use :file_path as :module_identifier
```

Where `:file_path` is a system path that is either absolute or relative to the file importing it, and `:module_identifier` is a unique ID within the module (e.g. my_mod).

## `input` declaration

*Not yet supported.*

```
input :input_name as :input_def
```

## `set` declaration

CloudSpec have global configuration parameters, or variables. All configuration parameters have a default value. Each provider define its own configuration parameters. For example, the AWS provider defines an `aws:regions` configuration parameter that allows you to limit the resource crawling and validation to a set of regions. Its default value is
_ALL REGIONS_.

```
set :config_ref = :value
```

Where `:config_ref` is the configuration reference, for example `aws:regions`, and value is either a `number`, a `string` or a `boolean` value.

For a complete list of supported configurations, see the CloudSpec [reference documentation](/doc/providers/index.md)