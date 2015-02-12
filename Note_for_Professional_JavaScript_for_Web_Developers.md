# Note for Professional JavaScript for Web Developers


## Syntax

### Case-sensitivity


###Identifiers
* The first character must be a letter, an underscore (_), or a dollar sign ($).
* All other letters may be a letter, an underscore, a dollar sign, and numbers.
* User camel case for identifiers


### Comments
    // single line comment


    /*
     * multi-line comments
     */


### Strict Mode
Strict mode changes many parts of how JavaScript is executed.

* put "use strict"; on top of js file to trigger strict mode of browser

        function doSomething() {
        	"use strict";
        	//function body
        }


### Statements
Statements that are terminated by semicolon is preferred as best practise of coding.

    var diff = a- b;  //valid and preferred

User code block in control statement such as _if_ is also preferred

    if (test) {
    test = false;
    alert(test);
    }


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

    var message = "some string";
    alert(typeof message);
    alert(typeof(message));
    alert(type of 95);


### The Undefined type
When a variable is declared by not initialized, it is assigned the value of _undefined_.


### The Null type
When defining a variable that is meant to later hold an object, it is advisable to initialize it to _null_.

The value _undefined_ is a derivative of _null_, they are defined to be superficially equal as follow:

    alert(null == undefined);  //return true


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

        var intNum = 55;

* octal integer (base 8)

        var octalNum = 070;

* hexadecimal (base 16)

        var hexNum = 0xA;

#### Floating-Point values
Floating-point values uses twice as much memory as storing integer values.

    var floatNum1 = 1.1
    var floatNum2 = .1   //valid, but not recommended

E-notation is to have a number followed by an uppercase or lower case letter E, followed by the power of 10 to multiply by.

    var floatNum = 3.125e7  //equal to 31250000

Floating point values are accurate up to 17 decimal places.


#### Range of values
Number.MIN_VALUE stores the smallest number, which is 5e-324

Number.MAX_VALUE stores the largest number, which is 1.7976931348623157e+308


#### NaN
short for "Not a Number", it indicates a failed return number.

use isNaN() function to determine if a value is NaN.


#### Number Conversions
* Number().  Can be used on any data type.
  * Boolean, true ->1, false ->0
  * Number, simply pass through and returned
  * _null_ ->0
  * _undefined_ ->NaN
  * String,
    * If contains only number, converted to decimal number, with signed.  i.e "123" ->123
    * If contains valid floating point format, converted to floating point numeric value. i.e "1.1" ->1.1
    * If contains valid hexadecimal format, converted to integer that matahces the hex value
    * If empty, ->0
    * If others, ->NaN
  * Object,
    * call valueOf() and return value, if result is NaN, call toString()
* parseInt().  Specifically used for converting strings to numbers.
* parseFloat().  Specifically used for converting strings to numbers.


### The String type
Using double quotes or single quotes has no difference.

#### Character Literals
* \xnn   A character represented by hexadecimal code nn (where n is a hex digit 0-F).  Example \x41 equals 'A'
* \unnnn  A unicode character represented by hexdecimal code nnnn (where n is a hex digit 0-F).  Example \u03a3 equals to Greek symbol ∑.

Use _length_ property of a string to return its length

    alert(text.length);


#### The Nature of Strings


#### Converting to a String
* toString()
  * available on values that are numbers, Booleans, objects and strings.
  * when used on a number, toString() accepts argument of radix to output the number

            var num = 10;
            alert(num.toString());  //"10"
            alert(num.toString(2)); //"1010"
            alert(num.toString(8)); //"12"
            alert(num.toString(10)); //"10"
            alert(num.toString(16)); //"a"

* String()
  * if value has toString() method, call toString().
  * if _null_, ->"null".
  * if _undefined_, ->"undefinied".


### The Object type
Use _new_ to create object.

    var o = new Object();

Each object has the following properties:
* constructor
* hasOwnProperty(propertyName)
* isPrototypeOf(object)
* propertyIsEnumerable(propertyName)
* toLocaleString()
* toString()
* valueOf()


## Operators
* math operations
* bitwise operators
* relational operators
* equality operators

### Unary Operators
Operators that work on only one value

#### Increment(++)/Decrement(--)
Besides integers, the operator will convert strings, Booleans, floating-point values and object before apply the changes, by using the Number() method under the hood.


