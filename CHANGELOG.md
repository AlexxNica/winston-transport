# CHANGELOG

### 2.0.0 (2017/04/11)

- [#2] Final semantics for `winston-transport` base implementations:
  - `TransportStream`: the new `objectMode` Writable stream which should be the base for all future Transports after `winston >= 3`.
  - `LegacyTransportStream`: the backwards compatible wrap to Transports written for `winston < 3`. There isn't all that much different for those implementors except that `log(level, message, meta, callback)` is now `log(info, callback)` where `info` is the object being plumbed along the objectMode pipe-chain. This was absolutely critical to not "break the ecosystem" and give [the over 500 Transport package authors](https://www.npmjs.com/search?q=winston) an upgrade path.
  - Along with all the code coverage & `WritableStream` goodies:
    - 100% code coverage for `TransportStream`
    - 100% code coverage for `LegacyTransportStream`
    - Implementation of `_writev` for  `TransportStream`
    - Implementation of `_writev` for  `LegacyTransportStream`

### 1.0.2 (2015/11/30)

- Pass the write stream callback so that we can communicate backpressure up the chain of streams.

### 1.0.1 (2015/11/22)

- First `require`-able version.

### 1.0.0 (2015/11/22)

- Initial version.

[#2]: https://github.com/winstonjs/winston-transport/pull/2
