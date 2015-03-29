# storm-stream

[![Build Status](http://img.shields.io/travis/jarofghosts/storm-stream.svg?style=flat)](https://travis-ci.org/jarofghosts/storm-stream)
[![npm install](http://img.shields.io/npm/dm/storm-stream.svg?style=flat)](https://www.npmjs.org/package/storm-stream)

Duplex stream interface to Storm

## example

```javascript
var stormStream = require('storm-stream')

var stream = stormStream()

stream.on('data', function(data) {
  if(data.stream && data.stream === '__heartbeat') {
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
