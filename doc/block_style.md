## Block style

Use following:

```js
var f = function (a) {
	if (a) {
		// do something
	}
	else {
		// do something else
	}

	try {
		// try it
	}
	catch (err) {
		// catched
	}
};
```

### Why?

It's cleaner than one of common practices and more compact than another.

Common practice example:

```js
if (a) {
	// do something
} else {
	// do something else
}
```

Here "else" is shifted and it's hard to locate it in code, that makes it less readable.

Another common practice example:

```js
if (a)
{
	// do something
}
else
{
	// do something else
}
```

It has bad readability due to verboseness.
