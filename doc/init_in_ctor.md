## Avoid any kind of init() calls in constructor

The problem will arise in subclasses. Common practice for subclass constructors is to call superclass constructor and then perform any additional actions having ready to use superclass instance in `this`.

But having init() call in constructor of superclass, you will have a problem. init() method of subclass may depend on subclass members initialization, so must be called last. But the only way to do it is to place superclass constructor call last as well (because it calls init()). And if you place superclass constructor last, you cannot rely on having ready to use superclass instance in `this`.

Example:

```js
var A = function (a) {
	this.a = this.prepare(a); // members init
	// problem: cannot insert code at this point in subclasses
	this.init(); // final init
};

A.prototype.init = function () {
	// some code depending on this.a
};


var B = function (a) {
	// want to call superclass constructor to have this.a ready
	// but cannot do it because init() will be called before this.b is ready
	// A.call(this, a); // wrong place to call
	this.b = this.a + 5; // want to have superclass members initialized here
	// want to call superclass constructor last to have init() call when this.b is ready
	// but cannot do it, because need this.a to be ready above
	// A.call(this, a); // wrong place to call also
};
inherits(B, A);

B.prototype.init = function () {
	// some code depending on this.a and this.b
};
```

Instead, remove init() call from constructor and rely on calling init() from external code:

```js
var A = function (a) {
	this.a = this.prepare(a);
};

A.prototype.init = function () {
	// some code depending on this.a
};


var B = function (a) {
	A.call(this, a); // always call superclass constructor first
	this.b = this.a + 5; // have superclass members initialized here
};
inherits(B, A);

B.prototype.init = function () {
	// some code depending on this.a and this.b
};

// B usage
var x = new B(7);
x.init();
// use inited x
```

Actually, the case is not specific for constructors only. If you have several initialization steps, there always can be a problem of inserting some additional step between them. So, be careful.
