---
layout: post
title: "How to load Ads asynchronously"
date: 2014-05-26 12:54:12 -0700
comments: true
categories: js
---
The Problem
-----------------
Most of the ads come with document.write statements, and we all know what happens when we try to execute document.write statements after the page has been loaded.

The Solution
-----------------
postscribe is a JS library that ensures the content is written as close to the way the browser would natively write the content with document.write/innerHTML, and it does it asynchronously!.

The Implementation
-----------------
### HTML:
``` javascript
<div id="ad"><!-- the ad content will be written here --></div>

<!-- postscribe files -->
<script src="htmlParser/htmlParser.js"></script>
<script src="postscribe.js"></script>
```

### JS:
``` javascript
(function (win) {
	var adCode = '<script>document.write("ad unit");</script>';

	postscribe('#ad', adCode);
}(window));
```

Simple right?!
