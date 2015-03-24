# async-request

[![NPM version](http://img.shields.io/npm/v/async-request.svg?style=flat)](https://www.npmjs.org/package/async-request)
[![Travis build status](http://img.shields.io/travis/gajus/async-request/master.svg?style=flat)](https://travis-ci.org/gajus/async-request)
[![Dependency Status](https://david-dm.org/gajus/async-request.svg?style=flat)](https://david-dm.org/gajus/async-request)

async-request is a wrapper for [request](https://www.npmjs.com/package/request) that uses [ES7 async functions](https://github.com/lukehoban/ecmascript-asyncawait).

## Usage

```js
let request = require('async-request'),
    response;

try {
    response = await request('http://gajus.com/');

    // response.statusCode
    // response.headers
    // response.body

    await request({
        url: 'http://gajus.com',
        method: 'POST',
        data: {
            foo: 'bar'
        },
        headers: {
            foo: 'bar'
        }
    });
} catch (e) {

}
```

## Debugging

`async-request` does not provide (expose) inbuilt debugging capabilities. Use a proxy (e.g. https://mitmproxy.org/) to intercept and analyze HTTP traffic.

## API

* Make sure API is based on https://fetch.spec.whatwg.org/ standard.

## Running

Async function behavior has been accepted into stage 1 ("Proposal") of the ECMASCript 7 spec process in January 2014. This means that it cannot be used out of the box with node.js or iojs without a transpiler.

This library is using [Babel](https://babeljs.io/) to compile ES7 code into ES5. Refer to the [./gulpfile.js](./gulpfile.js).

## Beware

This library has been created as part of [ES7 async function](https://github.com/lukehoban/ecmascript-asyncawait) proposal research. It covers basic use of [request](https://www.npmjs.com/package/request). I do not advise to use it in production, though I will be testing it in several private projects and update as I go – contributions are welcome too.
