*This repository is a mirror of the [component](http://component.io) module [component/array-series](http://github.com/component/array-series). It has been modified to work with NPM+Browserify. You can install it using the command `npm install npmcomponent/component-array-series`. Please do not open issues or send pull requests against this repo. If you have issues with this repo, report it to [npmcomponent](https://github.com/airportyh/npmcomponent).*
# Array Series [![Build Status](https://travis-ci.org/component/array-series.png)](https://travis-ci.org/component/array-series)

Call an array of asynchronous functions in series

### API

#### series(fns[, context[, callback]])

```js
var series = require('array-series')

series([
  function (done) {
    done()
  }
], this, function (err) {

})
```

#### fns

`fns` is an array of functions to call in series.
The argument signature should be:

```js
function (done) {
  done(new Error())
  // or
  done()
}
```

That is, each function should only take a `done` as an argument.
Each callback should only take an optional `Error` as an argument.

#### context

Optional context to pass to each `fn`.
Basically `fn.call(context, done)`.

#### callback(err)

```js
function (err) {

}
```

Only argument is an `Error` argument.
It will return the first error in the series of functions that returns an error,
and no function after will be called.

### License

The MIT License (MIT)

Copyright (c) 2013 Jonathan Ong me@jongleberry.com

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in
all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
THE SOFTWARE.