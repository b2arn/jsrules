# Rules for JS

* Follow [Google Code Style Guide](http://google-styleguide.googlecode.com/svn/trunk/javascriptguide.xml)
* Use [MDN](https://developer.mozilla.org/en/JavaScript/Guide) documentation
* Use [jswiki](https://github.com/bebraw/jswiki/wiki) as guide to JS libraries
* Use `"use strict";` everywhere
* Make [custom errors](https://github.com/dimsmol/nerr) right
* [Introduce library](doc/libraries.md) whenever it's possible
* Use right [blocks style](doc/block_style.md)
* [Avoid](doc/init_in_ctor.md) any kind of `init()` calls in constructor
* Remove listeners and do [further cleanup](doc/cleanup.md)
* Don't use `for (var k in arr)` for [iterating arrays](doc/iterate_array.md)
* Use [polyfills](https://github.com/Modernizr/Modernizr/wiki/HTML5-Cross-browser-Polyfills), but with care
* `catch(err)` doesn't need `var err;`
* Use `err` (not `error` or `exc`) for error variables
* Know about [harmony](http://wiki.ecmascript.org/doku.php?id=harmony:proposals) - it is already partially available in browsers and node
* Use Object.defineProperty() when available (not `__defineGetter__`/`__defineSetter__`)

## node.js

* Use [project template](https://github.com/dimsmol/nprj) (you can download it as an [archive](nprj.tgz))
* Properly use [require and exports](doc/node/require_exports.md) in your modules
* Use [async](https://github.com/caolan/async)
* And other useful [modules](doc/node/modules.md)
* Use `path.join()`
* Don't write "for node.js" in package.json description
* **Do** write "for node.js" in description on github
* You can use [harmony in node](http://www.goatslacker.com/post/16000243520/how-to-obtain-harmony-in-your-node-js) (partially for now)
