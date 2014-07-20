# resolve-from [![Build Status](https://travis-ci.org/sindresorhus/resolve-from.svg?branch=master)](https://travis-ci.org/sindresorhus/resolve-from)

> Resolve the path of a module like [`require.resolve()`](http://nodejs.org/api/globals.html#globals_require_resolve) but from a given path


## Install

```sh
$ npm install --save resolve-from
```


## Usage

```js
var resolveFrom = require('resolve-from');

// there's a file at `./foo/bar.js`

resolveFrom('foo', './bar');
//=> /Users/sindresorhus/dev/test/foo/bar.js
```


## API

### resolveFrom(fromDir, moduleId)

#### fromDir

*Required*  
Type: `string`

The directory to resolve from.

#### moduleId

*Required*  
Type: `string`

What you would use in `require()`.


## Tip

Create a partial using a bound function if you want to require from the same `fromDir` multiple times:

```js
var resolveFromFoo = resolveFrom.bind(null, 'foo');
resolveFromFoo('./bar');
resolveFromFoo('./baz');
```


## License

MIT © [Sindre Sorhus](http://sindresorhus.com)
