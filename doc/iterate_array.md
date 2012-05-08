## Iterate array right way

Don't use `for (var k in arr)` to iterate array.
It works, but array indexes will be converted to string before being put to `k`.
