## Useful modules

* [npm](http://npmjs.org/) - package manager (now is a standard for node.js)
* [express](http://expressjs.com/) - web framework
    * [connect](http://www.senchalabs.org/connect/) - http server
* [never](https://github.com/dimsmol/never) - demonizer
* [sockjs](http://sockjs.org) - websockets support
* [async](https://github.com/caolan/async) - asynchronous programming
* [args](https://github.com/dimsmol/args) - command line arguments parser
* [pg](https://github.com/brianc/node-postgres) - PostgreSQL client

### Take a look at

* [cluster](http://nodejs.org/api/cluster.html) (standard module) - multiprocessor running
* [mongodb](https://github.com/mongodb/node-mongodb-native) - mongodb interface

### Be careful with

* [forever](https://github.com/nodejitsu/forever) - has dirty buggy code, replaced with "never"
* [nomnom](https://github.com/harthur/nomnom), [optimist](https://github.com/substack/node-optimist) - bad designed, replaced with "args"
* [socket.io](http://socket.io/) - popular, but buggy and bad designed, replaced with "sockjs"
