---
title: Rule no-param-reassign
layout: doc
---
<!-- Note: No pull requests accepted for this file. See README.md in the root directory for details. -->
# Disallow Reassignment of Function Parameters (no-param-reassign)

Assignment to variables declared as function parameters can be misleading and lead to confusing behavior, as modifying function parameters will also mutate the `arguments` object. Often, assignment to function parameters is unintended and indicative of a mistake or programmer error.

## Rule Details

This rule aims to prevent unintended behavior caused by overwriting function parameters.

## Options

This rule takes one option, an object, with a property `"props"`.

```json
{
    "no-param-reassign": [2, {"props": false}]
}
```

### `props`

It is `false` by default. If it is `true` is set, this rule warns modifying of properties of parameters.

The following patterns are considered problems:

```js
/*eslint no-param-reassign: 2*/

function foo(bar) {
    bar = 13;
}

function foo(bar) {
    bar++;
}
```

When `{"props": true}`:

```js
/*eslint no-param-reassign: [2, { "props": true }]*/

function foo(bar) {
    bar.prop = "value";
}

function foo(bar) {
    delete bar.aaa;
}

function foo(bar) {
    bar.aaa++;
}
```

The following patterns are not considered problems:

```js
/*eslint no-param-reassign: 2*/

function foo(a) {
    var b = a;
}
```

When `{"props": false}`:

```js
/*eslint no-param-reassign: [2, { "props": false }]*/

function foo(bar) {
    bar.prop = "value";
}

function foo(bar) {
    delete bar.aaa;
}

function foo(bar) {
    bar.aaa++;
}
```

## When Not To Use It

If you want to allow assignment to function parameters, then you can safely disable this rule.

## Further Reading

* [JavaScript: Don’t Reassign Your Function Arguments](http://spin.atomicobject.com/2011/04/10/javascript-don-t-reassign-your-function-arguments/)

## Version

This rule was introduced in ESLint 0.18.0.

## Resources

* [Rule source](https://github.com/eslint/eslint/tree/master/lib/rules/no-param-reassign.js)
* [Documentation source](https://github.com/eslint/eslint/tree/master/docs/rules/no-param-reassign.md)
