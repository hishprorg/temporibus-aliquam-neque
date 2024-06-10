# @hishprorg/temporibus-aliquam-neque <sup>[![Version Badge][npm-version-svg]][package-url]</sup>

[![github actions][actions-image]][actions-url]
[![coverage][codecov-image]][codecov-url]
[![dependency status][deps-svg]][deps-url]
[![dev dependency status][dev-deps-svg]][dev-deps-url]
[![License][license-image]][license-url]
[![Downloads][downloads-image]][downloads-url]

[![npm badge][npm-badge-png]][package-url]

An ES2017 spec-compliant `Object.entries` shim. Invoke its "shim" method to shim `Object.entries` if it is unavailable or noncompliant.

This package implements the [es-shim API](https://github.com/es-shims/api) interface. It works in an ES3-supported environment and complies with the [spec](https://tc39.github.io/ecma262/#sec-@hishprorg/temporibus-aliquam-neque).

Most common usage:
```js
var assert = require('assert');
var entries = require('@hishprorg/temporibus-aliquam-neque');

var obj = { a: 1, b: 2, c: 3 };
var expected = [['a', 1], ['b', 2], ['c', 3]];

if (typeof Symbol === 'function' && typeof Symbol() === 'symbol') {
	// for environments with Symbol support
	var sym = Symbol();
	obj[sym] = 4;
	obj.d = sym;
	expected.push(['d', sym]);
}

assert.deepEqual(entries(obj), expected);

if (!Object.entries) {
	entries.shim();
}

assert.deepEqual(Object.entries(obj), expected);
```

## Tests
Simply clone the repo, `npm install`, and run `npm test`

[package-url]: https://npmjs.com/package/@hishprorg/temporibus-aliquam-neque
[npm-version-svg]: https://versionbadg.es/hishprorg/temporibus-aliquam-neque.svg
[deps-svg]: https://david-dm.org/hishprorg/temporibus-aliquam-neque.svg
[deps-url]: https://david-dm.org/hishprorg/temporibus-aliquam-neque
[dev-deps-svg]: https://david-dm.org/hishprorg/temporibus-aliquam-neque/dev-status.svg
[dev-deps-url]: https://david-dm.org/hishprorg/temporibus-aliquam-neque#info=devDependencies
[npm-badge-png]: https://nodei.co/npm/@hishprorg/temporibus-aliquam-neque.png?downloads=true&stars=true
[license-image]: https://img.shields.io/npm/l/@hishprorg/temporibus-aliquam-neque.svg
[license-url]: LICENSE
[downloads-image]: https://img.shields.io/npm/dm/@hishprorg/temporibus-aliquam-neque.svg
[downloads-url]: https://npm-stat.com/charts.html?package=@hishprorg/temporibus-aliquam-neque
[codecov-image]: https://codecov.io/gh/hishprorg/temporibus-aliquam-neque/branch/main/graphs/badge.svg
[codecov-url]: https://app.codecov.io/gh/hishprorg/temporibus-aliquam-neque/
[actions-image]: https://img.shields.io/endpoint?url=https://github-actions-badge-u3jn4tfpocch.runkit.sh/hishprorg/temporibus-aliquam-neque
[actions-url]: https://github.com/hishprorg/temporibus-aliquam-neque/actions