#### Unary Plus(+) and Minus(-)
The operator will convert nonnumeric value to number, using Number() method under the hood.


### Bitwise Operators
Operators works on bits of numbers.  It converted the 64-bit number to 32-bit integer then operated on it, then convert the result back to 64-bits.

The 32nd bit of a value is the signed of the value.

#### Bitwise NOT(~)
Returns the number's complement.


#### Bitwise AND(&)
Lines up the bits of each number, and using the following rules to perform operation between the two bits in the same position

BIT FROM FIRST NUMBER | BIT FROM SECOND NUMBER | RESULT
--|---|--
1 | 1 | 1
1 | 0 | 0
0 | 1 | 0
0 | 0 | 0


#### Bitwise OR(|)
Follow the following rules:

BIT FROM FIRST NUMBER | BIT FROM SECOND NUMBER | RESULT
--|---|--
1 | 1 | 1
1 | 0 | 1
0 | 1 | 1
0 | 0 | 0


#### Bitwise XOR(^)
Follow the following rules:

BIT FROM FIRST NUMBER | BIT FROM SECOND NUMBER | RESULT
--|---|--
1 | 1 | 0
1 | 0 | 1
0 | 1 | 1
0 | 0 | 0


#### Left Shift(<<)
Shift all bits to the left by the number given, and fill the empty bits with 0s.


#### Signed Rigth Shift(>>)
Shift all bits to the right while preserving the sign on 32nd bit, filled empty bits with 0s.


#### Unsigned Right Shift(>>>)
Shift all bits to the right, filled 0s on empty bits including the 32nd signed bit.


### Boolean Operators

#### Logical NOT(!)
Besides Boolean value, it converts the operand of other type to Boolean first and negates it.
* Object ->false
* empty string ->true
* nonempty string ->false
* 0 ->true
* any number other than 0 ->false
* _null_ ->true
* _undefined_ ->true

Two NOT operators (!!) can simulate the behavior of Boolean() method.


#### Logical AND(&&)
Follow the rules:

OPERAND 1 | OPERAND 2 | RESULT
-----|------|-----
true | true | true
true | false | false
false | true | false
false | false | false

Also:
* if the first operand is an object, return the second operand
* if the second operand is an object, it is returned only if the first operand is _true_
* if both operands are objects, return the second operand
* if either operand is _null_, return _null_
* if either operand is _NaN_, return _NaN_
* if either operand is _undefined_, return _undefined_

> __Short-circuited operations:__ if the first operand determines the result, the second operand is never evaluated.


#### Logical OR(||)
Follow the rules:

OPERAND 1 | OPERAND 2 | RESULT
-----|------|-----
true | true | true
true | false | true
false | true | true
false | false | false

If either operand is not a Boolean, it will:
* if the first operand is an object, the first operand is returned
* if the first operand evaluates to _false_, the second operand is returned
* if both operands are objects, the first operand is returned
* if both operands are _null_, _null_ is returned
* if both operands are _undefined_, _undefined_ is returned
* if both operands are _NaN_, _NaN_ is returned.

The logical OR is also short-circuited operator.


### Multiplicative Operators

#### Multiply(*)
* if either operand is _NaN_, the result is _NaN_
* if infinity is multiplied by 0, the result is _NaN_
* if either operand isn't a number, it is converted to number using Number() under the hood


#### Divid(/)
* if either operand is _NaN_, the result is _NaN_
* if infinity is divided by infinity, the result is _NaN_
* if 0 is divided by 0, the result is _NaN_
* if either operand isn't a number, it is converted to number using Number() under the hood


#### M0dulus(%)
* if infinity or -infinity is divided by a finite number, the result is _NaN_
* if the dividend is a finite number and divisor is 0, the result is _NaN_
* if infinity is divided by infinity, the result is _NaN_
* if either operand isn't a number, it is converted to number using Number() under the hood


### Additive Operators

#### Add(+)
* if either operand is string, the other operand is converted to a string, and the result is the concatenation of the two strings.
* if either operand is object, number or Boolean, its toString() method is called to get a string value, then the previous rules applied.
* For _undefined_ and _null_, String() method is called and the strings are concatenated.


