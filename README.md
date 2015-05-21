# Disallow use of constant expressions (no-constant-expressions)

**This is a working proof of concept. The code is a crazy stream of consciousness.**

Dynamically calculating a constant is likely to be an error.

```js
var success = a === a;
```

This pattern is most likely an error.

## Rule Details

The rule is aimed at preventing the use of a constant expression.

## Examples

The following patterns are considered okay and do not cause warnings:

```js
a === 3;
a === true && b === a;
2 < a && a < 2.1;
```

The following patterns are considered warnings:

```js
a * 0 + 5;
a > 1 && a < 1;
a !== a;
```
