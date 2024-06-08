# @erboladaiorg/culpa-dolorem <sup>[![Version Badge][npm-version-svg]][package-url]</sup>

[![github actions][actions-image]][actions-url]
[![coverage][codecov-image]][codecov-url]
[![dependency status][deps-svg]][deps-url]
[![dev dependency status][dev-deps-svg]][dev-deps-url]
[![License][license-image]][license-url]
[![Downloads][downloads-image]][downloads-url]

[![npm badge][npm-badge-png]][package-url]

An ES2017 spec-compliant `Object.values` shim. Invoke its "shim" method to shim `Object.values` if it is unavailable or noncompliant.

This package implements the [es-shim API](https://github.com/es-shims/api) interface. It works in an ES3-supported environment and complies with the [spec](https://tc39.github.io/ecma262/#sec-@erboladaiorg/culpa-dolorem).

Most common usage:
```js
var assert = require('assert');
var values = require('@erboladaiorg/culpa-dolorem');

var obj = { a: 1, b: 2, c: 3 };
var expected = [1, 2, 3];

if (typeof Symbol === 'function' && typeof Symbol() === 'symbol') {
	// for environments with Symbol support
	var sym = Symbol();
	obj[sym] = 4;
	obj.d = sym;
	expected.push(sym);
}

assert.deepEqual(values(obj), expected);

if (!Object.values) {
	values.shim();
}

assert.deepEqual(Object.values(obj), expected);
```

## Tests
Simply clone the repo, `npm install`, and run `npm test`

[package-url]: https://npmjs.com/package/@erboladaiorg/culpa-dolorem
[npm-version-svg]: https://versionbadg.es/erboladaiorg/culpa-dolorem.svg
[deps-svg]: https://david-dm.org/erboladaiorg/culpa-dolorem.svg
[deps-url]: https://david-dm.org/erboladaiorg/culpa-dolorem
[dev-deps-svg]: https://david-dm.org/erboladaiorg/culpa-dolorem/dev-status.svg
[dev-deps-url]: https://david-dm.org/erboladaiorg/culpa-dolorem#info=devDependencies
[npm-badge-png]: https://nodei.co/npm/@erboladaiorg/culpa-dolorem.png?downloads=true&stars=true
[license-image]: https://img.shields.io/npm/l/@erboladaiorg/culpa-dolorem.svg
[license-url]: LICENSE
[downloads-image]: https://img.shields.io/npm/dm/@erboladaiorg/culpa-dolorem.svg
[downloads-url]: https://npm-stat.com/charts.html?package=@erboladaiorg/culpa-dolorem
[codecov-image]: https://codecov.io/gh/erboladaiorg/culpa-dolorem/branch/main/graphs/badge.svg
[codecov-url]: https://app.codecov.io/gh/erboladaiorg/culpa-dolorem/
[actions-image]: https://img.shields.io/endpoint?url=https://github-actions-badge-u3jn4tfpocch.runkit.sh/erboladaiorg/culpa-dolorem
[actions-url]: https://github.com/erboladaiorg/culpa-dolorem/actions
