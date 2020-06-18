---
title: "Predicates"
linkTitle: "Predicates"
weight: 11
description: >
  Describe all evaluators for the property values.
---

Predicates validate a property value, and are used to narrow down validation scopes and asserting resource properties. CloudSpec currently support the predicates below. Keywords marked with `?` are optional, and can be used improve readability to make the syntax feel more natural. For example, both `is > ip address "10.0.0.1"` and `> ip "10.0.0.1"` are the same predicates.

For more information about values, see the [Property Values](property-values)) section.

**For any value:**

- `is? null`: value doesn't exist.
- `is? not null`: value exists.
- `is? == :value`: value is equal to another value.
- `is? equal to :value`: synonym of `== :value`.
- `is? != :value`: value is not equal to another value.
- `is? not equal to :value`: synonym of `!= :value`.
- `is? within [:value1, :value2...]`: value is within a list of values.
- `is? not within [:value1, :value2...]`: value is not within a list of values.

**For numeric values:**

- `is? > :number`: number value is greater than another number.
- `is? greater than :number`: synonym of `> :number`
- `is? gt :number`: synonym of `> :number`
- `is? >= :number`:number value is greater than or equal to another number.
- `is? greater than or equal to :number`: synonym of `>= :number`
- `is? gte :number`: synonym of `>= :number`
- `is? < :number`: number value is less than another number.
- `is? less than :number`: synonym of `> :number`
- `is? lt :number`: synonym of `< :number`
- `is? <= :number`: number value is less than or equal to another number.
- `is? less than or equal to :number`: synonym of `<= :number`
- `is? lte :number`: synonym of `<= :number`
- `is? between :number and :number`: number value is between two numbers.

**For string values:**

- `is? empty`: synonym of `is equal to ""`.
- `is? not empty`: synonym of `is not equal to ""`.
- `is? starting with :string`: string value starts with another string.
- `is? not starting :string`: string value does not start with another string.
- `is? ending with :string`: string value ends with another string.
- `is? not ending with :string`: string value does not end with another string.
- `is? containing :string`: string value contains another string.
- `is? not containing :string`: string value does not contain another string.

**For string values representing an IP address**

- `is? > ip address? :ip_address`: ip address is greater than another ip address.
- `is? greater than ip address? :ip_address`: synonym of `> ip :ip_address`.
- `is? gt ip address? :ip_address`: synonym of `> ip :ip_address`.
- `is? >= ip address? :ip_address`: ip address is greater or equal than another ip address.
- `is? greater than or equal to ip address? :ip_address`: synonym of `>= ip :ip_address`.
- `is? gte ip address? :ip_address`: synonym of `>= ip :ip_address`.
- `is? < id address? :ip_address`: ip address is less than another ip address.
- `is? less than ip address? :ip_address`: synonym of `< ip :ip_address`.
- `is? lt ip address? :ip_address`: synonym of `> ip :ip_address`.
- `is? <= ip address? :ip_address`: ip address is less or equal than another ip address.
- `is? less than or equal to ip address? :ip_address`: synonym of `<= ip :ip_address`.
- `is? lte ip address? :ip_address`: synonym of `<= ip :ip_address`.
- `is? within network cidr? :cidr_block`: ip address is within a network.
- `is? not within network cidr? :cidr_block`: ip address is not within a network.
- `is? ipv4`: value is an IPv4.
- `is? ipv6`: value is an IPv6.

**For boolean properties:**

- `is? true`: synonym of `is equal to true`.
- `is? false`: synonym of `is equal to false`.
- `is? enabled`: synonym of `is equal to true`.
- `is? disabled`: synonym of `is equal to false`.

**For date properties:**

- `is? before :date`: date value is before another date.
- `is? not before :date`: date value is not before another date.
- `is? after :date`: date value is after another date.
- `is? not after :date`: date value is not after another date.