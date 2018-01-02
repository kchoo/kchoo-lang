# kchoo-lang
JS-based language with strict, static typing (for learning about compilers)

## Differences between kchoo and JS

### Static Typing

The most glaring difference is the presence of strict types. The type of a variable **must** be specified if it cannot be unambiguously determined at compile time.

Some examples for primitives:

```
// uninstantiated, so type needed
int i;

// integral values default to int
j = 0;

// non-integral values default to float
x = 1.7;

// must be explicit about double
double y = 8.2;
```

Classes are a more complex, so much so that I'm thinking about scrapping implicit types because of it

```
// borrowing some classes from C# for this example

// case 1: function returns interface

// a is of type iEnumerable here
a = someFunctionThatReturnsEnumerable();

// case 2: function returns concrete class

// a is of type List here
a = someFunctionThatReturnsList();

// a is of type iEnumerable here
iEnumerable a = someFunctionThatReturnsList();
```

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
Hash (subject to change)
Function
Class (maybe?)
```

### Immutability

Variables are immutable by default, use `let` to enable mutability

```
i = 0;

while (i != 10) {
	...
	// compiler error
	i = i + 1;
}

let j = 0;

while (j != 10) {
	...
	// this is fine
	j = j + 1;
}
```
