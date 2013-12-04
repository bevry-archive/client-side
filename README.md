# Bevry's Client Side Approach

## Typical Architecture

- Building
	- Make
	- Grunt
	- Brunch
	- DocPad
- PreProcessors
	- Jade/CoffeeKup/Eco/Markdown
	- CoffeeScript/LiveScript/ClojureScript
	- Stylus/SASS/Less
- Packaging
	- Bower
	- Component
	- NPM / Browerserify / Ender
- DOM
	- jQuery/Zepto
	- Selector Engines (Sizzle, Qwery, etc)
- Business Logic
	- Backbone Views + Controllers
		- Marionette
		- Chaplin
		- Etc
	- Spine Controller
	- Ember/Angular
	- MiniView
- Data Logic
	- Backbone Models
	- Ember/Angular Models
- Templating
	- Handlebars
	- ECT/Eco
	- Facebook React
	- Knockout
	- Pointers
	- Vanilla jQuery
- Server Side Communication
	- Backbone Sync
	- Angular/Ember Data
	- Web Sockets
	- jQuery AJAX
- Routing / State Management
	- PJAX
	- History.js
	- Backbone/Spine/MVC Router
	- Crossroads (Microjs)


## Bevry's Architecture

- Building
	- DocPad + LiveReload

	``` bash
	npm install -g docpad
	mkdir myapp; cd myapp
	docpad run
	docpad install livereload
	```

- Pre-Processors
	- CoffeeScript
	- CoffeeKup
	- Stylus

	``` bash
	docpad install coffeescript coffeekup stylus
	```

- Packaging
	- NPM + Browserify
	
	``` bash
	npm install --save browserify safeps
	open "https://github.com/webwrite/inlinegui/blob/4676a090365ef15c5479e3b92e1e2250255a9176/docpad.coffee#L110-L143"
	```

- DOM
	- jQuery/Zepto

	``` bash
	open "https://github.com/webwrite/inlinegui/blob/4676a090365ef15c5479e3b92e1e2250255a9176/docpad.coffee#L51-L52"
	```

	``` coffeescript
	$ = window.$
	```

- Business Logic
	- MiniView

	``` bash
	npm install --save miniview
	```

	``` coffeescript
	MiniView = require('miniview').View
	```

- Data Logic
	- Lodash Backbone + QueryEngine
	
	``` bash
	npm install --save query-engine
	open "https://github.com/webwrite/inlinegui/blob/4676a090365ef15c5479e3b92e1e2250255a9176/docpad.coffee#L54-L58"
	```

	``` coffeescript
	class Model extends require('backbone').Model

	class Collection ends require('query-engine').QueryCollection
	```

- Templating
	- Pointers

	``` bash
	npm install --save pointers
	open "https://github.com/bevry/pointers#usage"
	```

- Server Side Communication
	- jQuery AJAX then to Primus

	``` bash
	open "https://github.com/webwrite/inlinegui/blob/4676a090365ef15c5479e3b92e1e2250255a9176/src/documents/scripts/models/file.js.coffee#L36-L59"
	```

- Routing
	- Spine Route

	``` bash
	npm install --save spine-route
	open "https://github.com/bevry/spine-route#usage"
	```
