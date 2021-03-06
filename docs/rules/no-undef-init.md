---
title: Rule no-undef-init
layout: doc
---
<!-- Note: No pull requests accepted for this file. See README.md in the root directory for details. -->
# Disallow Initializing to undefined (no-undef-init)

In JavaScript, a variable that is declared and not initialized to any value automatically gets the value of `undefined`. For example:

```js
var foo;

console.log(foo === undefined);     // true
```

It's therefore unnecessary to initialize a variable to `undefined`, such as:

```js
var foo = undefined;
```

It's considered a best practice to avoid initializing variables to `undefined`.


## Rule Details

This rule aims to eliminate variable declarations that initialize to `undefined`.

The following patterns are considered problems:

```js
/*eslint no-undef-init: 2*/
/*eslint-env es6*/

var foo = undefined;
let bar = undefined;
```

The following patterns are not considered problems:

```js
/*eslint no-undef-init: 2*/
/*eslint-env es6*/

var foo;
let bar;
const baz = undefined;
```

## When Not To Use It

There is one situation where initializing to `undefined` behaves differently than omitting the initialization, and that's when a `var` declaration occurs inside of a loop. For example:

```js
for (i = 0; i < 10; i++) {
    var x = undefined;
    console.log(x);
    x = i;
}
```

In this case, the `var x` is hoisted out of the loop, effectively creating:

```js
var x;

for (i = 0; i < 10; i++) {
    x = undefined;
    console.log(x);
    x = i;
}
```

If you were to remove the initialization, then the behavior of the loop changes:

```js
for (i = 0; i < 10; i++) {
    var x;
    console.log(x);
    x = i;
}
```

This code is equivalent to:

```js
var x;

for (i = 0; i < 10; i++) {
    console.log(x);
    x = i;
}
```

This produces a different outcome than defining `var x = undefined` in the loop, as `x` is no longer reset to `undefined` each time through the loop.

If you're using such an initialization inside of a loop, then you should disable this rule.

## Related Rules

* [no-undefined](no-undefined)
* [no-void](no-void)

## Version

This rule was introduced in ESLint 0.0.6.

## Resources

* [Rule source](https://github.com/eslint/eslint/tree/master/lib/rules/no-undef-init.js)
* [Documentation source](https://github.com/eslint/eslint/tree/master/docs/rules/no-undef-init.md)
