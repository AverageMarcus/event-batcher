# event-batcher

demo: http://benjaminbenben.com/event-batcher/examples/mouse.html

This gathers events and broadcasts them in batches with relative timestamps, allowing them to be unpacked and replayed in a smooth way.

```js

var encode = eventBatcher.encode(100)
var decode = eventBatcher.decode()

// handle a batch of events
encode.handle(b => {
  // this will only get called every 100ms
  // this is where you might trigger an
  // event with pusher
  decode(batch)
})


addEventListener('mousemove', e => encode(e.clientX) )

decode.handle( x => console.log(x) )

```
