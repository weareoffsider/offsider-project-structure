# Offsider Project Structure

Offsider is the business entity of [Weekends](http://weekends.ws). This is how we set up projects.  

## General Structure

```
/tasks
	/scripts.js
	/styles.js
/build
/assets
/cl
/scripts
/front-end
	/main.less
	/main.js
	/componentLibrary.js
	/componentLibrary.less
	/ui
		/_ = reusable mixin/extends/placeholder-styles, things that don’t match atoms, these classnames should never be used in markup, css only
		/config
			/palette.less
			/layers.less
			/breakpoints.less
			/spacing.less
		/base = base elements (a, ul, li, etc)
		/atoms = heavy api, small in scope, cannot standalone in a template, unset width
		/molecules = uses atoms to form a small visual component, only set witdth if required for execution, ideally let template restrict a molecule
		/layouts = use molecules and containers to allow a template to extend
		/templates = final rendition of a page using data + layouts + molecules
	/logic = app specific, there be dragons here
/server
/view-layer
/provisioning
	/development
	/deploy
```

## UI Components
```
/Component
	/Component.react.js / ts
	/Component.data.js / ts
	/Component.less
	/SubComponent.react.js
	/SubComponent.less
	/Component.test.png
	/Component.test.js
```


## Misc Notes
- US spelling in file names; e.g., "color" not "colour". I know it hurts. 
- Contexts (e.g., richtext*) are likely to be molecules (if not templates or layouts)
