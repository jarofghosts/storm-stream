# storm-stream

[![Build Status](https://img.shields.io/travis/jarofghosts/storm-stream.svg?style=flat-square)](https://travis-ci.org/jarofghosts/storm-stream)
[![npm install](https://img.shields.io/npm/dm/storm-stream.svg?style=flat-square)](https://www.npmjs.org/package/storm-stream)
[![npm version](https://img.shields.io/npm/v/storm-stream.svg?style=flat-square)](https://www.npmjs.org/package/storm-stream)
[![js-standard-style](https://img.shields.io/badge/code%20style-standard-brightgreen.svg?style=flat-square)](https://github.com/feross/standard)
[![License](https://img.shields.io/npm/l/storm-stream.svg?style=flat-square)](https://github.com/jarofghosts/storm-stream/blob/master/LICENSE)

Duplex stream interface to Storm

## example

```javascript
var stormStream = require('storm-stream')

var stream = stormStream()

stream.on('data', function (data) {
  if (data.stream && data.stream === '__heartbeat') {
    // sync on heartbeat
    stream.write({command: 'sync'})
  }
})
```

## api

`stormStream([inputStream], [outputStream]) -> DuplexStream`

* Accepts optional input and output streams, defaulting to stdin and stdout.
* Talks plain JavaScript objects and handles communication with Storm.

## license

MIT
