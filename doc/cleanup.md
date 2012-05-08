## Do cleanup

JS has GC, but it doesn't prevent memory leaks completely.
This is especially important with single-page web application and server-side js.

If your object has any links to it, GC will not recycle it. There are some places from which object can be implicitly referenced:

* Event emitters - if you subscribed to some event, emitter has reference to your object. Don't forget to unsubscribe!
* Collections - you could put a reference into some kind of cache or other collection and object will not be recycled before reference will be removed.
	* harmony has [WeakMap](http://wiki.ecmascript.org/doku.php?id=harmony:weak_maps) for such a cases
* Any other object with references to your object that semantically must not prevent your object recycling (but will)
	* harmony will have [weak references](http://wiki.ecmascript.org/doku.php?id=strawman:weak_references) for such a cases
