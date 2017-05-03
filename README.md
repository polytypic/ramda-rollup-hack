# Ramda Rollup Hack &middot; [![npm version](https://badge.fury.io/js/ramda-rollup-hack.svg)](http://badge.fury.io/js/ramda-rollup-hack)

This is a quick and dirty hack that converts Ramda in-place to support Rollup
and UglifyJS2 `/*#__PURE__*/` annotations.  This allows one to use Ramda with
Rollup without having to specify named exports by hand and also makes dead code
elimination by UglifyJS2 effective on Ramda.

## Usage

Run `ramda-rollup-hack` after installing Ramda.  For example, you could do it
in the `prepare` script of NPM:

```js
{
  // ...
  "scripts": {
    // ...
    "prepare": "ramda-rollup-hack"
  }
}
```

The `ramda-rollup-hack` scripts modifies the `package.json` file of the Ramda
under `node_modules` to include a `"module"` entry pointing to ES module copies
`*.js -> *-es.js` of Ramda sources created by the script.

The `ramda-rollup-hack` script has been designed to be idempotent so that
running it multiple times against exactly matching Ramda version should not
change anything.
