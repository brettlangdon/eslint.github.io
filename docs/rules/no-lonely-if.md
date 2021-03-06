---
title: Rule no-lonely-if
layout: doc
---
<!-- Note: No pull requests accepted for this file. See README.md in the root directory for details. -->
# Disallow `if` as the Only Statement in an `else` Block (no-lonely-if)

If an `if` statement is the only statement in the `else` block of a parent `if` statement, it is often clearer to combine the two to using `else if` form.

```js
if (foo) {
    // ...
} else {
    if (bar) {
        // ...
    }
}
```

should be rewritten as

```js
if (foo) {
    // ...
} else if (bar) {
    // ...
}
```

## Rule Details

This rule warns when an `if` statement's `else` block contains only another `if` statement.

The following patterns are considered problems:

```js
/*eslint no-lonely-if: 2*/

if (condition) {
    // ...
} else {
    if (anotherCondition) {
        // ...
    }
}

if (condition) {
    // ...
} else {
    if (anotherCondition) {
        // ...
    } else {
        // ...
    }
}
```

The following patterns are not considered problems:

```js
/*eslint no-lonely-if: 2*/

if (condition) {
    // ...
} else if (anotherCondition) {
    // ...
}

if (condition) {
    // ...
} else if (anotherCondition) {
    // ...
} else {
    // ...
}

if (condition) {
    // ...
} else {
    if (anotherCondition) {
        // ...
    }
    doSomething();
}
```

## When Not To Use It

Disable this rule if the code is clearer without requiring the `else if` form.

## Version

This rule was introduced in ESLint 0.6.0.

## Resources

* [Rule source](https://github.com/eslint/eslint/tree/master/lib/rules/no-lonely-if.js)
* [Documentation source](https://github.com/eslint/eslint/tree/master/docs/rules/no-lonely-if.md)
