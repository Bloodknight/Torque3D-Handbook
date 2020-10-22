# Operations 
Operators in TorqueScript behave very similarly to operators in real world math and other programming languages. You should recognize quite a few of these from math classes you took in school, but with small syntactical changes. The rest of this section will explain the syntax and show a brief example, but we will cover these in depth in later guides.  

## Arithmetic Operations
Basic math operations are supported using a syntax clear to everyone. TorqueScript supports multiplication, division, modulo, addition, and subtraction. Additionally, standard auto-increment and auto-decrement operations are available:

**Example**:
```cs
// Multiplication
%product = 3*4; // results in 12

// Division
%quotient = 4/2; // results in 2

// Modulo
%mod = 5%2; // results in 1

// Addition
%sum = 3+4; // results in 7

// Subtraction
%difference = 4-3; // results in 1

// Auto-increment
%value = 3;
%incr = %value++; // results in 4;

//Auto-decrement
%value = 3;
%decre = %value--; // results in 2;
```



## Relational Operations
Relational operators are used for comparing values and variables against each other. Again, the syntax for these operatations closely resemble real world math. The value returned from a comparison will always be true(1) or false(0).

**Example**:
```cs
// Greater than
if(4 > 3)
   echo("True. 3 is not greater than 4");

// Greater than or equal to
if(3 >= 3)
   echo("True. 3 is equal to or greater than 3");

// Equal to
if(6 == 6);
   echo("True. 6 is exactly equal to 6");
   
// Not equal to
if(3 != 5)
   echo("True. 3 is not equal to 5");
```

## Bitwise Operations
Bitwise operations are used for comparing and shifting the bits of a value.

**Examples**:
```cs
// Bitwise NOT/complement. Unary operation that flips bits.
%value = 101;
%bitValue = ~%value; // results in 101 becoming 010

// Bitwise AND. When applied to two binary values, resulting bits are 1 if original pairs were 1
%valueOne = 0101;
%valueTwo = 0011;
%bitValue = %valueOne&%valueTwo; // Results in 0001
```

## Assignment Operations
Assignment operators are used for setting the value of a variable. You should recognize it as the "equals" sign.

**Example**: 
```cs
%val = 3; // Assigns the value of 3 to the %val variable

%val = 3+4; // Assigns the value of 3+4 to the %val variable

%val += 3; // Assigns the %val variable the value of 3 plus itself
```

## String Operations
There are special values you can use to concatenate strings and variables. Concatenation refers to the joining of multiple values into a single variable. The following is the basic syntax:

 "string 1" operation "string 2"
You can use string operators similarly to how you use mathematical operators (=, +, -, *). You have four operators at your disposal: @ NL TAB SPC. For example, the @ symbol will concatenate two strings together exactly how you specify, without adding any additional whitespace.

**Example**: 
```cs
%newString = "Hello" @ "World";
echo(%newString);

// OUPUT: HelloWorld
```


