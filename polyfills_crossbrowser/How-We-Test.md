## Modernizr's Feature detection approach

* Conformance testing (like WebKit layoutTests, Mozilla Mochitests, and W3C Test Suites) test the full range of functionality to make sure the browser handles all edge cases in the spec correctly
* Feature testing will run through behavior (like setting a value into localStorage and reading it out). 
* Feature detection will lightly see if such a feature's API exists (`!!window.localStorage`)

Many browsers get 80-100% coverage on conformance tests. Even robust implementations that most developers are content with may only get 80%. 

**Modernizr aims to write the fastest executable test that satisfies the 90% use case of what a developer wants to use a feature for.**

So if a light sniff of `!!window.localStorage` will give the same result as a run through a conformance test, then we'll use it. (In `localStorage`'s case, it doesn't and [we have much more trickery involved](https://github.com/Modernizr/Modernizr/blob/94a690127904ed7d85679970257e76f3528b4b1c/modernizr.js#L777-802).)

## Testing techniques

[Testling](http://testling.com) is great for writing small tests that you can run on 30 different browsers in under a minute. Here are [some testling feature tests](https://gist.github.com/1431660) we used to explore possible feature detects.

The [Browserstack](//browserstack.com) API is another great technique to try out some feature detects on a wide array of mobile phones. Look at [node-browserstack](https://github.com/scottgonzalez/node-browserstack) for digging into that.


## Browsers we test in

#### primary targets

* IE6 - IE10
* FF ESR, FF stable - FF Nightly
* Chrome stable - Chrome Canary
* Opera stable, Opera Next
* Safari 5.1, Webkit Nightly
* iOS4+
* Android 2.2+, Chrome on Android

#### secondary targets

* Safari 4
* WebOS
* WP7
* BB6
* Opera Mobile
* Kindle Fire

#### incomplete list of browsers that are lucky if they're compatible

* BB pre-6
* Opera Mini