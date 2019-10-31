# H2JS Element Class

A simple javascript class for creating self contained, reusable, ui elements.


#### Custom DOM elements as easy as vanilla javascript objects.
* **Reusable components** -- *as simple as an import*.
* **Styling encapsulation** -- *use css without concern for the global scope*.
* **Complex UI elements** -- *UI elements can contain UI elements*.
* **Flexible** -- *elements can be used on their own or with other frameworks*.


-------------------
### Basic Usage
```sh
$ npm i -S h2js-element
```

index.html
```js
<script type='module'>
	import Clock from './clock-element.js'
	
	let i = new Clock('green')
	document.querySelector('body').appendChild(i.element)
</script>
```
&nbsp;



clock-element.js
```js
import ElementClass from 'h2js-element'

class ClockElement extends ElementClass{

	constructor(faceColor){
		faceColor = faceColor || 'white'
	
		let C = `
			<style>
				.item {color: ${faceColor};}
			</style>
			<div class='display'></div>
			`
		super('clock',C)
		this.shadow.querySelector('.display').textContent = new Date()
		}
	}

export default ClockElement
```

