# Ramda Rollup Hack

This is a quick and dirty hack that converts Ramda in-place to support Rollup
and UglifyJS2 `/*#__PURE__*/` annotations.  This allows one to use Ramda with
Rollup without having to specify named exports by hand and also makes dead code
elimination by UglifyJS2 effective on Ramda.
