---
tags:
  - JS
---
# What is `this` keyword?
> The **`this`** keyword refers to ==the context where a piece of code==, such as a function's body, is ==supposed to run==. - MDN Docs
# The Value of `this`
- Depends on invocation, [[Runtime Binding]]
	- Object method -> value is the object itself
	- Standalone function -> global object or undefined (strict mode)
	- Arrow Functions -> Their parent scope
## Strict vs Non Strict
```javascript
"use strict";
function testingThis() {
	console.log(this); // undefined
}
```
- What is [[Javascript Script Mode, and Why its a thing?]]
```javascript
function testingThis() {
	console.log(this); // window object
}
```
## Object Method
```javascript
 const Person = {
        name: "John",
        age: 30,
        greet: function () {
          console.log(this.name); // John
          console.log(this.age); // 30
          
        },
      };
```
### Binding with Function.Prototype.bind()?
- `Function.Prototype.bind` Can be used to **bind a function's this keyword's value** with provided value
```javascript
function myFunction() {
	console.log(this.name);
}

let newFunction = myFunction.bind({
	name: "John",
});


myFunction(); // window.name
newFunction(); // name 
```
## Arrow Functions
`this` in arrow function are binded to what it parent scope was at the time of ==definition==.
### Invoking from global scope
```javascript
const arrowFunction = () => {
	console.log(this)
}

arrowFunction(); // Prints the window object
```

```javascript
function functionWArrow() {
	const arrowFunction = () => {
		console.log(this);
	};
	arrowFunction();
}

functionWArrow();
```
- `arrowFunction` is defined within `functionWArrow`. Since `functionWArrow` is likely ==called in the ==global scope and it's not within another function or object, the `this` inside `arrowFunction` will refer to the global object (which is typically the `window` object in browsers). 
- We can bind this using `bind()` to any other object to get different results for `this`. 
- 

### Invokign
# References
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/this