#### Subtract(-)
* if either operand is a string, Boolean, _null_, _undefined_, it is converted to a number and the calculation continues.
* if either operand is an object, its valueOf() method is called.  If no valueOf() method is defined, toString() method is called, then the calculation continues.


### Relational Operators
* less-than(<)
* greater-than(>)
* less-than-or-equal-to(<=)
* greater-than-or-equal-to(>=)

Rules:
* if numbers, perform numeric comparison
* if strings, compare character codes of each corresponding character in the string
* if one is number, convert the other to a number, then compare
* if one is an object, call valueOf().  If valueOf() is not available, call toString().  Then apply the above rules
* if one is a Boolean, convert it to number and compare.


### Equality Operators

#### Equal(==) and Not Equal(!=)
Do conversions first:
* if one is Boolean, convert to a numeric number.
* if one is string and the other is a number, convert string to a number.
* if one is object and the other is not, convert object by valueOf() to a number.
* Values of _null_ and _undefined_ are equal.
* if either one is _NaN_, the equal operator return false, the not-equal operator return true.  If both are _NaN_, the equal operator returns false.
* if both are objects, compare and see if they are the same object.


#### Identically Equal(===) and Not Identically Equal(|==)
compare witout conversion


#### Conditional Operator

    valuable = boolean_expression ? true_value : false_value;


#### Assignment Operators(=)


#### Compount-assignment Operators
* Multiply/assign (*=)
* Divide/assign (/=)
* Modulus/assign (%=)
* Add/assign (+=)
* Subtract/assign (-=)
* Left shift/assign (<<=)
* Signed right shift/assign (>>=)
* Unsigned right shift/assign (>>>=)


### Comma Operator
Allow execution of more than one operation in a single statement.


## Statements

### The _if_ statement

    if (condition) statement1; else statement2;

    if (condition1) {
      statement1;
    } else if (condition2) {
      statement2;
    } else {
      statement3;
    }


### The _do-while_ statement

    do {
      statement
    } while (expression);


### The _while_ statement

    while (expression) {
      statement;
    }


### The _for_ statement

    for (var num=initial_value; expression; post-loop-expression) {
      statement;
    }


### The _for-in_ statement

    for (property in expression) {
      statement
    }


### Labeled statement

    label: statement;


### The _break_ and _continue_ statement
* break: exit loop immediately, forcing execution to continue with the next statement.
* continue: exit loop immediately but execution continues from the top of the loop.


### The _with_ statement
Set scope of the code within a particular object.

    with (expression) statement;

> Not recommend to use with statement.


### The _switch_ statement

    switch (expression) {
      case value1: statement
        break;
      case value2: statement
        break;
      case value3: statement
        break;
      case value4: statement
        break;
      default: statement
    }

> No type coercion occurs


## Functions

    function functionName(arg0, arg1, ..., argN) {
      statements;
    }

Note:
* no need to specify a function to return a value or not;
* stop executing and exits immediately whenever encounters the _return_ statement;
* _return_ can be used without specifying a value behind;
* no function ca be named _eval_ or _arguments_;
* no parameters can be named _eval_ or _arguments_;
* no two parameters can have the same name.

### Arguments
* A ECMAScript function don't care how many arguments are passed in, nor does it care about the data type of them.
* Arguments in ECMAScript are represented as an array _arguments_.  Indivisual argument can be accessed by arugments[0] or arguments[n].
* Number of arguments can be checked by _arguments.length.
* Any named argument that is not passed into the function is assigned _undefined_ automatically.
* Under strict mode, if there's argument not assigned a value, error will be throwed.


### No Overloading
If two functions has the same name the the last function becomes the owner.

However, inside the function you can simulate the overloading by checking type and number of arguments that have been passing into a function.  Detail information can be found on this [SO thread](http://stackoverflow.com/questions/10855908/how-to-overload-functions-in-javascript)



## Premitive and Reference Value
*Primitive variable:* Undefined, Null, Boolean, Number, and String.
*Reference variable:* Objects


### Dynamic Properties
* Reference value can add, change or delete properties and method at any time.
* Primtive values cannot.


### Copying Values
* When copied, value of a primative variable is copied into the newly created variable.
* When copied, value of a reference variable, which is a pointer to an object, is copied into the other variable, so both variable points to the same object.


### Argument Passing
All function arguments are passed by value, which is passed into a local variable from outside.