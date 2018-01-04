# kchoo
JS-based language with strict, static typing (for learning about compilers)

## Differences between kchoo and JS

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
Hash (name subject to change)
Function

// Maybes
Class
Interface
BigInt
Decimal
```

### Immutability

Variables are immutable by default, use `let` to enable mutability

```
int i = 0;

while (i != 10) {
	...
	// compiler error
	i = i + 1;
}

let int j = 0;

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
* Backticks ````` for strings that are interpolated

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

### Importing 

Import statements will have a few different forms: (very tentative)

```
import
	from './OtherClass': OtherClass
	from './Functions': function string coolFunction as f
	from './Constants': *
```

### Standard Library

Very tentative

Unlike JS, where everything is global, you'll need to import those classes/namespaces

```
import
	from 'Math': double E as exp
```