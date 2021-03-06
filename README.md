# bundle loader for webpack

## Usage

[Documentation: Using loaders](http://webpack.github.io/docs/using-loaders.html)

``` javascript
// The chunk is requested, when you require the bundle
var waitForChunk = require("bundle!./file.js");

// To wait until the chunk is available (and get the exports)
//  you need to async wait for it.
waitForChunk(function(file) {
	// use file like is was required with
	// var file = require("./file.js");
});
// wraps the require in a require.ensure block
```

The file is requested when you require the bundle loader. If you want it to request it lazy, use:

``` javascript
var load = require("bundle?lazy!./file.js");

// The chunk is not requested until you call the load function
load(function(file) {

});
```

## License

MIT (http://www.opensource.org/licenses/mit-license.php)
