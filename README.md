# responsive-img
An experiement respsonsive images plugin.

### Getting Started

To use this plugin we will require a `img` tag and the appropriate selector eg. `.responsiveImg`. 
This will enable the plugin to find the img tag to replace the  `src` dynamically.

```html
	<img alt="" class="" src="loading.gif" title=""
		data-small	="dog-s.jpg"
		data-medium	="dog-m.jpg"
		data-large	="dog-l.jpg"
	/>
	<noscript><img src="dog-s.jpg" alt="" title=""></noscript>
```

### Config

To initialize the plugin, with the default breakpoints.

```javascript
	$( document ).ready(function() {
		$(".responsiveImg").responsiveImg();
	});
```


##### Custom Breakpoints

You can create as many breakpoints as nessercary using the CSS Media Querys.

```javascript
		$( document ).ready(function() {
		  $(".responsiveImg").responsiveImg({
			breakpoints  : 
				[
					{ name: 's',	mq: "(min-width: 000px)"},
					{ name: 'm', 	mq: "(min-width: 420px)"},
					{ name: 'l', 	mq: "(min-width: 640px)"},
					{ name: 'xl', 	mq: "(min-width: 1019px)"},
				],
			});
		});
```

To use a breakpoint, on the `img` simply match the name to a data attribute, eg. `data-m` is directly associated with the `m` breakpoint above.

```html
	<img alt="" class="responsiveImg" src="loading.gif" title=""
		data-s	="dog-s.jpg"
		data-m	="dog-m.jpg"
		data-l	="dog-l.jpg"
		data-xl	="dog-xl.jpg"		
	/>
	<noscript><img src="dog-s.jpg" alt="" title=""></noscript>
```

### Browser Support

This solution is not intended to run in ancient browsers for the 1%. This is built to run in [evergreen browsers](http://eisenbergeffect.bluespire.com/evergreen-browsers/). the main reason for this is the use of [matchMedia](http://caniuse.com/#feat=matchmedia).
It has been tested and works in chrome 31+, safari 7.1+ firefox 35+ and IE10+.

### Copyright and license

Code and documentation copyright 2015 cereal. Code released under the MIT license. Docs released under Creative Commons.
