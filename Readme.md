# segmentio-snippet-lite

  Render the analytics.js snippet using ES6 templates, without using handlebars
  of minification

## Why?

  The original [segment.io snippet generator](https://github.com/segmentio/snippet)
  is great, however, it was giving my webpack build chain heartburn. So,
  this version was created.

  It puts the burden of minification on your build chain.

## Example

```js
var snippet = require('snippet');

var contents = snippet.max({
  host: 'cdn.segment.com',
  apiKey: '03fwkuu3',
  page: {
    category: 'Docs',
    name: 'Integrations',
    properties: {
      foo: 'bar'
    }
  }
});
```

## API

### snippet.max(options)

  Returns the maxified version of the analytics.js snippet given a set of `options`:

  * `host`: the domain name where the analytics.js script is hosted
  * `apiKey`: the `apiKey` to load in the snippet
  * `page`: the options to pass to `analytics.page`. if `page` is `false`, then the `page()` call will be omitted

## Requirements

  * Babel ES6
