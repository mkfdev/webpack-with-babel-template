In Modernizr 3, we use a new [AMD](https://github.com/amdjs/amdjs-api/wiki/AMD) format for feature detects.

**tl;dr**:

* Wrap it in a `define()`
* Use appropriate dependencies, e.g. `Modernizr`, `testAllProps`, `testStyles`, `createElement`, `docElement`, `is`, etc
* `Modernizr.addTest()` and `Modernizr.addAsyncTest()` should still be called on the `Modernizr` object
* Add it to the correct location inside of `/feature-detects/` and its subfolders.
* Add a metadata block and documentation block
* Add you detect to [config-all.json](https://github.com/Modernizr/Modernizr/blob/master/lib/config-all.json)

[EXAMPLE](/Modernizr/Modernizr/blob/master/feature-detects/a/download.js)

## Structure

* **Metadata block**
* **Documentation block**
* **AMD module declaration**
* **Test declaration**

## Metadata block

This is a parseable comment containing a JSON object of information about the test:

```javascript
/*!
{
  "name": "a[download] Attribute",
  "property": "adownload",
  ...
}
!*/
```

The available fields are:

| Name             | Type             | Description                                                                                                                                                                                                       |
| :--------------: | :--------------: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `aliases`        | array            | Alternative aliases for this test                                                                                                                                                                                 |
| `builderAliases` | array            | Aliases this test may have had in past modernizr.com build URLs                                                                                                                                                   |
| `async`          | Boolean          | Whether or not this test is asynchronous (i.e. uses `Modernizr.addAsyncTest()`)                                                                                                                                   |
| `authors`        | array            | A list of names of contributors to this detect                                                                                                                                                                    |
| `caniuse`        | string           | The equivalent feature name at [caniuse.com](http://caniuse.com)                                                                                                                                                  |
| `doc`            | string           | A relative path to documentation about this feature on the Modernizr website                                                                                                                                      |
| `knownBugs`      | array            | Strings describing known false positives/negatives and any other bugs in this detect                                                                                                                              |
| `name`           | string           | A descriptive name for this test                                                                                                                                                                                  |
| `notes`          | array            | Additional notes about this test; links to external documentation should be defined as objects with `name` and `href` properties (both strings)                                                                   |
| `polyfills`      | string / array   | A list of known polyfills for this feature, as strings mapping to names in `lib/polyfills.json`                                                                                                                   |
| `property`       | string / array   | The Modernizr property defined by this module; this should be an array if the module provides multiple properties (as in [css/hyphens](/Modernizr/Modernizr/blob/master/feature-detects/css/hyphens.js))          |
| `tags`           | array            | A list of keywords associated with this feature                                                                                                                                                                   |
| `warnings`       | array            | Important notes about this test, such as common misuse, unstable features and related browser bugs                                                                                                                |

If you'd like to propose a new metadata field, please submit an [issue](https://github.com/Modernizr/Modernizr/issues).

## Documentation block

This is another parseable comment containing [Markdown](http://daringfireball.net/projects/markdown/) syntax, e.g.:

```javascript
/* DOC

When used on an `<a>`, this attribute signifies that ...

*/
```

This should contain documentation relevant to the user and will be extracted for documentation of this feature detect on the Modernizr website.

Maintainer/implementation documentation (i.e. how it works, why it's implemented how it is, etc) should be inline with the test code as usual.

## AMD module declaration

All executable code in the module should be contained within a [`define()`](https://github.com/amdjs/amdjs-api/wiki/AMD#define-function-) function call, which takes 2 arguments:

* An array of dependencies
* A function defining the module, which takes the dependencies as arguments

```javascript
define(['Modernizr', 'createElement'], function( Modernizr, createElement ) {
  ...
});
```

Our convention is that `Modernizr` should be the first dependency. Other dependencies might be helper functions from the [`src` dir](https://github.com/Modernizr/Modernizr/tree/master/src), or other detects. Asynchronous test *must* have the `addTest` dependency – [see below](#asynchronous-tests).

### Dependencies on other detects

You can make one detect dependent on another to use its result. For example, [canvas/todataurl](/Modernizr/Modernizr/blob/master/feature-detects/canvas/todataurl.js) depends on the basic `canvas` test:

```javascript
define(['Modernizr', 'createElement', 'test/canvas'], function( Modernizr, createElement ) {
  ...
});
```

* Refer to these dependencies by prefixing with `test/`, followed by the path to the detect
    * e.g. to depend on `adownload`, you'd use `'test/a/download'`
* By convention, these should always come after other dependencies
* Detects don't have a return value, so you can omit them from the arguments list of the module
* You can access the result of this dependency within the module via the `Modernizr` object; e.g.:

```javascript
if (!Modernizr.canvas) {
  ...
}
```

## Test declaration

A test declaration either takes the form of a call to `Modernizr.addTest()` or `Modernizr.addAsyncTest()`, for synchronous and asynchronous tests respectively.

This should be the only thing in the direct scope of the `define()` module declaration.

### Synchronous tests

`Modernizr.addTest()` takes 2 arguments:

1. A property name
2. Either:
    * A statement which returns a Boolean value representing the test result
    * A function, which takes no arguments and returns a Boolean value representing the test result

### Asynchronous tests

Please try to avoid writing tests asynchronously if you can help it. They're much better supported in v3, but can still complicate things for end users. That said, sometimes it's the only way to do it.

Async detects *must* have include the `addTest` function in their dependency array. This is *not* the same as `Modernizr.addTest`, but takes the same arguments.

`Modernizr.addAsyncTest()` takes a single argument: a function defining the test procedure. All paths within this function should, at some point, call `addTest`. See [img/webp](/Modernizr/Modernizr/blob/master/feature-detects/img/webp.js) for a good example of this.