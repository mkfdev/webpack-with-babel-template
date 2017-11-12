> The No-Nonsense Guide to HTML5 Fallbacks

So here we're collecting all the shims, fallbacks, and polyfills in order to implant HTML5 functionality in browsers that don't natively support them.

The general idea is that: We, as developers, should be able to develop with the HTML5 APIs, and scripts can create the methods and objects that should exist. Developing in this future-proof way means as users upgrade, your code doesn't have to change but users will move to the better, native experience cleanly.

---

- **Looking to conditionally load these scripts (client-side), based on feature detects?**  
  See [**Modernizr**](https://modernizr.com).

- **Looking for a guide to write your own polyfills?**  
  See [**Writing Cross-Browser JavaScript Polyfills**](http://addyosmani.com/blog/writing-polyfills/).

- **Looking for an alphabetical guide on HTML5, CSS3, etc. features, and how to use them?**  
  See [**HTML5PLEASE**](http://html5please.com).

- **Looking for a polyfill combinator?**  
  See [**Polyfiller**](https://github.com/Polyfiller/polyfiller).

---



## SVG

- **[svgweb](http://code.google.com/p/svgweb/)** by Brad Neuberg & others
  - Fallback via Flash
- **[Snap.SVG](http://snapsvg.io/)** from scratch by the author of Raphaël (Dmitry Baranovskiy)
  - Abstracted API. Adds features. Fallback for IE via VML.
- **[Ample SDK](http://www.amplesdk.com/examples/svg/)** by Sergey Ilinsky
- **[canvg](http://code.google.com/p/canvg/)** by Gabe Lerner
  - Writes SVG to `canvas`. Good for Android
- **[SVG Boilerplate](https://github.com/darobin/svgboilerplate)**
  - (alpha; still buggy) Handle multiple concurrent SVG shims together
- **[SIE SVG library](http://sie.sourceforge.jp/)** by dhrname
  - Fallback to VML for old IE
- **[dojo gfx](http://docs.dojocampus.org/dojox/gfx/)** by Eugene Lazutkin, Kun Xi, Chris Mitchell
  - Fallback via VML, Canvas, Silverlight and Flash
- **[fabric.js](http://github.com/kangax/fabric.js)** by kangax
  - Render SVG via `canvas`

#### SVG SMIL

- **[FakeSmile](http://leunen.me/fakesmile/)** by David Leunen



## Canvas

- **[FlashCanvas](http://flashcanvas.net/)** by Shinya Muramatsu
  - Reported to have [33x better performance](https://github.com/paulirish/lazyweb-requests/issues#issue/21) than excanvas
- **[excanvas](http://code.google.com/p/explorercanvas/)** by Google, Erik Arvidsson
- **[slcanvas project](http://slcanvas.codeplex.com)** ([Original Silverlight bridge](http://blogs.msdn.com/b/delay/archive/2009/08/24/using-one-platform-to-build-another-html-5-s-canvas-tag-implemented-using-silverlight.aspx))
- **[canvas-text](http://code.google.com/p/canvas-text/)**
  - Only necessary for canvastext in IE, really
- **[fxCanvas](http://burzak.com/proj/fxcanvas/)**
- **[Kinetic.js](http://kineticjs.com)** by Eric Drowell



## Web Storage (`LocalStorage` and `SessionStorage`)

- **[mortzdk/localStorage](https://github.com/mortzdk/localStorage)** by Morten Houmøller Nygaard
- **[inexorabletash polyfill](https://github.com/inexorabletash/polyfill/blob/master/obsolete/storage.js)** by Joshua Bell
  - based on Remy Sharp's gist
- **[cookie-based polyfill](http://gist.github.com/350433)** by Remy Sharp
- **[In-memory stub polyfill](https://gist.github.com/juliocesar/926500)** by Julio Cesar Ody
- **[`sessionStorage`](http://code.google.com/p/sessionstorage/)** by Andrea Giammarchi
- **[Amplify.js](http://amplifyjs.com)** by appendTo
- **[textStorage.js](https://gist.github.com/1221115)** by sofish
  - Using `localStorage` API, Fallback for IE6+

#### Non HTML5 API Solutions

- **[ssw](http://github.com/molily/javascript-client-side-session-storage)** by Matthias Schäfer
- **[`$.store`](https://github.com/medialize/jQuery-store)** by Rodney Rehm
- **[lawnchair](https://github.com/brianleroux/lawnchair)** by Brian Leroux
- **[store.js](https://github.com/marcuswestin/store.js)** by Marcus Westin
- **[PersistJS](http://pablotron.org/?cid=1557)** by Paul Duncan
- **[Squirrel.js](https://github.com/easy-designs/Squirrel.js)** by Aaron Gustafson
- **[jStorage](https://github.com/andris9/jStorage)** by Andris Reinman



## Sectioning Elements

- **[html5shiv](http://github.com/afarkas/html5shiv)** by afarkas, Jon Neal & community
  - Enables for print use, as well
- **[~~innerShiv~~](http://jdbartlett.github.com/innershiv)** by Joe Bartlett
  - ~~Enables elements for `innerHTML` use~~
  - **Deprecated:** replaced by html5shiv



## Video

- **[html5media](http://github.com/etianen/html5media)**
  - Uses Flowplayer SWF for fallback.
- **[mediaelement.js](http://mediaelementjs.com)** by John Dyer
  - SWF player that mimics HTML5 media API. Consistent UI across browsers and flash. `<track>` support.
- **[video.js](http://videojs.com)** by Zencoder
  - Device fixes. `<track>` support
- **[LeanBack Player - HTML5 audio/video media player](http://www.leanbackplayer.com)**
  - HTML5 audio/video media player UI, easy to integrate and independent of other JS libraries.
- **[video for everybody](http://web.archive.org/web/20101205155004/http://camendesign.com/code/video_for_everybody)** by Kroc Camen ([original](http://camendesign.com/code/video_for_everybody))
  - The granddaddy of `<video>` fallbacks. Markup-based solution; works _without_ Javascript! A must read.

#### VTT: Video Timed Track (subtitles)

- **[videosub](http://www.storiesinflight.com/js_videosub/)**
- **[JSCaptions](https://bitbucket.org/tagawa/jscaptions)** by Daniel Davis
- **[Captionator](https://github.com/cgiffard/Captionator)** by Christopher Giffard
  - Supports WHATWG TextTrack spec & has experimental support for MediaTracks/synchronised media elements
- **[playr](http://www.delphiki.com/html5/playr/)** by Julien Villetorte
  - Support both WebVTT & SubRip files



## Audio

- **[SoundJS](http://www.createjs.com/#!/SoundJS)**
  - SoundJS provides a simple API and powerful features that abstract away the difficulties in varied browser audio support. Optional flash fallback for older browser support. Extensive documentation and active community.
- **[audioJS](http://github.com/EvandroLG/audioJS)**
  - AudioJS is a agnostic and cross-browser lib to work easily with the AudioContext API of HTML5.
- **[jPlayer](http://github.com/happyworm/jPlayer)**
  - custom `<audio>` player with jQuery dependency, flash fallback
- **[audio.js](http://kolber.github.com/audiojs)** by ab+c
  - custom `<audio>` player, flash fallback
- **[SoundManager2](http://www.schillmania.com/projects/soundmanager2)**
  - custom `<audio>` player, flash fallback, API, extensive documentation
- **[LeanBack Player - HTML5 audio/video media player](http://www.leanbackplayer.com)**
  - HTML5 audio/video media player UI, easy to integrate and independent of other JS libraries.

#### Audio Data API

- **[WAAPISim](https://github.com/g200kg/WAAPISim)** by g200kg
  - Uses Audio Data API in Firefox. Falls back to Flash in Opera, IE.
- **[XAudioJS](https://github.com/grantgalitz/XAudioJS)** by Grant Galitz
  - Audio sample stream output thin-abstraction library that supports mono and stereo audio, as well as resampling the audio stream.
  - Supports the Mozilla Audio Data API, Web Audio API, Adobe Flash 10, real-time WAV PCM Data URI generation
- **[dynamicaudio.js](http://github.com/bfirsh/dynamicaudio.js)** by Ben Firshman
- **[audiolib.js](https://github.com/jussi-kalliokoski/audiolib.js)** by Jussi Kalliokoski
  - specs: [incubator group proposed spec](http://chromium.googlecode.com/svn/trunk/samples/audio/specification/specification.html), [Mozilla Audio Data API (temporary)](https://wiki.mozilla.org/Audio_Data_API)



## IndexedDB

- **[IndexedDB Polyfill](http://nparashuram.com/IndexedDBShim) by [Parashuram](http://nparashuram.com)**
  - Polyfill for IndexedDB on WebSql
  - Tested on IndexedDB libraries like [PouchDB](http://pouchdb.com), [JqueryIndexedDB Plugin](http://nparashuram.com/jquery-indexeddb/), [Linq2IndexedDB](http://linq2indexeddb.codeplex.com) and [DBJS](http://aaronpowell.github.com/db.js/)
- **[localForage](https://github.com/mozilla/localForage)** by Mozilla
- **[idb-iegap](https://github.com/dfahlander/idb-iegap)** by [David Fahlander](https://github.com/dfahlander)
  - Makes IE10 and IE11 support the full indexedDB standard, as Chrome, Opera and Firefox does.



## Web SQL Database

- **[clientdb.js](http://bitbucket.org/malde/bespin-malde/src/16664c5e59e4/frontend/js/db/clientdb.js)** _Requires gears._ _Non-HTML5 API_
- **[webstorageportabilitylayer](http://code.google.com/p/webstorageportabilitylayer/)** _Requires gears._ _Non-HTML5 API_
- **[SQLjs](http://code.google.com/p/sqljs/)** _Requires gears._ _Non-HTML5 API_
- **[DomSQL](http://code.google.com/p/dom-storage-query-language/)** _Non-HTML5 API_
- **[localForage](https://github.com/mozilla/localForage)** by Mozilla

#### Local Database Abstractions (non-HTML5 APIs, but useful)

- **[localStorageDB](https://github.com/knadh/localStorageDB)** _Non-HTML5 API_
- **[LocalStorageDB.js](https://github.com/easy-designs/LocalStorageDB.js)** _Non-HTML5 API_
- **[db.js](https://github.com/WebReflection/db#asyncstorage--a-developer-friendly-asynchronous-storage)** by Andrea Giammarchi _Non-HTML5 API_



## Web Forms

- **[Webshims Lib](http://afarkas.github.io/webshim/demos/)** by Alexander Farkas
  - Several Polyfills including Constraint Validation and several input-widgets
- **[H5F](http://github.com/ryanseddon/H5F)** by Ryan Seddon
- **[webforms2](https://github.com/westonruter/webforms2)** by Weston Ruter
- **[nwx forms](https://github.com/dperini/nwxforms)** ([demo](http://dl.dropbox.com/u/598365/html5forms/html5forms.html)) by Diego Perini
- **[HTML5 Form Shim](https://github.com/dsheiko/HTML5-Form-Shim)** by Dmitry Sheiko
- **[jQuery form shim](http://adodson.com/jquery.form.js/)** ([GitHub](https://github.com/MrSwitch/jquery.form.js)) by Andrew Dodson
- **[html5widgets](http://www.useragentman.com/blog/2010/07/27/cross-browser-html5-forms-using-modernizr-webforms2-and-html5widgets/)** by Zoltan Hawryluk
  - uses **webforms2** a few other battle-tested scripts for datepicker and colorpicker.
- **[gallery-html5-forms YUI3 gallery module](http://yuilibrary.com/gallery/show/html5-forms)** by Matt Snider
  - HTML5-enable forms for legacy browsers; requires YUI3; doesn't include `type=number` or `type=range`
- **[selectedOptions multiple `<select>` shim](https://gist.github.com/4212217)** by Brett Zamir
- **[`oninput` event shim](http://benalpert.com/2013/06/18/a-near-perfect-oninput-shim-for-ie-8-and-9.html)** by Ben Alpert
- **[`form` attribute polyfill](http://stackoverflow.com/a/26696165/214325)** by ChiChou
- **[FormData](https://github.com/jimmywarting/FormData)** by Jimmy Wärting

#### Web Forms: individual input types

- **[jscolor](https://github.com/jo/JSColor)** Polyfill version of [jscolor by Jan Odvárko](https://github.com/odvarko/JSColor). by Johannes J. Schmidt
- **[nodep-date-input-polyfill](https://www.npmjs.com/package/nodep-date-input-polyfill)** by Brian Blakely
- **[better-dateinput-polyfill](https://github.com/chemerisuk/better-dateinput-polyfill)** by Maksim Chemerisuk
- **[better-timeinput-polyfill](https://github.com/chemerisuk/better-timeinput-polyfill)** by Maksim Chemerisuk
- **[Accessible and unobtrusive slider / `<input type=range>` polyfill](http://github.com/freqdec/fd-slider)** by Brian McAllister
- **[rangeslider.js](http://andreruffert.github.io/rangeslider.js/)** by André Ruffert
  - simple, small and fast JavaScript/jQuery polyfill for the HTML5 `<input type="range"`> slider element (not accessible)
- **[`<input type=range>` shim for Firefox](https://github.com/fryn/html5slider)** by Frank Yan
- **[`<input type=number>` shim](https://github.com/jonstipe/number-polyfill)** by jonstipe

#### Web Forms: validation

- **[better-form-validation](https://github.com/chemerisuk/better-form-validation/)** by Maksim Chemerisuk
- **[jquery.html5form](http://www.matiasmancini.com.ar/jquery-plugin-ajax-form-validation-html5.html)** by Matias Mancini
- **[HyperForm](https://github.com/hyperform/hyperform/)**

#### Web Forms: `<input placeholder="…">`

- **[Placeholder](https://github.com/UmbraEngineering/Placeholder)** by James Brumond
  - multiple different placeholder implementations for different use cases
- **[Placeholder jQuery plugin](http://github.com/mathiasbynens/jquery-placeholder)** by Mathias Bynens
- **[Placeholder Enhanced](https://github.com/dciccale/placeholder-enhanced)** by Denis Ciccale
- **[jquery-placeholder](https://github.com/diy/jquery-placeholder)** by Brian Reavis
  - doesn't set `input`'s value
- **[jquery.HTML5Support](https://github.com/amiel/html5support)** by Amiel Martin
  - supports `placeholder` and `autofocus`
- **[jquery.placeholder.js](https://github.com/serby/jquery.placeholder.js)** by Paul Serby
- **[Placeholders.js - An HTML5 placeholder attribute polyfill](https://github.com/jamesallardice/Placeholders.js)** by James Allardice
  - non-jQuery, works in IE6+, and also now allows for placeholders that don't disappear on focus
- **[placeholder-augment](https://github.com/jethrolarson/placeholder-augment)** by Jethro Larson
  - jQuery, IE6, iPhone, android, etc. Placeholders don't disappear on focus.
- **[better-placeholder-polyfill](https://github.com/chemerisuk/better-placeholder-polyfill)** by Maksim Chemerisuk
  - doesn't require initialization for a dynamic content
- **[Placeholdr](https://github.com/vote539/placeholdr/blob/master/placeholdr.js)** by Shane Carr
  - under 1KB, drop-in functionality, extends jQuery `$.fn.val`, empties `placeholder` text on form submit
- **[HTML5 placeholder polyfill](https://github.com/ginader/HTML5-placeholder-polyfill)** by Dirk Ginader
  - jQuery powered with a focus on accessibility

#### `<datalist>`

- **[Minimal and library dependency-free vanilla JavaScript polypill](https://github.com/mfranzke/datalist-polypill)** by Maximilian Franzke
- **[Relevant Dropdowns](https://css-tricks.com/relevant-dropdowns-polyfill-for-datalist/)** by Chris Coyier
- **[`datalist` fallback](http://adactio.com/journal/4272/)** by adactio.
  - Not a polyfill, but it's done with <abbr title="Progressive Enhancement">PE</abbr>.
- **[Webshims Lib](http://afarkas.github.io/webshim/demos/)** by Alexander Farkas
  - has support for `datalist` element (includes `input[list]`, `input[selectedOption]`, `datalist[options]`)



## Accessibility / ARIA

- **[accessifyhtml5.js](https://github.com/yatil/accessifyhtml5.js)**



## Web Sockets

- **[SockJS](https://github.com/sockjs/sockjs-client)** by Marek Majkowski
- **[socket.io](http://socket.io/)** by Guillermo Rauch
  - Abstracts API and adds features
- **[kaazing websocket gateway](http://kaazing.com/products/kaazing-websocket-gateway.html)**
  - Commercial product. Pure polyfill.
- **[web-socket-js](http://github.com/gimite/web-socket-js/)**
  - Supports CORS fallback
- **[atmosphere jQuery plugin](http://jfarcand.wordpress.com/2010/06/15/using-atmospheres-jquery-plug-in-to-build-applicationsupporting-both-websocket-and-comet/)**
  - Fallback to comet long-polling
- **[Graceful WebSocket jQuery plugin](https://github.com/ffdead/jquery-graceful-websocket)** by David Lindkvist
  - Fallback to comet long-polling
- **[Portal](https://github.com/flowersinthesand/portal)** by Donghwan Kim
  - Server agnostic and supports Sharing connection, WebSocket, Server-Sent Events, Streaming and Long polling.
- **[DataChannel polyfill](https://github.com/piranna/DataChannel-polyfill)** by Jesús Leganés Combarro “Piranna”
  - Add support for WebRTC DataChannels using a WebSockets proxy server as backend



## Geo-Location

- **[Webshims Lib](http://afarkas.github.io/webshim/demos/index.html#Geolocation)** by Alexander Farkas
- **[geolocation polyfill](http://www.calormen.com/polyfill/#geo)** by Joshua Bell
- **[geolocation shim](https://gist.github.com/paulirish/366184)** by Paul Irish
- **[geo-location-javascript](http://code.google.com/p/geo-location-javascript/)**
  - Mobile-centric: non-standard Blackberry and WebOS tricks
- **[Geolocation-API-Polyfill](https://github.com/manuelbieh/Geolocation-API-Polyfill)** by Manuel Bieh



## Beacon

- **[Navigator.sendBeacon](https://github.com/miguelmota/Navigator.sendBeacon)** by Miguel Mota



## Application Cache

- **[html5-gears](http://code.google.com/p/html5-gears/)** by Brad Neuberg

#### `<link rel="prefetch|prerender" ...`

- **[jiagra](https://github.com/samyk/jiagra)** by Samy Kamkar
  - A psuedo-polyfill for preloading pages to browser cache



## Browser State Management

#### Visibility

- **[Visibility.js](https://github.com/ai/visibility.js)** by Andrey Sitnik
- **[visibly.js](https://github.com/addyosmani/visibly.js)** by Addy Osmani
- **[Page Visibility shim for jQuery](https://github.com/mathiasbynens/jquery-visibility)** by Mathias Bynens
  - The [HTML5 Page Visibility API](http://www.w3.org/TR/page-visibility/) allows you to determine whether your web page is visible to the user, is hidden in background tab, or is prerendering. visibility.js deals with vendor-prefixes and provides a fallback for browsers without this API by assuming the page is always visible. However, this is a wrapper more than a polyfill.

#### Offline & Online Events

- **[offline-event.js](https://github.com/remy/polyfills/blob/master/offline-events.js)** by Remy Sharp (Opera not supported. Safari doesn't update `navigator.onLine` property.)
- **[heyoffline.js](http://oskarkrawczyk.github.com/heyoffline.js)** by oskarkrawczyk

#### HTML5 History API (pushState, replaceState, popState)

- **[History.js](https://github.com/browserstate/history.js)** by Benjamin Lupton
  - (optional `hashchange` fallback for HTML4 browsers)
- **[HTML5-History-API](https://github.com/devote/HTML5-History-API)** by Dmitriy Pakhtinov
  - Lightweight, and fully standards-compliant implementation of History API with IE6+ support and `hashchange` implementation
- **[PJAX](http://pjax.heroku.com)** by Chris Wanstrath
  - (`pushState` + ajax = pjax) (not a polyfill)

#### `hashchange` Event

- **[`hashchange` jQuery event](http://benalman.com/projects/jquery-hashchange-plugin/)** by Ben Alman
- **[`HistoryManager` Mootools Plugin](http://mootools.net/forge/p/historymanager/)** by Arieh Glazer
- **[SWFAddress](http://www.asual.com/swfaddress/)** (popular among Flash developers) & **[jQuery Address](http://www.asual.com/jquery/address/)** by Asual DZZD
- **[jQuery Ajaxy](http://balupton.com/projects/jquery-ajaxy)** by Benjamin Lupton
- **[Hasher](https://github.com/millermedeiros/hasher/)** by Miller Medeiros
- **[sHistory](https://github.com/tatsh/sHistory)** by Andrew Udvare



## Drag and drop

- **[Drag drop shim](https://github.com/timruffles/ios-html5-drag-drop-shim)** by Tim Ruffles



## requestAnimationFrame

- **[`AnimationFrame`](https://github.com/kof/animation-frame)** even better animation frame by Oleg Slobodskoi
- **[`requestAnimationFrame`](http://paulirish.com/2011/requestanimationframe-for-smart-animating/)** by Erik Möller
- **[`raf.js`](https://github.com/ngryman/raf.js)** dependency-free polyfill by Nicolas Gryman



## Animated PNG (APNG)

- **[APNG-Canvas](https://github.com/davidmz/apng-canvas)** by Давид Мзареулян
- **[png.js](https://github.com/devongovett/png.js)** by Devon Govett
  - Parses and renders PNGs both animated and static to a canvas element with putImageData



## Ruby

- **[Cross-browser ruby annotations using CSS](http://www.useragentman.com/blog/2010/10/29/cross-browser-html5-ruby-annotations-using-css/)** by Zoltan Hawryluk



## New tag

#### `<details>` and `<summary>`

- **[Details Element Polyfill](https://github.com/javan/details-element-polyfill)** by Javan Makhmali
- **[Accessible `<details>` fallback via jQuery](http://mathiasbynens.be/notes/html5-details-jquery)** by Mathias Bynens ([repository](https://github.com/mathiasbynens/jquery-details))
- **[Another `<details>` alternative, also based on jQuery](https://github.com/manuelbieh/Details-Polyfill)** by Manuel Bieh
- **[jquery-details](http://akral.bitbucket.org/details-tag/)** by Denis Sokolov
- **[Pure JS polyfill with DOM API and IE6+ support](https://github.com/termi/Element.details)** by Егор Халимоненко
- **[Deets - jQuery UI Widget based fallback + enhancements](https://github.com/Akkuma/jquery-deets)** by Gregory Waxman
- **[better-details-polyfill](https://github.com/chemerisuk/better-details-polyfill)** by Maksim Chemerisuk

#### `<dialog>`

- **[dialog-polyfill](https://github.com/GoogleChrome/dialog-polyfill)** by Google

#### `<meter>`

- **[`<meter>` meter-polyfill](https://github.com/fisker/meter-polyfill)** by fisker Cheung
- **[`<meter>` fallback](https://gist.github.com/667320)** by strings28
- **[`<meter>` jQuery plugin/shim](https://github.com/xjamundx/HTML5-Meter-Shim)** by xjamundx
- **[`<meter>` Dojo Toolkit module](http://codepen.io/whymarrh/pen/rjawK)** by Whymarrh Whitby

#### `<output>`, `<progress>`, `<menu>`, `<command>`

- **[`<progress>` polyfill](https://github.com/LeaVerou/HTML5-Progress-polyfill)** by Lea Verou
- **[`<menu type="context">` polyfill](https://github.com/swisnl/jQuery-contextMenu)** by Björn Brala and Rodney Rehm

#### `dataset` property (for use with custom `data-*` attributes)

- **[`dataset` shim](https://github.com/code42day/dataset)**
- **[`dataset` fallback rewritten](https://gist.github.com/4093766#file_html5_dataset.js)** by Brett Zamir
- **[`element-dataset`](https://github.com/epiloque/element-dataset)** with cross browser tests
- **[`dataset` ponyfill](https://github.com/awcross/elem-dataset)** by Alex Cross

#### `<ol reversed>`

- **[Polyfill for `reversed` attribute on ordered lists](https://github.com/impressivewebs/HTML5-Reverse-Ordered-Lists)** by Louis Lazaris. Also integrates with the `start` attribute, which has 100% browser support. See also: [Reverse Ordered Lists in HTML5](http://www.impressivewebs.com/reverse-ordered-lists-html5/)
- **[A vanilla-js polyfill (with `start` attribute support)](https://gist.github.com/1671548)**

#### `<style scoped>`

- **[Scoped Styles](http://github.com/thingsinjars/jQuery-Scoped-CSS-plugin)** by Simon Madine
  - jQuery Plugin to enable the scoped attribute on style blocks so they only affect their parent element's children.
- **[Scoper](https://github.com/thomaspark/scoper)** by Thomas Park

#### `<picture>` and `<img srcset>`

- **[picturefill](http://scottjehl.github.io/picturefill/)** by Scott Jehl
  - A polyfill for `<picture>`, `srcset` and `sizes`.
- **[respimage](https://github.com/aFarkas/respimage)** by Alexander Farkas
  - A polyfill for `<picture>`, `srcset` and `sizes` with smart resource selection



## File API

- **[dropfile.js](https://github.com/MrSwitch/dropfile)** by Andrew Dodson
  - Creates the FileReader part of the [FileAPI](http://www.w3.org/TR/FileAPI/) via Silverlight for drag and drop files
- **[FileSaver.js](https://github.com/eligrey/FileSaver.js)** by Eli Grey
  - Implements `saveAs()`
  - Includes `BlobBuilder` shim
- **[mOxie](https://github.com/moxiecode/moxie)** Polyfill extracted from Plupload
  - FileReader, drag and drop
  - XHR2 shim for storing on IE<10, FormData
  - Flash fallback
  - File input 'overlay'
- **[FileReader.js](https://github.com/Jahdrien/FileReader)** by Jahdrien
  - Creates FileReader and FileAPI using Flash, jQuery and jQuery UI
  - No drag and drop support!
- **[FileAPI](https://github.com/mailru/FileAPI)** by Konstantin Lebedev (© Mail.ru Group)
  - Multiupload: all browsers that support HTML5 or Flash
  - Drag'n'Drop upload: files (HTML5) & directories (Chrome 21+)
  - Upload one file: all browsers
  - Working with Images: IE6+, FF 3.6+, Chrome 10+, Opera 11.1+, Safari 5.4+
- **[idb.filesystem.js](https://github.com/ebidel/idb.filesystem.js)** by Eric Bidelman
  - HTML5 Filesystem API polyfill that uses IndexedDB as a storage layer.
- **[`window.saveAs`](https://gist.github.com/3552985)** by Andrew Dodson
  - Simple shim (for IE10 current Chrome and FireFox)



## Binary and Typed data

- **[jDataView](https://github.com/vjeux/jDataView/)** by vjeux
  - `DataView` polyfill for structured data
- [Typed Arrays](http://www.calormen.com/polyfill/#typedarray) by Joshua Bell



## Base64 (`window.atob` and `window.btoa`)

- [David Chambers’ `window.btoa` and `window.atob` polyfill](https://github.com/davidchambers/Base64.js)



## WebRTC / `getUserMedia()`

- [getUserMedia.js](https://github.com/addyosmani/getUserMedia.js) by Addy Osmani provides a cross-browser shim for `getUserMedia()` camera access.
- [webrtc4all](https://code.google.com/p/webrtc4all/) by Doubango Telecom provides the WebRTC APIs for Safari, Opera Classic and IE via an NPAPI/ActiveX plugin.
- [Temasys WebRTC Plugin](https://temasys.atlassian.net/wiki/display/TWPP/WebRTC+Plugins/) by Temasys provides the WebRTC APIs for Safari and IE via an NPAPI/ActiveX plugin.



## WebGL

- [jebgl](http://code.google.com/p/jebgl/)
  - Uses a Java applet to emulate.
- [webgl-compat](https://github.com/sinisterchipmunk/webgl-compat)
  - maps the API to 2D canvas
- [cwebgl](http://code.google.com/p/cwebgl/)
- [IEWebGL](https://github.com/iewebgl)



## MathML

- **[MathJax](http://www.mathjax.org)**



## Cross-Document/Domain Messaging (`postMessage`)

- **[easyXDM](http://easyxdm.net/)** by Sean Kinsey
  - Implements XDM and RPC in most browsers since IE6\. Also ships with an endpoint for exposing ajax across the domain boundary.
- **[postMessage jquery plugin](http://benalman.com/projects/jquery-postmessage-plugin/)** by Ben Alman



## Cross-Origin Resource Sharing (CORS)

- **[XDomain](https://github.com/jpillora/xdomain)** by Jaime Pillora
  - Transparently enable cross-domain XMLHttpRequest by adding a small `proxy.html` on the destination domain*
- **[pmxdr](http://purl.eligrey.com/github/pmxdr)** by Eli Grey
  - Implements a CORS-compliant cross-domain `XMLHttpRequest` with `postMessage`. Note that sites being requested must have a pmxdr host.
- **[libxdr](http://purl.eligrey.com/github/libxdr)** by Eli Grey
  - Implements a CORS `XMLHttpRequest` drop-in using pmxdr.
- **[postmessage-proxied-xhr (PPX)](https://github.com/toolness/postmessage-proxied-xhr/#readme)** by Atul Varma
- **[flXHR](https://github.com/flensed/flXHR)** by Kyle Simpson
  - Provides XHR API using Flash transport mechanism. Target server must have a `crossdomain.xml` policy file.



## DOM & Events

- **[Flow](https://code.google.com/p/flowjs/)**
  - implements DOM3 in IE6+
- **[DOM-shim](https://github.com/Raynos/DOM-shim)**
  - implements [DOM4](http://dvcs.w3.org/hg/domcore/raw-file/tip/Overview.html) in IE8+
- **[DOM4](https://github.com/WebReflection/dom4#dom4)** by Andrea Giammarchi
  - HTMLElement `prepend`, `append`, `before`, `after`, `replace`, and `remove`
  - Also: `classList`, `matches`, and `CustomEvent`
  - W3C Specs compatible and fully tested
- **[IE8 DOM Level 2](https://github.com/WebReflection/ie8#ie8)** by Andrea Giammarchi
  - W3C Events, included custom bubbling events, for IE8
- **[`document.head`](http://mathiasbynens.be/notes/document-head)**
- **[url.js](https://gist.github.com/1384398)** implements the [W3C URL API](http://dvcs.w3.org/hg/url/raw-file/tip/Overview.html), by Erik Arvidsson
  - also [polyfilled by Joshua Bell](http://www.calormen.com/polyfill/#url)
- **[DOM Keyboard Event Level 3 polyfill](https://github.com/termi/DOM-Keyboard-Event-Level-3-polyfill)** by Егор Халимоненко
  - with optional IE6–8 support
- **[`DOMImplementation.prototype.createDocument`](https://gist.github.com/4274369)** by Brett Zamir
- **[`navigator.language`](https://gist.github.com/brettz9/6150009)** very simple shim by Brett Zamir
- **[`document.currentScript`](https://github.com/JamesMGreene/document.currentScript)** by James M. Greene

#### `classList`

- **[classList.js](https://github.com/remy/polyfills/blob/master/classList.js)** by Remy Sharp
- **[classList.js](http://purl.eligrey.com/github/classList.js)** by Eli Grey
- **[Minimal `classList` shim](https://gist.github.com/1381839)** by Devon Govett

#### EventSource

- **[`EventSource`](https://github.com/remy/polyfills/blob/master/EventSource.js)** by Remy Sharp
- **[`jQuery.EventSource`](http://github.com/rwldrn/jquery.eventsource)** by Rick Waldron
- **[`EventSource`](https://github.com/Yaffle/EventSource/blob/master/eventsource.js)** by Yaffle
- **[`EventSource`](https://github.com/amvtek/EventSource)** by AmvTek
  - Provides in-browser **Unit Tests** suite
  - Documents what needs to be considered when patching `EventSource`

#### Pointer Events (API)

- **[Hand.js](https://github.com/Deltakosh/handjs)** by DeltaKosh
  - Implements the [Pointer Events](http://www.w3.org/Submission/pointer-events/) API
- **[Pointy.js](https://github.com/vistaprint/PointyJS)** by Vistaprint
  - Implements the [Pointer Events](http://www.w3.org/Submission/pointer-events/) API
- **[Pointer Events Polyfill](https://github.com/jquery/pep)** by jQuery (originally part of Google Polymer)
  - Implements the [Pointer Events](http://www.w3.org/TR/pointerevents/) API

#### Touch Events (API)

- **[ie-touch.js](https://github.com/WebReflection/ie-touch#ie-touch)** by Andrea Giammarchi
  - Implements the W3C [Touch Events](http://www.w3.org/TR/touch-events/) API for IE Mobile and Tablets

#### Pointer Events (CSS)

- **[Pointer Events Polyfill](https://github.com/kmewhort/pointer_events_polyfill)** by Kent Mewhort
  - Implements `pointer-events: none` in IE and other non-supporting browsers.
- **[jquery.pointer-events-polyfill](https://github.com/screeny05/jquery.pointer-events-polyfill)** by Sebastian Langer
  - Adds `pointer-events: none|all;` drop-in-support for all non-supporting browsers.

#### DOM Range and Selection

- **[selecting](https://github.com/EvandroLG/selecting)** by EvandroLG
  - A library that allows you to access the text selected by the user
- **[Rangy](https://github.com/timdown/rangy)** by Tim Down
  - Implements [DOM Range and Selection](http://html5.org/specs/dom-range.html) APIs in IE < 9.
- **[selection-polyfill](https://github.com/luwes/selection-polyfill)** by Wesley Luyten

#### New Events

- **[`transitionEnd`](https://github.com/EvandroLG/transitionEnd/)**
  - Agnostic, cross-browser lib. Work with the `transitionend` event.

#### DOM Parsing and Serialization

- **[insertAdjacentHTML.js](https://gist.github.com/1276030)** by Eli Grey, implements [`insertAdjacentHTML`](http://html5.org/specs/dom-parsing.html#dom-element-insertadjacenthtml)
- **[outerHTML.js](https://gist.github.com/1044128)** by Eli Grey, implements [`outerHTML`](http://html5.org/specs/dom-parsing.html#dom-element-outerhtml)
- **[DOMParser HTML extension](https://gist.github.com/1129031)** by Eli Grey, implements [DOMParser `text/html` support](http://html5.org/specs/dom-parsing.html#the-domparser-interface)

#### XPath

- **[js-xpath](http://nchc.dl.sourceforge.net/project/js-xpath/js-xpath/1.0.0/xpath.js)**
  - Provides `document` with `evaluate`, `createNSResolver`, `createExpression`
  - Adds support for `XPathResult`, `XPathNSResolver`, and `XPathExpression`.
- **[wicked-good-xpath](https://code.google.com/p/wicked-good-xpath/)** rewrite of js-xpath with support for newer (>9) IE versions



## ECMAScript

#### Web Workers

_Fake workers are useful for unit testing or for fallback behavior on non-supporting browsers_

- **[fakeworker](http://code.google.com/p/fakeworker-js/)**
- **[Web Worker API shim](http://html5-shims.googlecode.com/svn/trunk/demo/workers.html)**
- **[Simulated Web Workers](https://github.com/timdream/simworker)** by Timothy Guan-tin Chien
  - Web Workers for IEs and Mobile Safari; uses `iframes` to create separate environments for workers
- **[EasyWebWorker](https://github.com/ramesaliyev/EasyWebWorker)** by Rameş Aliyev

#### Arrays

- **[`Array.prototype.slice`](https://gist.github.com/brettz9/6093105)** adds ability to treat DOM elements as arrays. This behavior is not required by any standard given that it applies to host object behavior (which is implementation-dependent), but it is not forbidden either.
- **[Array Generics](https://github.com/plusdude/array-generics)**
  - Implementation of standard Array methods (introduced in ECMAScript 5th edition) and shorthand generics (JavaScript 1.8.5)
  - Browser support: Internet Explorer 6+, Firefox 1.5+, Chrome, Safari, Opera.

#### ECMAScript 5

- **`Array.prototype`** methods from MDN: [`indexOf`](https://developer.mozilla.org/en-US/docs/JavaScript/Reference/Global_Objects/Array/indexOf), [`lastIndexOf`](https://developer.mozilla.org/en-US/docs/JavaScript/Reference/Global_Objects/Array/lastIndexOf), [`forEach`](https://developer.mozilla.org/en-US/docs/JavaScript/Reference/Global_Objects/Array/forEach), [`every`](https://developer.mozilla.org/en-US/docs/JavaScript/Reference/Global_Objects/Array/every), [`filter`](https://developer.mozilla.org/en-US/docs/JavaScript/Reference/Global_Objects/Array/filter), [`some`](https://developer.mozilla.org/en-US/docs/JavaScript/Reference/Global_Objects/Array/some), [`map`](https://developer.mozilla.org/en-US/docs/JavaScript/Reference/Global_Objects/Array/map), [`reduce`](https://developer.mozilla.org/en-US/docs/JavaScript/Reference/Global_Objects/Array/reduce), [`reduceRight`](https://developer.mozilla.org/en-US/docs/JavaScript/Reference/Global_Objects/Array/reduceRight)
- **[`Function.prototype.bind`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Function/bind)** from MDN.
- **[es5-shim](http://github.com/kriskowal/es5-shim/)** by Kris Kowal, Tom Robinson, community.
- **[Xccessors](http://purl.eligrey.com/github/Xccessors)** by Eli Grey.
  - Implements ES5 accessors (getters and setters) for browsers supporting legacy methods and/or legacy methods for browsers supporting ES5.
- **[getters and setters](http://blogs.msdn.com/b/ie/archive/2010/09/07/transitioning-existing-code-to-the-es5-getter-setter-apis.aspx)** by the IE team.
  - Pick up get/set'ers for DOM elements in IE8
- **[json2.js](https://github.com/douglascrockford/JSON-js/blob/master/json2.js)** by Douglas Crockford
- **[json3.js](http://bestiejs.github.com/json3/)** by Kit Cambridge
- **[ddr-ecma5](http://code.google.com/p/ddr-ecma5)** by David de Rosier
- **[augment.js](http://augmentjs.com)** by Oliver Nightingale
- **[String.js](https://gist.github.com/4050063)** by Brett Zamir
  - Allows array-like accessors on strings created via `new String()` (admittedly, not very useful)

#### ECMAScript 6 (Harmony)

- **[es6-shim](http://github.com/paulmillr/es6-shim/)** by Paul Miller
- **[core-js](https://github.com/zloirock/core-js)** by Denis Pushkarev
- **[`WeakMap`, `Map`, `Set`, `HashMap` - ES6 Collections](https://github.com/Benvie/harmony-collections)** by Brandon Benvie
- **[`Function.create`](https://github.com/walling/Function.create.js)** by Bjarke Walling
- **[`String.prototype.contains`](https://github.com/robertkowalski/contains.js)** by Robert Kowalski
- **[`Object.observe` polyfill](https://github.com/MaxArt2501/object-observe)** by Massimo Artizzu
- **[ES6 shim](https://github.com/inexorabletash/polyfill/blob/master/es6.js)** by inexorabletash
- **[ES6 `Map`, `Set`, `WeakMap`](https://github.com/EliSnow/Blitz-Collections)** by EliSnow
- **[`Object.assign` polyfill](https://github.com/msn0/object-assign-mdn)** by Michał Jezierski - implementation from [MDN article](https://developer.mozilla.org/pl/docs/Web/JavaScript/Referencje/Obiekty/Object/assign#Polyfill)

#### Promise

- **[es6-promise](https://github.com/jakearchibald/es6-promise)**
  - Polyfill for JavaScript Promises, based on RSVP.js but matches ES6 API
- **[P.js](https://github.com/EvandroLG/P)**
  - An agnostic, cross-browser and very lightweight library to help you to work with Promise in JavaScript.
- **[rsvp.js](https://github.com/tildeio/rsvp.js)**
  - Implementation of Promises/A with mixin for turning objects into event targets.
- **[lie](https://github.com/calvinmetcalf/lie)**
  - lie is a small, performant promise library implementing the Promises/A+ spec (Version 1.1).



## CSS Prefix generators

- **[cssFx](http://imsky.github.com/cssFx/)** - by Ivan Malopinsky
  - Standalone, lightweight, client-side JS; supports almost all CSS3 properties
- **[CSS Crush](http://the-echoplex.net/csscrush/)**
  - A PHP based CSS pre-processor for handling vendor prefixes, CSS variables, data-uris and minification
- **[CSS Agent](http://www.keithclark.co.uk/labs/cssagent/)** by Keith Clark
  - A ASP.Net based CSS pre-processor for handling vendor prefixes, CSS variables, and minification
- **[jQuery Css3 Finalize](https://github.com/codler/jQuery-Css3-Finalize)** by Han Lin Yap
- **[-prefix-free](http://leaverou.github.io/prefixfree/)** by Lea Verou
- **[Autoprefixer](https://github.com/ai/autoprefixer)** by Andrey Sitnik
  - A fast post-processor that uses the data on current browser popularity (caniuse.com) and adds their vendor prefixes or other required syntax changes. Great integration with Grunt, Rails, Sublime Text, and others.



## CSS, core modules

#### Selectors, [L3-spec](http://www.w3.org/TR/selectors/), [L4-spec](http://www.w3.org/TR/selectors4/)

- **[selectivizr](http://selectivizr.com)** by Keith Clark
- **[cssParentSelector](http://demo.idered.pl/jQuery.cssParentSelector/)** by Kasper Mikiewicz
- **[CSS3/4 `querySelectorAll` and `matches` polyfill](https://github.com/termi/CSS_selector_engine)** by Егор Халимоненко. Pure JS with optional IE6/7 support. Currently CSS4 Selector API supporting:
  - subject of a selector: `div! a[href*=twitter]`
  - `:scope` pseudo-class: `:scope>*:nth-child(2n+1)`
  - nodesRef: `document.querySelector("a", <div>)` -> `<a>` child of `<div>`

#### Values and Units, [spec](http://www.w3.org/TR/css3-values/)

- **[CSS3 - REM Unit conversion](https://github.com/chuckcarpenter/REM-unit-polyfill)** by Chuck Carpenter and Lucas Serven
  - Evaluates stylesheets for `REM` declarations, converts them to pixels and appends to the `HEAD`. Has no dependencies, but can easily be implemented with Modernizr/Yepnope for loading.
- **[Units](https://github.com/heygrady/Units)** by Grady Kuhnline
  - Units is a JavaScript library for converting between angle and length units (including the `rem` unit). Both are intended for use within other libraries that need to convert between acceptable CSS units when creating polyfills.
- **[viewport-units-buggyfill](https://github.com/rodneyrehm/viewport-units-buggyfill)** by Rodney Rehm
  - Viewport units in Safari and IE9, and slightly hackier mode that puts them in `calc()`
- **[vminpoly](https://github.com/saabi/vminpoly)** by Sebastian Ferreyra
  - A polyfill for CSS units `vw`, `vh` & `vmin`.
- **[Prefixfree - Viewport Relative Units Plugin](http://leaverou.github.io/prefixfree/#plugins)** by Lea Verou
  - Another `vw`, `vh`, and `vmin` polyfill
  - Requires prefixfree (2kb).
- **[cssMinMax](https://github.com/indyarmy/jquery.cssMinMax.plugin)** by Russ Porosky
  - `min()` and `max()` jQuery plugin polyfill
  - Includes JSCSSP, so it's a bit large

#### Image Values and Replaced Content, [L3-spec](http://www.w3.org/TR/css3-images/), [L4-spec](http://www.w3.org/TR/css4-images/)

- **[jQuery.object-fit.js](https://github.com/steveworkman/jquery-object-fit)** by Steve Workman (fork of Simon Schmid's work)
  - CSS3 object-fit via jQuery plugin API. Currently supports: `object-fit: contain|cover;` (for [developing standard](http://dev.w3.org/csswg/css3-images/#object-fit))
- **[object-fit.js](https://github.com/anselmh/object-fit)** by Anselm Hannemann (and Christian Schaefer)
  - CSS3 `object-fit` via vanilla JS polyfill. Currently supports: `object-fit: contain|cover|fill` (for [CR standard](http://www.w3.org/TR/css3-images/#the-object-fit))
- **[-image-set on img elements](https://github.com/fabdrol/retina-img-set)** by Fabian Tollenaar

#### Backgrounds and Borders, [spec](http://www.w3.org/TR/css3-background/)

- **[CSS3 PIE](http://css3pie.com)** by Jason Johnston
  - CSS3 decoration rendering for IE 6-9\. Supports: `border-radius`, `box-shadow`, multiple backgrounds, linear gradients, `border-image`
- **[background-size polyfill](https://github.com/louisremi/background-size-polyfill)** by Louis-Rémi Babé
  - `background-size` for IE7 and IE8 via Microsoft's proprietary CSS behavior / `.htc-script`
- **[background-size emu](https://github.com/Metafalica/background-size-emu)** by Metafalica
  - a better `background-size` polyfill that doesn't need an `.htc` script

#### Basic user interface, [spec](http://www.w3.org/TR/css3-ui/)

- **[jQuery Text Overflow plugin](http://www.bramstein.com/projects/text-overflow/)** by Devon Govett, Andrew A. Kononykhin, Micky Hulse
  - `text-overflow` via jQuery plugin API (for [developing standard](http://dev.w3.org/csswg/css3-ui/#text-overflow))
- **[borderBoxModel](https://github.com/albertogasparin/borderBoxModel)** by Alberto Gasparin
  - `box-sizing: border-box;` javascript polyfill for IE6+
- **[box-sizing-polyfill](https://github.com/Schepp/box-sizing-polyfill)** by Christian “Schepp” Schaefer
  - `box-sizing: border-box;` for IE6 and IE7 via Microsoft's proprietary CSS behavior / `.htc-script`
- **[Borderbox for Compass](https://github.com/doctyper/compass-borderbox)** by Richard Herrera
  - `box-sizing: border-box;` polyfill for SASS/Compass. Outputs equivalent CSS for IE6 & 7



## CSS, responsive design modules

#### Media Queries Level 3, [spec](http://www.w3.org/TR/css3-mediaqueries/)

- **[css3-mediaqueries-js](http://code.google.com/p/css3-mediaqueries-js/)**
- **[Respond](https://github.com/scottjehl/Respond)** by Scott Jehl
  - A fast & lightweight polyfill for min/max-width CSS3 Media Queries (for IE 6-8, and more)
- **[mediatizr](https://github.com/pyrsmk/mediatizr)** by Aurélien Delogu
  - Responsive-oriented CSS3 media queries polyfill
- **[matchMedia](https://github.com/paulirish/matchMedia.js/)** by Scott Jehl, Paul Irish, Nicholas Zakas
  - A standardized way to check media query matching in script.
- **[jQuery Media Helpers](https://github.com/scottjehl/jQuery-Media-Helpers)** by Scott Jehl
  - Some media query and cross-browser responsive design helpers, abstracted from jQuery Mobile
- **[pointeraccuracy.js](https://github.com/n-fuse/pointeraccuracy.js)** by n-fuse
  - Implementation of the `pointer` media query

#### Media Queries Level 4, [spec](http://dev.w3.org/csswg/mediaqueries-4/)

- **[mq4-hover-shim](https://github.com/twbs/mq4-hover-shim)**
  - A shim for the [`hover: hover`](http://dev.w3.org/csswg/mediaqueries-4/#hover) media query

#### Conditional rules, [spec](http://www.w3.org/TR/css3-conditional/)

- **[CSS.supports()](https://gist.github.com/codler/03a0995195aa2859465f)** by Han Lin Yap
- **[CSS.supports polyfill](https://github.com/termi/CSS.supports/)** by Егор Халимоненко
- **[@supports polyfill](https://github.com/kjarmicki/fq-polyfill)** by Krystian Jarmicki
  - Polyfills `window.CSS.supports()` method and `@supports` rules in stylesheets



## CSS, text modules

#### Text decoration, [spec](http://www.w3.org/TR/css-text-decor-3/)

- **[jQuery Text Shadow](https://github.com/heygrady/textshadow)** by heygrady
  - `text-shadow` action via jQuery plugin API



## CSS, font modules

#### Font events, [spec](http://dev.w3.org/csswg/css-font-load-events-3/)

- **[fontloader](https://github.com/bramstein/fontloader)** by Bram Stein



## CSS, layout modules

#### Multi-column Layout, [spec](http://www.w3.org/TR/css3-multicol/)

- **[CSS3 - Multi Column](https://github.com/BetleyWhitehorne/CSS3MultiColumn)** Updated for HTML5 tags
  - Supports: `column-count`, `column-width`, `column-gap`, `column-rule` **[Original by](http://www.csscripting.com/css-multi-column/)** by Cédric Savarese

#### Flexible Box Layout, [spec](http://www.w3.org/TR/css3-flexbox/)

- **[Flexie](http://github.com/doctyper/flexie)** by Richard Herrera
  - Flexible box model - _legacy spec from 2009_. (flexbox) Supports: `box-orient`, `box-align`, `box-direction`, `box-pack`, `box-flex`, `box-ordinal-group`
- **[Flexibility](https://github.com/10up/flexibility)** - Flexbox for IE 8/9 (requires special prefixed CSS)
- Any Flexbox polyfill should also be paired with a post-processor like **[Autoprefixer](https://github.com/postcss/autoprefixer)** for generating rules compatible with IE10 and old iOS Safari

#### Grid Layout, [spec](http://www.w3.org/TR/css3-grid-layout/)

- **[Grid Layout Polyfill](https://github.com/FremyCompany/css-grid-polyfill)** by François REMY
- **[Grid Layout Polyfill](https://github.com/codler/Grid-Layout-Polyfill)** by Han Lin Yap

#### Template Layout, [spec](http://www.w3.org/TR/css3-layout/)

- **[CSS Template Layout jQuery plug-in](http://css-template-layout.googlecode.com)** by Alexis Deveria

#### Regions, [spec](http://www.w3.org/TR/css3-regions/)

- **[CSS Regions Polyfill](https://github.com/FremyCompany/css-regions-polyfill)** by François Remy



## CSS, effects modules

#### Transforms, [spec](http://www.w3.org/TR/css3-transforms/)

- **[Transformie](https://github.com/pbakaus/transformie)** by Paul Bakaus
- **[CSS Sandpaper](http://www.useragentman.com/blog/2010/03/09/cross-browser-css-transforms-even-in-ie/)** by Zoltan Hawryluk

#### Filter Effects, [spec](http://www.w3.org/TR/filter-effects/)

- **[Polyfilter - a CSS Filters Polyfill](https://github.com/Schepp/CSS-Filters-Polyfill)** by Christian "Schepp" Schaefer
  - CSS `filter` effects for Chrome 20+, Safari 6+, Firefox 4+, IE 6–9 and some mobile browsers.



## CSS, generated content

- **[CSS Polyfills](https://github.com/philschatz/css-polyfills.js)** by philschatz
  - Implements many of the CSS selectors and rules defined in CSS3 Generated and Replaced Content Module and CSS3 Generated Content for Paged Media Module



## Microdata API

- **[microdatajs](http://gitorious.org/microdatajs)** by Philip Jägenstedt
- **[Microdata-JS](https://github.com/termi/Microdata-JS)** by Егор Халимоненко
  - Pure JS (Extending Element.prototype with IE6+ support)



## Notification API

- **[notification.js](http://adodson.com/notification.js)** by Andrew Dodson
- **[`desktop-notify`](https://github.com/ttsvetko/HTML5-Desktop-Notifications)** by Tsvetan Tsvetkov (uses deprecated syntax - createNotification)
- **[html5-notifications](https://gist.github.com/Asmod4n/6030828)** by Hendrik Beskow



## XBL

- **[xbl.js](https://github.com/ilinsky/xbl)** by Sergey Ilinsky



## Flash

- **[Mozilla Shumway](https://github.com/mozilla/shumway)**
  - Flash VM and runtime written in JavaScript.
- **[Google Swiffy](http://swiffy.googlelabs.com)**
  - Webapp converts SWF to HTML+JS. Supports subset of SWF 8 and ActionScript 2.0, and webkit-only output.
- **[Gordon](https://github.com/tobeytailor/gordon/wiki/)**
  - Javascript that interprets SWFs live. Plays only SWF1 files completely, as well as most of the SWF2 features.



## Web Performance (Profile)

- **[UserTiming.js](https://github.com/nicjansma/usertiming.js)** by Nic Jansma
- **[`performance.now()`](https://gist.github.com/paulirish/5438650)** by Paul Irish
- **[Core Estimator](https://github.com/oftn/core-estimator)** by Eli Grey, Devin Samarin, and Yorick van Pelt
  - A polyfill for [`navigator.hardwareConcurrency`](https://wiki.whatwg.org/wiki/Navigator_HW_Concurrency).



## Hyphenation

- **[hyphenator](http://code.google.com/p/hyphenator/)** by Mathias Nater
  - [CSS3](http://www.w3.org/TR/css3-text/#hyphenation) defines six properties and an at-rule that influence hyphenation. `hyphenator` is a JavaScript implementation with pattern files for many languages.



## GamePad API

- **[JavaScript Joystick](https://code.google.com/p/javascript-joystick/)** by Carl Woffenden
- **[Boomstick](https://github.com/STRd6/Boomstick)** by Daniel X. Moore



## Media Fragments

- **[xywh.js](https://github.com/tomayac/xywh.js)**
  - Polyfill that lets you crop images and videos simply by using specific `x`, `y`, `w`(idth), and `h`(eight) parameters from their URIs.
  - The library implements the [spatial media fragments](http://www.w3.org/TR/media-frags/#naming-space) dimension of the W3C Media Fragments URI specification.
- **[mediafragments.js](https://github.com/tomayac/Media-Fragments-URI)**
  - Polyfill that lets you place deep links into videos and audios simply by using a specific `t`(ime) parameter from their URIs.
  - The library implements the [temporal media fragments](http://www.w3.org/TR/media-frags/#naming-time) dimension of the W3C Media Fragments URI specification.



## Other

- **[Permission API](https://github.com/jimmywarting/browser-su)**
  - Extended version that stay consistent with the `navigator.permission` API
- **[Overthrow](https://github.com/filamentgroup/Overthrow)**
  - `overflow:auto` detection and polyfill
- **[iScroll](https://github.com/cubiq/iscroll)**
  - The `overflow:scroll` for mobile
- **[Scroll Snap](https://github.com/ckrack/scrollsnap-polyfill)**
  - CSS scroll snapping
- **[`RadioNodeList` polyfill](https://gist.github.com/1647489)**
- **[screenfull.js](https://github.com/sindresorhus/screenfull.js)**
  - Simple wrapper for cross-browser usage of the JavaScript Fullscreen API
- `<marquee scrollamount="100%">blink</marquee>`
  - HTML-only polyfill for the no longer supported `<blink>` element.
- **[pointeraccuracy.js](https://github.com/n-fuse/pointeraccuracy.js)**
  - Implementation of the `pointer` media query
- **[`scrollTo(x, y, 'smooth')`](https://github.com/iamdustan/smoothscroll)**
  - CSSOM View smooth scroll polyfill
- **[`window.location.origin` fix for IE](http://tosbourn.com/a-fix-for-window-location-origin-in-internet-explorer/)**
  - A fix to allow you to use window.location.origin consistently
- **[`W3C Manifest`](https://github.com/boyofgreen/manUp.js/)**
  - W3C Manifest polyfill support for Safari iOS, Windows Phone 8+, Windows 8+, Firefox OS 1.1+, the Android browser and Chrome for Android.
- **[console-polyfill](https://github.com/paulmillr/console-polyfill)** by Paul Miller
  - Adds no-operation console methods to environments where console is not available. Basically makes console safe to use.



## Collection

- **[Webshims Lib](http://afarkas.github.io/webshim/demos/)** several Polyfills using lightweight capability based loading concept (shiv, innershiv, canvas, forms, ES5, `localStorage`/`sessionStorage`, JSON, geolocation) by Alexander Farkas
- **[Assorted file formats](https://github.com/bebraw/jswiki/wiki/File-Formats)** decoding of several file formats done in Javascript, documented on the excellent [jswiki](https://github.com/bebraw/jswiki/wiki)
- **[Polyfill.js](https://github.com/kbjr/polyfill.js)** Polyfills loaded dynamically based on need (list of available polyfills on the linked page) by James Brumond
- **[ES5/DOM shim](https://github.com/termi/ES5-DOM-SHIM)** implements [DOM API](http://dvcs.w3.org/hg/domcore/raw-file/tip/Overview.html) and EcmaScript 5 (and some from ES6), and bug fixing in IE6+ and other browsers:
  - Add methods such [`add`/`remove`]`EventListener`, `querySelector`[`All`], `setSelectionRange`, etc in IE6+
  - Add `Element`/`Node` properties such `classList`, `children`, [`first`/`last`]`ElementChild`, `reversed`, `control`, `labels`, etc in IE6+
  - Add methods such `insertAdjacentHTML` (old FF), `stopImmediatePropagation` (Opera < 12) and properties `reversed`, `control`, `labels`, etc in W3C browsers
  - Add ES5/6 methods in all browsers
  - Add DOM4 methods `append`, `prepend`, `after`, `before`, `replace`, `remove`, `match` in all browsers
  - Provide bugs fixing for DOM and ES in IE, Opera, Chrome, FF
  - and more with low cost:
    - ≈8KiB for W3C browsers
    - ≈16KiB for IE8
    - ≈18KiB for IE6/7 [gzip]
- **[aight](https://github.com/shawnbot/aight)**
  - A collection of shims and shams for IE8 and 9, and a nifty CLI tool to make your scripts IE8-friendly.
- **[ie7.js, ie8.js, ie9.js](http://code.google.com/p/ie7-js/)** by Dean Edwards
  - A JavaScript library to make MSIE behave like a modern browser. Many fixes including PNG transparency, CSS styles/selectors, rendering bug fixes, etc.

----



## Contributors

Edited and maintained by [Paul Irish](http://paulirish.com). Contributions from [Jonathan Cook](http://code.google.com/p/html5-shims/wiki/LinksandResources), [Mark Boas](http://www.html5patch.com), [Michael Behan](http://twitter.com/#!/irishbehan), [Mathias Bynens](http://mathiasbynens.be/), [Eli Grey](http://eligrey.com), Øyvind Sean Kinsey, and others.