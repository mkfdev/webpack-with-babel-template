## File it!

In order for the team to better fix issues we request that you include the following information that can help us diagnose and fix the problem:

* Confirm it's still an issue with the latest version from [the download page](http://www.modernizr.com/download/).
* Include a link to the exact build you're using. 
* Explain if your issue is browser specific, and which browsers (incl. versions) it affects
* Create a reduced testcase; this helps a huge amount!
  * Use [jsfiddle](http://jsfiddle.net/) or codepen if you want.

We can never have too much detail, so include as much info as you can. Have a look at issue [#501](https://github.com/Modernizr/Modernizr/issues/501) for a great example that ticks all the boxes.

<hr>

## False positive?

A feature test that passes in a browser that _should_ fail is a bad thing for everyone. :( You can help in a few ways.

1. First, file a ticket on modernizr's issue tracker. It'll be tagged as ["false result"](https://github.com/Modernizr/Modernizr/issues?labels=false+result&milestone=&page=1&state=open).
2. [Report the false positive as a bugs to their corresponding browser vendors](http://coding.smashingmagazine.com/2011/09/07/help-the-community-report-browser-bugs/). Many times its a mobile port of WebKit that has a the problem, while it may not exist in other WebKit ports. You can file these at the WebKit tracker regardless.
3. Write a pull request to fix the feature detect. Sometimes the false positive can be worked around (by forcing a reflow, adding the element to the DOM, etc)… as a last result we will add a UA sniff.
4. Add to the .js file some metadata that declares what browsers are false positiving here.

We expect to have an overview page later on with all false positives, for easy reading. More importantly, though, Modernizr will strive to report accurately, even if the browser is returning a false positive for the correct detect.


## Browser bug?

We agree that browser bugs should be detected instead of assumed for given UA strings. This is how `jQuery.support` works. However Modernizr detects features and will not be collecting bugs (like `box-sizing` doesn't work with `min-height` in Firefox). We do recommend you [file the issue with the appropriate vendor](http://coding.smashingmagazine.com/2011/09/07/help-the-community-report-browser-bugs/) and blog about it or post on Stack Overflow to get the word out there with your proposed fix. 


Thanks!