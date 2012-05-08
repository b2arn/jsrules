## How to use require

* Place require lines first (right after "use strict";)
* Use simple requires (see below)
* Use one line per require
* Never use conditional requires
	* instead, require all you may need, then place your conditions
* Place `module.exports = something;` last
* Use simple exports (see below)

### Why?

When require and exports of your module are simple, they can be easily parsed and transformed to some other module system, which can be useful if you want to allow to use your code beyond node.js environment.

### Simple require

```js
var x = require('./x'); // it's simple
var y = require('./z').y; // also simple
```

### Simple exports

```js
module.exports = SomeClass;
```

```js
module.exports = {
	SomeClass: SomeClass,
	SomeOtherClass: SomeOtherClass
};
```
