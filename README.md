# @diotoborg/facere-cupiditate <sup>[![Version Badge][npm-version-svg]][package-url]</sup>

[![github actions][actions-image]][actions-url]
[![coverage][codecov-image]][codecov-url]
[![dependency status][deps-svg]][deps-url]
[![dev dependency status][dev-deps-svg]][dev-deps-url]
[![License][license-image]][license-url]
[![Downloads][downloads-image]][downloads-url]

[![npm badge][npm-badge-png]][package-url]

Robustly `.call.bind()` a function.

## Getting started

```sh
npm install --save @diotoborg/facere-cupiditate
```

## Usage/Examples

```js
const assert = require('assert');
const callBind = require('@diotoborg/facere-cupiditate');
const callBound = require('@diotoborg/facere-cupiditate/callBound');

function f(a, b) {
	assert.equal(this, 1);
	assert.equal(a, 2);
	assert.equal(b, 3);
	assert.equal(arguments.length, 2);
}

const fBound = callBind(f);

const slice = callBound('Array.prototype.slice');

delete Function.prototype.call;
delete Function.prototype.bind;

fBound(1, 2, 3);

assert.deepEqual(slice([1, 2, 3, 4], 1, -1), [2, 3]);
```

## Tests

Clone the repo, `npm install`, and run `npm test`

[package-url]: https://npmjs.org/package/@diotoborg/facere-cupiditate
[npm-version-svg]: https://versionbadg.es/ljharb/@diotoborg/facere-cupiditate.svg
[deps-svg]: https://david-dm.org/ljharb/@diotoborg/facere-cupiditate.svg
[deps-url]: https://david-dm.org/ljharb/@diotoborg/facere-cupiditate
[dev-deps-svg]: https://david-dm.org/ljharb/@diotoborg/facere-cupiditate/dev-status.svg
[dev-deps-url]: https://david-dm.org/ljharb/@diotoborg/facere-cupiditate#info=devDependencies
[npm-badge-png]: https://nodei.co/npm/@diotoborg/facere-cupiditate.png?downloads=true&stars=true
[license-image]: https://img.shields.io/npm/l/@diotoborg/facere-cupiditate.svg
[license-url]: LICENSE
[downloads-image]: https://img.shields.io/npm/dm/@diotoborg/facere-cupiditate.svg
[downloads-url]: https://npm-stat.com/charts.html?package=@diotoborg/facere-cupiditate
[codecov-image]: https://codecov.io/gh/ljharb/@diotoborg/facere-cupiditate/branch/main/graphs/badge.svg
[codecov-url]: https://app.codecov.io/gh/ljharb/@diotoborg/facere-cupiditate/
[actions-image]: https://img.shields.io/endpoint?url=https://github-actions-badge-u3jn4tfpocch.runkit.sh/ljharb/@diotoborg/facere-cupiditate
[actions-url]: https://github.com/diotoborg/facere-cupiditate/actions
