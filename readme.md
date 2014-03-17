# rocambole-strip-assert [![Build Status](https://travis-ci.org/timopheym/rocambole-strip-assert.png?branch=master)](https://travis-ci.org/timopheym/rocambole-strip-assert)

> Strip assert statements from a [rocambole](https://github.com/millermedeiros/rocambole) AST


## Install

```
npm install --save rocambole-strip-assert
```


## Example

```js
var rocambole = require('rocambole');
var stripconsole = require('rocambole-strip-assert');

rocambole.moonwalk('if (true) { assert(function(){}); }', function (node) {
	stripAssert(node);
}).toString();
//=> if (true) { void 0; }
```

To prevent any side-effects, `assert` is replaced with `void 0` instead of being removed.


## License

MIT © [Sindre Sorhus](http://sindresorhus.com), [Timopheym](timopheym@gmail.com)
