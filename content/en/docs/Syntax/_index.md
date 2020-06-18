---
title: "Syntax"
linkTitle: "Syntax"
weight: 9
description: >
  The CloudSpec logical language syntax.
---

At a high-level, it all starts with a `plan`. A `plan` contains one or more `module`, `group` or `rule`. Each `module` 
contains one or more `group` or `rule`. Each `group` contains one or more validation `rule`. `plan` and `module` can 
define `input` variables. `module`, `group` and `rule` can be imported from other files (i.e. `use (module|group|rule)`)
,or defined in-line. `plan`, `module` and `group` can `set` configuration parameters. `rule` defines a validation scope 
using `on` and `with`. `rule` defines validations using `assert`.

All keywords are case-insensitive (e.g. both `plan` and `PLAN` are valid).

## `plan` declaration

To validate your resources you need one `plan`, and only one `plan`. Everything in CloudSpec is declared within a 
`plan`. A `plan` is declared in a file with `.csp` extension. 

```
plan :plan_name
    (input ...)*
    (set ...)*
    (use module|group|rule ...)*
    (group ...)*
    (rule ...)*
end plan
```

Where `:plan_name` is a quoted `"string"`. For example, `"My plan"`.

Within a `plan` you can declare the following:

- Zero or more `input`: an input variable (see: [input declaration](#input-declaration))
- Zero or more `set`: set a global configuration (see: [set declaration](#set-declaration))
- Zero or more `use module|group|rule`: import a module, group or rule from a file (see: [use declaration](#use-declaration))
- Zero or more `group`: a group of rules (see: [group declaration](#group-declaration))
- Zero or more `rule`: a validation rule (see: [rule declaration](#rule-declaration))

A plan must have at least one `rule` declared either in-line, within a group, within a module or imported.

## `module` declaration

Modules are like plan, but reusable. Different plans can import the same module. A `module` is declared in a file
with the `.csm` extension.

```
module :module_name
    (input ...)*
    (set ...)*
    (use module|group|rule ...)*
    (group ...)*
    (rule ...)*
end module
```

Where `:module_name` is a quoted `"string"`. For example, `"My module"`.

Within a `module` you can declare the following:

- Zero or more `input`: an input variable (see: [input declaration](#input-declaration))
- Zero or more `set`: set a global configuration (see: [set declaration](#set-declaration))
- Zero or more `use module|group|rule`: import a module|group|rule from a file (see: [use declaration](#use-declaration))
- Zero or more `group`: a group of rules (see: [group declaration](#group-declaration))
- Zero or more `rule`: a validation rule (see: [rule declaration](#rule-declaration))

A module must have at least one `rule` declared either in-line, within a group, within another module or imported.

## `group` declaration

Rules that are alike or share the same configuration parameters can be grouped. A `group` can be declared in-line or its
own file with the `.csg` extension.

```
group :group_name
    (set ...)*
    (use rule ...)*
    (rule ...)*
end group
```

Where `:module_name` is a quoted `"string"`. For example, `"My group"`.

Within a `group` you can declare the following:

- Zero or more `set`: set a global configuration (see: [set declaration](#set-declaration))
- Zero or more `use rule`: import a rule from a file (see: [use declaration](#use-declaration))
- Zero or more `rule`: a validation rule (see: [rule declaration](#rule-declaration))

A group must have at least one `rule` declared either in-line or imported.

## `rule` declaration

Validation rules are the essential ingredient of CloudSpec. At least one rule must exist in a `plan`, `module` or
`group`. Without rules there are not validations. A `rule` can be declared in-line or its own file with the `.csr`
extension.

```
rule :rule_name
    on :resource_reference
    (with ...)?
    assert ...
end rule
```

Where `:rule_name` is a quoted `"string"`. for example `"My rule"`, and `:resource_reference` is a unique
resource definition reference (e.g. aws:ec2:instance).

Rules are defined within a scope. The scope is the set of resources that will be validated. A scope if defined as
follows:

- The `on` statement selects all resources of a kind. For example, all EC2 instances.
- The `with` statements narrow down the selected resources. For example, all EC2 instances of type m5.large.

`with` statements are optional. If absent, all resources of a kind will be validated. At least one `assert` must be
declared on each rule.

Within a `rule` you can declare the following:

- Zero or more `with`: filters to narrow down the scope (see: [with declaration](#with-declaration))
- Zero or more `assert`: validations (see: [assert declaration](#assert-declaration))

## `with` declaration

A `with` statement narrows down the scope of the rule. It is similar in essence to the `WHERE` clause in SQL.

```
with :member_path :predicate
(and :member_path :predicate)*
```

Where `:member_path` (see [member paths](#members-paths)) is a path to a property in the resource, and `:predicate` 
(see [predicates](#predicates)) is the actual validation upon that property. If all `with` statements were true on a
resource, the resource would be added to the validation scope.

Multiple `with` declarations can be concatenated with `and`.

## `assert` declaration

An `assert` statement does the actual validation of the resources in the scope. Its syntax is similar to `with`, but its
purpose is completely different. While `with` narrows down the validation scope, `assert` validates that the resources 
in the validation scope are correctly configured, or it will produce an error.

```
assert :member_path :predicate
(and :member_path :predicate)*
```

Where `:member_path` (see [member paths](#members-paths)) is a path to a property in the resource, and `:predicate` 
(see [predicates](#predicates)) is the actual validation upon that property. If any `assert` statement was true on a
resource, an error would be produced.

Multiple `assert` declarations can be concatenated with `and`.

## `use` declaration

This is used to compose a spec with multiple files. Modules, groups and rules can be defined and imported into a plan
from other files.

```
use (module|group|rule) :file_path
```

Where `:file_path` is a system path that is either absolute or relative to the file importing it.

## `input` declaration

*Not yet supported.*

```
input :input_name as :input_def
```

## `set` declaration

CloudSpec have global configuration parameters, or variables. All configuration parameters have a default value. Each
provider define its own configuration parameters. For example, the AWS provider defines an `aws:regions` configuration
parameter that allows you to limit the resource crawling and validation to a set of regions. Its default value is
_ALL REGIONS_.

```
set :config_ref = :value
```

Where `:config_ref` is the configuration reference, for example `aws:regions`, and value is either a `number`, a
`string` or a `boolean` value.

For a complete list of supported configurations, see the CloudSpec [reference documentation](/doc/providers/index.md)