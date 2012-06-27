Proper access of superclass is `YourClass.super_`.

Never use `this.constructor.super_` instead. This can work for direct child of superclass you're trying to reach, but will fail for any deeper children classes, because `this.constructor` will contain deeper class than you can expect.
