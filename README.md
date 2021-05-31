## koa-oracledb-middleware
node-oracledb middleware for Koa v2

This is a fork of [https://github.com/viniciusam/koa-oracledb](https://github.com/viniciusam/koa-oracledb). I updated dependencies, and changed a bit.

[![NPM](https://nodei.co/npm/koa-oracledb-middleware.png)](https://nodei.co/npm/koa-oracledb-middleware/)

## Install

    npm install koa-oracledb-middleware --save

## Usage

```
const Koa = require('koa');
const app = new Koa();
const KoaOracle = require('koa-oracledb-middleware');

var db = new KoaOracle({
    user:          process.env.NODE_ORACLEDB_USER,
    password:      process.env.NODE_ORACLEDB_PASSWORD,
    connectString: process.env.NODE_ORACLEDB_CONNECTIONSTRING
});
app.use(db.middleware());
```

or

```
const Router = require('koa-router');
const KoaOracle = require('koa-oracledb-middleware');

var poolV1 = new KoaOracle({
    user:          process.env.NODE_ORACLEDB_USER,
    password:      process.env.NODE_ORACLEDB_PASSWORD,
    connectString: process.env.NODE_ORACLEDB_CONNECTIONSTRING
});
var router = new Router({ prefix: '/v1' });
router.use(poolV1.middleware());
```

## Example
You can find a full example on examples/example.js.

## License

MIT
