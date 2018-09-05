# Truthy and Falsy

Every value in JavaScript has an inherent `boolean` value. When
that value is evaluated in the context of a boolean expression,
the value will be tranformed into that inherent boolean value.

---

## Falsy
A value is *falsy* if it converts to `false` when evaluated in
a boolean context.

There are 6 *falsy* values in JavaScript:

1. The Boolean value `false`
1. The `null` type
1. The `undefined` type
1. The number `0`
1. The empty string `""`
1. The value `NaN`

---

## Truthy
A value is *truthy* if it converts to `true` when evaluated in
a boolean context.

If a value is not in the *falsy* list, it will be *truthy*.