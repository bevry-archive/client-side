# Bevry's Client Side Approach

## Available Architectures

- Building
	- Task based build tools
		- [Make](http://en.wikipedia.org/wiki/Make_(software)
			- Not friendly to web developers
		- [Ant](http://en.wikipedia.org/wiki/Ant_(software)
			- Make + XML configuration file
		- [Grunt](http://gruntjs.com/)
			- Make in javascript + JSON configuration file
		- [Brunch](http://brunch.io/)
			- Grunt in coffeescript
		- [Cake](http://coffeescript.org/#cake)
			- Make in coffeescript
	- Resource based build tools
		- [DocPad](http://docpad.org)
			- Next generation web architecture

- PreProcessors
	- HTML
		- [jQuery Smarty](http://balupton.github.io/jquery-smarty/demo/), [Jade](http://jade-lang.com/), [Handlebars](http://handlebarsjs.com/)
			- [Did people forget about no smarty?](https://web.archive.org/web/20101129144816/http://www.nosmarty.net/)
			- Don't created a new interpreted syntax to stop templating errors
			- Just use a common better language, run tests, and train your developers
		- [Eco](https://github.com/sstephenson/eco)
			- Like erb, and phtml, but with coffeescript
		- [CoffeeKup](http://coffeekup.org/)
			- All coffeescript
	- JavaScript
		- [CoffeeScript](http://coffeescript.org/)
			- Expressive
		- [LiveScript](http://www.typescriptlang.org/)
			- Safe
		- [ClojureScript](http://himera.herokuapp.com/synonym.html)
			- Functional
	- CSS
		- [LessCSS](http://lesscss.org/)
			- JavaScript
		- [Stylus](http://learnboost.github.io/stylus/)
			- Like LessCSS + Expressive
		- [SASS](http://sass-lang.com/)
			- Ruby

- Packaging
	- [Bower](http://bower.io/)
		- Clones out git repositories, either add your built files to the repo, or get bower to build it after clone
	- [Component](https://github.com/component/component)
		- Clones out git repositories, add your built files to the repo
	- [NPM](http://npmjs.org/) / [Browerserify](http://browserify.org/) / [Ender](http://ender.jit.su/)
		- Publish your built files to the NPM registry, bundle them with browserify or ender

- DOM
	- [jQuery](http://jquery.com/)/[Zepto](http://zeptojs.com/)
	- [MicroJS Selector Engines](http://microjs.com/#selector) (Sizzle, Qwery, etc)

- Business Logic
	- [Backbone](http://backbonejs.org/) Views + Controllers, [Marionette](http://marionettejs.com/), [Chaplin](http://chaplinjs.org/)
	- [Spine](http://spinejs.com/) Controller
	- [Ember](http://emberjs.com/)/[Angular](http://angularjs.org/)
	- [MiniView](https://github.com/bevry/miniview)

- Data Logic
	- [Backbone](http://backbonejs.org/) Models
	- [Ember](http://emberjs.com/)/[Angular](http://angularjs.org/) Models

- Templating
	- Jade/Handlebars/Etc
		- Write your template in a special markup, only to re-render all of it on a minor change
	- ECT/Eco
		- Write your template in a familiar markup, only to re-render all of it on a minor change
	- [Facebook React](http://facebook.github.io/react/), [Knockout](http://knockoutjs.com/)
		- Write your template in a special markup, to pollute the rendered dom, so minor changes are handled fast
	- Vanilla jQuery
		- Write your template in normal markup, and write a lot of custom javascript, so minor changes are handled fast
	- [Pointers](https://github.com/bevry/pointers)
		- Write your template in normal markup, and write minimal code, so minor changes are handled fast

- Server Side Communication
	- [Backbone Sync](http://backbonejs.org/#Sync)
	- Angular/Ember Data
	- Web Sockets
	- jQuery AJAX

- Routing / State Management
	- [PJAX](https://github.com/defunkt/jquery-pjax)
	- [History.js](https://github.com/browserstate/history.js)
	- Backbone/Spine/MVC Router
	- [MicroJS Routers](http://microjs.com/#route) (Crossroads)


## Bevry's Architecture

[WebWrite InlineGUI](https://github.com/webwrite/inlinegui)

- Building
	- [Bevry's Base Cake](https://github.com/bevry/base/blob/master/Cakefile) + [DocPad's HTML5 Boilerplate Skeleton](https://github.com/docpad/html5-boilerplate.docpad) + [DocPad LiveReload Plugin](http://docpad.org/p/livereload)

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
	- Backbone's Model + QueryEngine's QueryCollection
	
	``` bash
	npm install --save query-engine
	open "https://github.com/webwrite/inlinegui/blob/4676a090365ef15c5479e3b92e1e2250255a9176/docpad.coffee#L54-L58"
	```

	``` coffeescript
	class Model extends require('backbone').Model

	class Collection extends require('query-engine').QueryCollection
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
	open "https://github.com/webwrite/inlinegui/blob/4676a090365ef15c5479e3b92e1e2250255a9176/src/documents/scripts/views/app.js.coffee#L353-L393"
	```

- Routing
	- Spine Route

	``` bash
	npm install --save spine-route
	open "https://github.com/bevry/spine-route#usage"
	```
