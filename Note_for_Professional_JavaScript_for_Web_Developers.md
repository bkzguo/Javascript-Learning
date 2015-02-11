# Note for Professional JavaScript for Web Developers


## Syntax

### Case-sensitivity


###Identifiers
* The first character must be a letter, an underscore (_), or a dollar sign ($).
* All other letters may be a letter, an underscore, a dollar sign, and numbers.
* User camel case for identifiers


### Comments
> // single line comment

> /*
> * multi-line comments
> */


### Strict Mode
Strict mode changes many parts of how JavaScript is executed.

* put "use strict"; on top of js file to trigger strict mode of browser
> function doSomething() {
> 	"use strict";
> 	//function body
> }


### Statements
Statements that are terminated by semicolon is preferred as best practise of coding.
> var diff = a- b;  //valid and preferred

User code block in control statement such as _if_ is also preferred
> if (test) {
> test = false;
> alert(test);
> }


## Keywords and Reserved Words
Know the difference of keywords and reserved words.


## Variables
A variable can hold any type of data.

It is not recommended to swtich data type that a variable contains.  However it is valid in ECMAScript.

Use _var_ operator to define local variable of a scope.

Omitting _var_ operator to make a variable becomes global.  But it is not recommended.  Strict mode throws a _ReferenceError when an undeclared variable is assigned a value.


## Data Types
* Undefined
* Null
* Boolean
* Number
* String
* Object

### The typeof operator
Use the operator provides datatype of a variable
> var message = "some string";
> alert(typeof message);
> alert(typeof(message));
> alert(type of 95);


### The Undefined type
When a variable is declared by not initialized, it is assigned the value of _undefined_.


### The Null type
When defining a variable that is meant to later hold an object, it is advisable to initialize it to _null_.

The value _undefined_ is a derivative of _null_, they are defined to be superficially equal as follow:
> alert(null == undefined);  //return true


### The Boolean type
true or false.

Al types of value have Boolean equivalents in ECMAScript.  To convert a value into its Boolean equivalent, use _Boolean()_ function.

DATA TYPE | VALUES CONVERTED TO TRUE | VALUES CONVERTED TO FALSE
----------|--------------------------|--------------------------
Boolean | true | false
String | Any nonempty string | ""(empty string)
Number | Any nonzero number, including infinity | 0, NaN
Object | Any object | null
Undefined | n/a | undefined


### The Number type
* decimal integer
> var intNum = 55;
* octal integer (base 8)
> var octalNum = 070;
* hexadecimal (base 16)
> var hexNum = 0xA;

#### Floating-Point values
Floating-point values uses twice as much memory as storing integer values.
> var floatNum1 = 1.1
> var floatNum2 = .1   //valid, but not recommended

E-notation is to have a number followed by an uppercase or lower case letter E, followed by the power of 10 to multiply by.
> var floatNum = 3.125e7  //equal to 31250000

Floating point values are accurate up to 17 decimal places.


#### Range of values
Number.MIN_VALUE stores the smallest number, which is 5e-324

Number.MAX_VALUE stores the largest number, which is 1.7976931348623157e+308


#### NaN
short for "Not a Number", it indicates a failed return number.

use isNaN() function to determine if a value is NaN.


#### Number Conversions
* Number().  Can be used on any data type.
* parseInt().  Specifically used for converting strings to numbers.
* parseFloat().  Specifically used for converting strings to numbers.


### The String type
Using double quotes or single quotes has no difference.

#### Character Literals
* \xnn   A character represented by hexadecimal code nn (where n is a hex digit 0-F).  Example \x41 equals 'A'
* \unnnn  A unicode character represented by hexdecimal code nnnn (where n is a hex digit 0-F).  Example \u03a3 equals to Greek symbol ∑.

Use _length_ property of a string to return its length
> alert(text.length);


#### The Nature of Strings


#### Converting to a String
* toString()
  * available on values that are numbers, Booleans, objects and strings.
  * when used on a number, toString() accepts argument of radix to output the number
  	> var num = 10;
  	> alert(num.toString());  //"10"
  	> alert(num.toString(2)); //"1010"
  	> alert(num.toString(8)); //"12"
  	> alert(num.toString(10)); //"10"
  	> alert(num.toString(16)); //"a"
* String()
  * available for _null_ and _undefined_.
  * if a value is _null_, "null" is returned.
  * if a value is _undefined_, "undefinied" is returned.


### The Object type
Use _new_ to create object.
> var o = new Object();

Each object has the following properties:
* constructor
* hasOwnProperty(propertyName)
* isPrototypeOf(object)
* propertyIsEnumerable(propertyName)
* toLocaleString()
* toString()
* valueOf()