# loud-rejection [![Build Status](https://travis-ci.org/sindresorhus/loud-rejection.svg?branch=master)](https://travis-ci.org/sindresorhus/loud-rejection)

> Make unhandled promise rejections fail loudly instead of the default [silent fail](https://gist.github.com/benjamingr/0237932cee84712951a2)

By default, promises fail silently if you don't attach a `.catch()` handler to them.

Use it in top-level things like tests, CLI tools, apps, etc, **but not in reusable modules.**


## Install

```
$ npm install --save loud-rejection
```


## Usage

```js
const loudRejection = require('loud-rejection');
const promiseFn = require('promise-fn');

loudRejection();

promiseFn();
```

Without this module it's more verbose and you might even miss some that will fail silently:

```js
const promiseFn = require('promise-fn');

function error(err) {
	console.error(err.stack);
	process.exit(1);
}

promiseFn().catch(error);
```


## License

MIT © [Sindre Sorhus](http://sindresorhus.com)
