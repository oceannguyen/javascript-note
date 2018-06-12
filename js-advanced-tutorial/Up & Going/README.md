## Coercion

Có 2 dạng *Coercion*: explicit và implicit

### Equality

There are four equality operators: ```==```, ```===```, ```!=```, and ```!==```

The difference between ```==``` and ```===``` is usually characterized that ```==``` checks for value equality and ```===``` checks for both value and type equality. However, this is inaccurate. The proper way to characterize them is that ```==``` checks for value equality with coercion allowed, and ```===``` checks for value equality without allowing coercion; ```===``` is often called "strict equality" for this reason.

```javascript
var a = "42";
var b = 42;

a == b;			// true
a === b;		// false
```

whether to use ```==``` or ```===``` in various situations, here are my simple rules:

- If either value (aka side) in a comparison could be the true or false value, avoid ```==``` and use ```===```.
- If either value in a comparison could be of these specific values (```0```, ```""```, or ```[]``` -- empty array), avoid == and use ```===```.
- In all other cases, you're safe to use ```==```. Not only is it safe, but in many cases it simplifies your code in a way that improves readability

## Function Scopes

### Hoisting

Wherever a var appears inside a scope, that declaration is taken to belong to the entire scope and accessible everywhere throughout.

When a var declaration is conceptually "moved" to the top of its enclosing scope.

```javascript
var a = 2;

foo();					// works because `foo()`
						// declaration is "hoisted"

function foo() {
	a = 3;

	console.log( a );	// 3

	var a;				// declaration is "hoisted"
						// to the top of `foo()`
}

console.log( a );	// 2
```

In addition to creating declarations for variables at the function level, ES6 lets you declare variables to belong to individual blocks (pairs of { .. }), using the ```let``` keyword

# Strict Mode

ES5 added a "strict mode" to the language, which tightens the rules for certain behaviors. Generally, these restrictions are seen as keeping the code to a safer and more appropriate set of guidelines.

```javascript
function foo() {
	"use strict";

	// this code is strict mode

	function bar() {
		// this code is strict mode
	}
}

// this code is not strict mode
```
Compare that to:

```javascript
"use strict";

function foo() {
	// this code is strict mode

	function bar() {
		// this code is strict mode
	}
}

// this code is strict mode
```
# Functions As Values

## Immediately Invoked Function Expressions (IIFEs)

There's another way to execute a function expression, which is typically referred to as an immediately invoked function expression (IIFE):

```javascript
(function IIFE(){
	console.log( "Hello!" );
})();
// "Hello!"
```
IIFEs can also have return values:

```javascript
var x = (function IIFE(){
	return 42;
})();

x;	// 42
```

## Closure

You can think of closure as a way to "remember" and continue to access a function's scope (its variables) even once the function has finished running.

Consider:

```javascript
function makeAdder(x) {
	// parameter `x` is an inner variable

	// inner function `add()` uses `x`, so
	// it has a "closure" over it
	function add(y) {
		return y + x;
	};

	return add;
}
```

The reference to the inner ```add(..)``` function that gets returned with each call to the outer ```makeAdder(..)``` is able to remember whatever ```x``` value was passed in to ```makeAdder(..)```. Now, let's use ```makeAdder(..)```:

```javascript
// `plusOne` gets a reference to the inner `add(..)`
// function with closure over the `x` parameter of
// the outer `makeAdder(..)`
var plusOne = makeAdder( 1 );

// `plusTen` gets a reference to the inner `add(..)`
// function with closure over the `x` parameter of
// the outer `makeAdder(..)`
var plusTen = makeAdder( 10 );

plusOne( 3 );		// 4  <-- 1 + 3
plusOne( 41 );		// 42 <-- 1 + 41

plusTen( 13 );		// 23 <-- 10 + 13
```
### Module

The most common usage of closure in JavaScript is the module pattern. Modules let you define private implementation details (variables, functions) that are hidden from the outside world, as well as a public API that is accessible from the outside.

Consider:

```javascript
function User(){
	var username, password;

	function doLogin(user,pw) {
		username = user;
		password = pw;

		// do the rest of the login work
	}

	var publicAPI = {
		login: doLogin
	};

	return publicAPI;
}

// create a `User` module instance
var fred = User();

fred.login( "fred", "12Battery34!" );
```

# ```this``` Identifier

If a function has a ```this``` reference inside it, that this reference usually points to an ```object```. But which ```object``` it points to depends on how the function was called.

```javascript
function foo() {
	console.log( this.bar );
}

var bar = "global";

var obj1 = {
	bar: "obj1",
	foo: foo
};

var obj2 = {
	bar: "obj2"
};

// --------

foo();				// "global"
obj1.foo();			// "obj1"
foo.call( obj2 );		// "obj2"
new foo();			// undefined
```

# Prototypes

When you reference a property on an object, if that property doesn't exist, JavaScript will automatically use that object's internal prototype reference to find another object to look for the property on.

```javascript
var foo = {
	a: 42
};

// create `bar` and link it to `foo`
var bar = Object.create( foo );

bar.b = "hello world";

bar.b;		// "hello world"
bar.a;		// 42 <-- delegated to `foo`
```
The ```a``` property doesn't actually exist on the ```bar``` object, but because ```bar``` is prototype-linked to ```foo```, JavaScript automatically falls back to looking for ```a``` on the ```foo``` object, where it's found.