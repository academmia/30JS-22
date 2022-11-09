#
## In JavaScript, a __primitive__ is data that is not an object and has no methods or properties

#

- ### string
- ### number
- ### bigint
- ### boolean
- ### undefined
- ### symbol
- ### null

#

## Primitives have no methods but still behave as if they do

#

- ### A string is a sequence of characters used to represent text.

- ### A String is one of the primitive values and the String object is a wrapper around a String primitive.

#

- ### Number is a numeric data type in floating point format

- ### In other programming languages different numeric types exist; for example, Integers, Floats, Doubles, or Bignums.

#

- ### BigInt is a numeric data type that can represent integers in the arbitrary precision format 
    - also called _infinite-precision arithmetic_, indicates that calculations are performed on numbers whose digits of precision are limited only by the available memory of the host system
    - created by appending n to the end of an integer literal

```js
const bigIntNumber = 2001196253540289n

const alsoHuge = BigInt(2001196253540289)
// 2001196253540289n
```

#

- ### a Boolean is a logical data type that can have only the values true or false

#

- ### a ___null___ value represents a reference that points, generally intentionally, to a nonexistent or invalid object or address

#

- ### ___undefined___ is a primitive value automatically assigned to variables that have just been declared, or to formal arguments for which there are no actual arguments.

#

- ### Symbol is a built-in object whose constructor returns a symbol primitive — also called a Symbol value or just a Symbol — that's guaranteed to be unique

- ### Symbols are often used to add unique property keys to an object that won't collide with keys any other code might add to the object

- ### Every Symbol() call is guaranteed to return a unique Symbol.

- `Symbol('foo') === Symbol('foo')  // false`


#

## [Primitive Symbol - article](https://academmia.ro/blog/javascript/es6-iterators-iterables-and-symbol-data-type/)

