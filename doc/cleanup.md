## Do cleanup

JS has GC, but it doesn't prevent memory leaks completely.
Proper cleanup is especially important with single-page web application and with server-side JS where your code can live for a long time without runtime reloading.

If your object has any references to it, GC will not recycle it. There are some places from which object can be implicitly referenced:

* Event handlers (emitters) - if object listens to some event, handler or emitter has reference to it. Don't forget to stop listening!
* Collections - you could put a reference into some kind of cache or other collection and object will not be recycled before reference will be removed.
	* harmony has [WeakMap](http://wiki.ecmascript.org/doku.php?id=harmony:weak_maps) for such cases
* Any object having kind of service reference to your object that semantically must not prevent your object recycling (but will)
	* harmony will have [weak references](http://wiki.ecmascript.org/doku.php?id=strawman:weak_references) for such cases
