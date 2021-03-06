# stream-array

Pipe an Array through Node.js streams. This is rather useful for testing other
streams.

[![npm version][1]][2] [![build status][3]][4] [![dependencies][5]][6] [![devDependencies][7]][8]

[//]: [![testling][9]][10]


## Usage

```js
var streamify = require('stream-array'),
    os = require('os');

streamify(['1', '2', '3', os.EOL]).pipe(process.stdout);
```


## API

#### streamify(Array)
The result of [require][13] is a 'function' that when invoked, will return a [Readable][11] [Stream][12].

```
var streamify = require('stream-array');
```

The Array passed into stream-array() can contain any type, as it assumes the receiving stream can handle it. Each element will be dequeued and pushed into the following piped stream.

```
var readable = streamify(['Hello', new Buffer('World')]);
```

This [Stream][12] will emit each element of the source array as chunks.

```
readable(['1', '2', '3', os.EOL]).pipe(process.stdout);
```

```
123\n
```

## Install

```
npm install stream-array
```

  [1]: https://badge.fury.io/js/stream-array.svg
  [2]: https://badge.fury.io/js/stream-array
  [3]: https://api.travis-ci.org/mimetnet/node-stream-array.svg
  [4]: https://travis-ci.org/mimetnet/node-stream-array
  [5]: https://david-dm.org/mimetnet/node-stream-array.svg
  [6]: https://david-dm.org/mimetnet/node-stream-array
  [7]: https://david-dm.org/mimetnet/node-stream-array/dev-status.svg?#info=devDependencies
  [8]: https://david-dm.org/mimetnet/node-stream-array/#info=devDependencies
  [//]: https://ci.testling.com/mimetnet/node-stream-array.png
  [//]: https://ci.testling.com/mimetnet/node-stream-array
  [11]: http://nodejs.org/api/stream.html#stream_class_stream_readable
  [12]: http://nodejs.org/api/stream.html#stream_stream
  [13]: http://nodejs.org/api/globals.html#globals_require

## License

[MIT License](https://github.com/mimetnet/node-stream-array/blob/master/LICENSE)
