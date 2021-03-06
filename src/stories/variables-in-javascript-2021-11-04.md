---
title: Variables in JavaScript
shortDesc: " Variables are used to store data values. They are essential ideas
  in every programming language."
badge: JavaScript
author: Jimmy Emem Obot
authorImage: /assets/images/edet.jpg
authorBio: Jimmy Emem Obot is a Certified Graduate of Accountancy from the
  University of Nigeria, Nsukka. A Front-end Developer, who is excellent in
  implementing responsive websites. An Agile Trainee, Technical writer and a
  Scrum Master Certified.
timeRead: 5 min
date: 2021-11-04T12:01:11.460Z
tags:
  - post
  - today
image: /assets/images/photo-1-.jpg
imageAlt: "JavaScript "
---
### Introduction

 Variable simply means a quantity capable of assuming any of a set of values. A variable can be one data type and be changed later to another data type.

Variable can either be local or global. If a variable is used within a block or can be accessed with a specific part of the program, it is called a **local variable** because it can only be accessed within that block structure. **Global variables** can be accessed everywhere within the program. 

In this article, I'll be writing more on variables. How to name, assign, declare, reassign variables, and more about it.

* [Introduction](#introduction)
* [Naming a variable](#naming-a-variable)
* [Reserved names](#reserved-names)
* [Declaring a variable](#declaring-a-variable)
* [Assigning a variable](#assigning-a-variable)
* [Data types](#data-types)
* [Reassigning variables](#reassigning-variables)
* [Arithmetic operators](#arithmetic-operators)
* [Summary](summary)
* [Further reading](#further-reading)

### Naming a variable

Variable names are case-sensitive:  An uppercase and a lower-case character aren't the same. Here is an example; `$firstname`, `$FIRSTNAME`, and  `$firstName`  are different. 

A variable name cannot contain spaces. If it is more than a word, we can use an underscore "_".  For example, the variable `$Year 2021` is not correct, rather use `$Year2021` or  `$Year_2021`
Variable names should only include numbers (9,50,4,2021), letters (Year, age, etc.), dollar sign ($), or underscore.  

Select a variable name in a way that defines the character. For example, a variable that holds a car value might be named **$Toyota**.
Don't use the variable name with just a single character, use more than one word to name variables. 

### Reserved names

There are some words in JavaScript, that cannot be used as variables, labels, or function names. The usage of these phrases causes errors (bugs) when loading the script. As a developer, is important you know these words. Some examples of the words are;

***null, package, private, protected, public, return, char, boolean, byte
, abstract, case, const, argument, do, catch, break, char, else, enum
,float, for, function, goto, instanceof, if, new, static, this, in, delete
, fault, debugger, default, switch, this, public, short, synchronized, class
, implement, interface, volatile, import, void, final, throw, transient, and with*** 

### Declaring a variable

To declare a variable means to create the variable. We can declare a variable with either:  ***var, let, or const***.
Examples of declaring variable;

* `var a;` 
* `var car;`
* `var name;`

These are undefined variables that are declared but not assigned.

**VAR**: Var is a global variable; we can reassign and redeclare a variable when using "var". All values can be assigned using var.
var A = string;
var B = boolean;
var C = number

**LET**: You can redeclare a variable defined with let and it is restricted to scope it's declared.
Examples;

`let a;`

`let a = 2;`

`let a, b, c;`

`let a = 2, b = 20, c = 10;` 

Variables can be redeclared when using let. We can say 

`let x = 30;` and

`let x = 3;` 

This is because x has been declared already.

**CONST**: We cannot reassign or redeclare a variable when using const, when declaring a const variable, it must be assigned. **Const** means **constant**, its value cannot be changed.

We can't say 

`const name = 'Emem';`

`name = 'Jimmy';`  

This will result in an error because the value of a const cannot be changed. 

### Assigning a variable

We can assign a value to a variable while declaring or after declaring the variable. A variable can be declared without assigning it a value. You assign a  value to a variable using the "=" operator

Example `var a = 50;`

### Data types

In JavaScript we have different data types namely; string, Boolean, number, undefined, null, object, symbol, and biglnt. All except objects are [primitive data types](https://www.scientecheasy.com/2020/06/non-primitive-data-types-in-java.html/), object is a non-primitive data type. 

* **Object data type** stores different collections of data, while primitive data stores a single data only.
  Example of primitive data type;

```javascript
var name:
 { "Toyota";

  model: "CRV5";

  year: 2008;

 config: "two doors"
 }
```

* **Strings:** Represents textual data, that is wrapped in a single or a double quote. Strings are used for storing text. The number of elements in the string is its length.
  Examples 
  "Hello World"
   "Honda"
* **Number**: This is an integer or a floating-point number. It can be written with or without decimals.
  Examples;

`let x = 20;`

`let y = 2e-1;`

`let z = 2.5;`

* **Boolean**: It's any of these two values, which are; True or False.

`Boolean (20<10);` this will return False because 20 is not less than 10. 

`Boolean (20>10);` will return True because 20 is greater than 10.

* **Biglnt**: In JavaScript data type, biglnt is an integer with arbitrary precision.
  Examples;
  3n
  4566n
  23768954093567146788864598n
* **Undefined**: This is a data type whose variable is not initialized or assigned.
  Examples;

`var j;` // creates a variable but no value is assigned

`console.log ("j's value is" j)` log j's value is undefined

`const car;`

`let b;`

* **Null**: It denotes a null value, non-existent or invalid object
  Example; 

`let car = null;`

* **Symbol**: It is a data type whose instances are unique and immutable. Symbols are called atoms.
  Example;

 `let car = symbol ('Honda');`

* **Object**: It is a key-value pair of collection of data 
  Example;

`let car = {`

`name: "Toyota";`

`model: "Camry";`

`year: 2017 }`

It is recommended not to assign undefined to a variable. Null is usually used to assign "unknown" or "empty" values to a variable.

### Reasining

This simply means what has been declared and assigned again. 
Example; 

`var a = 20;`

`var a = 15;`

You have re-assigned the value of a to 15.

### Arithematic operators.

They are simply used in mathematical expression, performed on the number, and operate on two numbers. Operators can manipulate certain values. It assigns values to a variable and adds them together.
Example; 

`let w =1000 +50;`

* **Assingment  operator**: This operator ('=') assigns a value to a variable.
  Example; 

`let x =3;`

* **Addition operator**: This simply adds numbers (+)

`let a = 6;` //Assigns the value 6 to a

`let b = 2;` // Assigns value b to 2

`let c = a + b`   //The value 8 to c (6+2)

* **Division operator**: Divides the numbers (/)

`let a = 6;`

`let b = 2;`

`let c = a / b;`

* **Multiplication operator**: This multiplies the numbers (*)

`let a = 6;`

`let b = 2;`

`let c = a * b;`

There are other arithmetic operators like the **Remainder (%), Incrementing (++), Decrementing (--), and Exponentiation (**)\*\*.

### Summary

In conclusion, we understand that variable stores a single data value that can be changed later. You can declare and assign it to any value using var. This article also explained how and rules on naming a variable. If you have come this far, reading and studying with this article. I believe you've gained more knowledge about variables in JavaScript.

### Further reading

* [How to declare variable](https://www.geeksforgeeks.org/how-to-declare-variables-in-different-ways-in-javascript/?ref=rp)
* [Declaring JavaScript varialbes](https://www.better.dev/declaring-javascript-variables-var-let-const)
* [Understanig variable is JavaScript](9https://www.w3schools.com/)
* [Global Objects in JavaScript](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Symbol)
* [Primitive data types](https://www.scientecheasy.com/2020/06/non-primitive-data-types-in-java.html/)

Thank you for reading, you can connect with me on
[Facebook](https://www.facebook.com/emem.jimmy.9)
, [Twitter](https://twitter.com/lastbornpikin)
, [Instagram](https://www.instagram.com/emem_jimmy)
 and [Linkedin](https://www.linkedin.com/in/emem-jimmy-69456a206)