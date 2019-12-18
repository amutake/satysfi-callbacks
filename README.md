satysfi-pubsub
==============

[![Build Status](https://github.com/amutake/satysfi-pubsub/workflows/build/badge.svg)](https://github.com/amutake/satysfi-pubsub/actions?query=workflow%3Abuild)

A simple Pub/Sub library for SATySFi.

Example
-------

```
$ cat test.saty
@import: ./pubsub
@require: standalone

let topic = PubSub.make () in
let () = PubSub.subscribe display-message topic in
let () = PubSub.publish `foo` topic in
let () = PubSub.subscribe display-message topic in
let () = PubSub.publish `bar` topic in

standalone '<>
$ docker run --rm -it -v $(pwd):/satysfi amutake/satysfi:nightly satysfi test.saty
...
foo
bar
bar
...
```

For more complex example, see [example](./example) directory.
