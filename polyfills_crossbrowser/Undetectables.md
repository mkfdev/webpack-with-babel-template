# The Undetectables

These things cannot be feature detected. They must rely on either:

1. UA sniffing 
2. Browser inferences
3. Providing the same (slow) fix to everyone

## Categories of Undetectables:

### HTML5
* `registerProtocolHandler()` support (exist[[ed|http://code.google.com/p/chromium/issues/detail?id=44984]] in webkit but doesnt do anything, still live in iOS/Android likely.)
* File Drag 'n Drop (webkit doesnt expose a global DataTransfer constuctor to inspect) [[issue 57|https://github.com/Modernizr/Modernizr/issues#issue/57]]
  * I think `Modernizr.draganddrop && window.FileReader` is good enough these days.
* webforms UI: datepicker, colorpicker UIs cannot be detected, only the associated constraint validation
* inability to edit things in contenteditable/designMode in mobile Webkit browsers


### Audio/Video
* `timeupdate` video/audio event fires inconsistently across webkit and moz
* HTML5 video `readyState` is inconsistent across webkit(4) and moz(3) 
* `canPlayType()` results on mobile are unreliable
* `preload` attribute support, can't be tested without bandwidth-consuming tests (Chrome has implemented the preload-IDL, but not the feature)
* `loop` attribute support, can't be tested without bandwidth-consuming tests (support for this attribute is practically non-existent)

### Networking
* `script` tag onload/onerror/onreadystatechange actual behaviour (atomicity, order, etc etc)
* `link` tag / stylesheet onload actual behaviour (exists in webkit / ff but never fires)
* Network related metrics, a la the [[Browserscope Networking |http://www.browserscope.org/?category=network&]] [[Results |http://www.webmastersitesi.com/linux/]](|| script, css, etc)



### Typography / Text
* ClearType disabling during opacity changes
* FOUT behavior of Gecko's @font-face support
* font rendering (like smoothing, anti-aliasing, font-weight diffs among browsers/platforms)
* consistent rendering ( in the page and alert() dialogs) of HTML entities
* proper handling of CSS `text-overflow:ellipsis` behavior on text
* native spellchecking (added in ie10pp3)



### Events
* keyboard event bugs, especially related to the `keydown/keypress` events, and the `keyCode/charCode` event properties.  
  * Best documented and fixed by the [[Google Closure guys |https://github.com/google/closure-library/blob/master/closure/goog/events/keyhandler.js]]
* the order (and reliability) of mousedown, click, and mouseup events (especially if a mousedblclick is happening) 
   * especially when fired on a form element like a checkbox, reliability of state update of the element compared to when the events fire
* whether a scroll wheel event is coming from a continuous device like a trackpad or the Magic Mouse or from a traditional clicking scroll wheel (in webkit).  
  * [`MozMousePixelScroll`](https://developer.mozilla.org/en/Gecko-Specific_DOM_Events#MozMousePixelScroll)
* `onhashchange` is case insensitive in IE8 (maybe 9 too?), all others are case sensitive (HTML5 requires case sensitivity). Can't be detected without actually triggering a hashchange event.
* IE8 in compatibility view mode has `onhashchange`, but doesn't support it.  Workaround is to test for `document.documentMode > 8`.
* support for `DOMContentLoaded`. 
  * You can add an event listener and hope, fall back to `document.readyState` or `window.onload` or in IE, the `doScroll` technique. 
* [the `oninput` event](https://github.com/Modernizr/Modernizr/issues/210).
* WebKit popstate (history API) out-of-synch issues (http://www.bcherry.net/playground/pushstate)
* The `load` event of the `XHR2.upload` fires in different times in different implementations.
Firefox fires it too lately (when the download of the response completed and not when the upload actually ends).
* iOS/Safari bounce scrolling: If the browser can temporarily scroll above to the top of the page (negative `window.pageYOffset || documentElement.scrollTop || body.scrollTop`) or below the bottom of the page.
* The `transitionend` event doesn't fire correctly on some instances of webkit running on iOS, even though the browser has the event definition and handlers. Workaround is setting timeouts when a CSS transition is triggered.
* When using both a touchscreen and mouse at the same time, double-clicking or double-tapping might or might not trigger a `dblclick` event, most notably on Chrome on a MS Surface ([Leaflet/Leaflet#4127](https://github.com/Leaflet/Leaflet/issues/4127)).

### CSS
* `<select>` display in IE6
* PNG alpha transparency
* The look of the various *-resize cursors is very different across browsers and platforms.
* IE6 css bugs like [[duplicate characters bug |http://www.positioniseverything.net/explorer/dup-characters.html]]
* IE display transparency bug on height > 4096px
* Generated content detection is now part of Modernizr core tests see [[L640|https://github.com/Modernizr/Modernizr/blob/master/modernizr.js#L640]]<br /><del>CSS Generated Content support</del>
  * <del>(Updated) Solution: using generated content to alter the width or height of an element ([[Dirty example (updated) |http://jsfiddle.net/z7fTg/7/]]) [example now checks for partial CSS2 support, .e.g, Firefox < 3.5, and CSS3 support]</del>
  * <del>[[modernizr test for gencontent |https://github.com/KrofDrakula/Modernizr/commit/cdb322bdbdc]]</del>
* False positives for `box-shadow`, `border-radius`, etc (happens in Aurora/Midori/etc) [[issue 169 |https://github.com/Modernizr/Modernizr/issues#issue/169]]
* <del>`pointer-events` false positive in Opera</del>
  * [fixed in pull request #386](https://github.com/Modernizr/Modernizr/pull/386)
* `position:fixed` support in iOS and Android
* @rules [prefix inconsistencies](https://github.com/Modernizr/Modernizr/pull/1132#issuecomment-49923209) in IE/Opera requiring browser engine inferences.

### Edge cases
* IE CSS bug where certain types of positioning of an `<input type=text>` element can cause that element's autocomplete box to not render at the same location as the actual input box.
* strange treatment of `<!-- -->` comment nodes in the DOM (in IE)... like in some cases, a comment node will be moved to be a child of the previous element even though it's not a child proper. Can cause things like `:empty` to fail differently.
* resize event firing rate. e.g. you can't keep an element's position smoothly updated in response to resize or scroll.


### General undetectables
* Memory leaks
* DOM/JS performance (e.g.: [[innerHTML vs. DOM manipulation|http://blog.stevenlevithan.com/archives/faster-than-innerhtml]])
  * Testable, but typically not feasible to test just to avoid code forking.
* Hardware Acceleration
  * Whether a CSS transition can use (or did use) [accelerated compositing](https://trac.webkit.org/wiki/QtWebKitGraphics#Acceleratedcompositing). If an effect isn't going to be hardware-accelerated, then a setTimeout animation is often more performant than a non-accelerated CSS transition. No reliable way to measure the framerate of a CSS transition. 

## This might not be a complete list

Add to the list if you know more Undetectables. Likewise, link to possible solutions if you think an item listed here can be feature-detected.

Contributors: paulirish, jaubourg, rwaldron, zachleat, snover, devongovett, rgrove, savetheclocktower, getify, garann, jdalton, michaelbrundage, necolas, mislav, davidcalhoun, ivansanchez