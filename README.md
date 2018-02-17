# kchoo

`kchoo` is a JS-based language with strict, static typing (for learning about compilers)

### Static Typing

The most glaring difference is the presence of strict types. The type of a variable must be specified (this is subject to change with an `auto` type or similar)

Not-set-in-stone comprehensive list of primitives (and their aliases)

```
boolean

int8
int16
int32 (int)
int64

uint8
uint16
uint32 (uint)
uint64

float
double
```

Types in the standard library

```
String
Array
Hash (name subject to change, Map? Dict(ionary)?)
Function
Promise

// Maybes
Class
Interface
BigInt
Decimal
```

### Immutability

Variables are immutable by default, use `mutable` to enable mutability

```
int i = 0;

while (i != 10) {
	...
	// compiler error
	i = i + 1;
}

mutable int j = 0;

while (j != 10) {
	...
	// this is fine
	j = j + 1;
}
```

### Functions

Functions will work the same way as normal JS functions (without fat arrow context weirdness), but with type signatures

```
function int sum2(int a) {
	return 2 * a;
}

function int g = f;

[1, 2, 3].map(g);
```

### Strings

Two different delimiters:

* Single quotes `'` for static, literal strings
* Backticks `` for strings that are interpolated

Using the wrong type of delimiter is a syntax error.

```
// Yes
string s = 'Hello, world';

// No
string s = 'Hello, ${`world`}';

// Yes
string s = `Hello, ${'world'}`;

// No
string s = `Hello, world`;
```

### Modules 

Modules will work the same way as ES6 modules will (http://exploringjs.com/es6/ch_modules.html)

### Standard Library

You'll have to import stuff from the standard library, very little will be available by default (just types for right now)

Parts of the standard library:

```
// from JS
Math

// from node standard library
fs
http
```

### Generics

We have types, so we should have generics. I'll try to keep things as close to JS as possible (e.g. `[1, 2, 3]` will be interpreted as an `int32[]`), but some things will need to use the standard angle bracket syntax (e.g. `Queue<T>`)

### Exceptions

Taking a leaf out of the books of Rust and Haskell, there won't be typical `Error`s with `try`/`catch` blocks. Instead, any function that `throws new Error();` will require a return type of `Option<T>`. More on unwrapping `Option`s later (there will be probably be some kind of pattern matching features, TBD)

### TODO

I'm going to take a look at some code I wrote recently (maybe the media-aggregator) and "port" it to `kchoo`. That will help me hash out the specifics of the language and determine what I'd like and what I should drop.
