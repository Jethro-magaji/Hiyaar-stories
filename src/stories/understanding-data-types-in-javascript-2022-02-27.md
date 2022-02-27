---
title: Understanding data types in JavaScript
shortDesc: " In JavaScript, there are six basic data types that can be divided
  into three main groups: primitive (or primary), composite (or reference), and
  special data types. String, Number, and Boolean are primitive data types,
  while Object, Array, and Function are composite data types(these data types
  are all objects. Whereas Undefined and Null are special data types. In this
  article, we will look at primitive data type"
badge: JavaScript
author: EMMANUEL OLUBIYI
authorImage: /assets/images/emoji.jpg
authorBio: EMMANUEL OLUBIYI is a Tech Enthusiast with the volunteer spirit. He
  loves working on community building project and sharing valuable tip son
  JavaScript
timeRead: 10 min
date: 2022-02-27T18:15:58.079Z
tags:
  - latest
image: /assets/images/photo-16.jpg
imageAlt: "hero "
---
 In JavaScript, there are six basic data types that can be divided into three main groups: primitive (or primary), composite (or reference), and special data types. String, Number, and Boolean are primitive data types, while Object, Array, and Function are composite data types(these data types are all objects. Whereas Undefined and Null are special data types.
In this article, we will look at primitive data types.

### Goals
By the end of this article, you should:
- understand the concept of data types
- know the different data types I JavaScript
- be able to carry out basic operations with data types in JavaScript. 
This will help you to check if you have grasped the concept of data types in JavaScript.
### Prerequisite:
Before reading this article, you should know what a variable is, how to declare, assign and initialize a variable because variables and data types are always used together. 
Knowledge of JavaScript variables and how to use them.


### Table of contents
Introduction
- Goals

- Prerequisite
-What are Data types
- The Data types we have
- Types  of Operator
- Remark
_ Reference

Prerequisite:
Before reading this article, you should know what a variable is, how to declare, assign and initialize a variable because variables and data types are always used together. 
Knowledge of JavaScript variables and how to use them.
Head over to w3schools.com to learn about JavaScript variable.

What are Data Types
Data types are the various types of data value or item that can be used or are valid in a programming language. Data is one key feature one can’t do without when programming as we basically work with data, we collect data from the users, databases, process it, and give the data to the users and databases. All data that are used in JavaScript language must fall into some set-out category and this is what we refer to as data types and that’s what we will be looking at in this article.



###  Data types
In JavaScript, we have the following data types:  

- Strings
- Numbers
- Boolean
- Arrays
- Objects
- Undefined
- Null

### Strings
A “**string**” is a set of characters made up of letters, spaces, symbols, and even numbers enclosed within a quotation mark, either double quote (“ ”) or single quote (‘ ’). 

Example:

``Let name = “emmo”;``

``Let quote = “No amount of money ever bought a second of time.”``

``Let Age = “18”;``

As you noticed Age is a number, but here it is used as a string. Anything placed inside quotation marks is considered a string by JavaScript.

## Numbers 
The “Number” data type contains arithmetic values. These may be decimals (99.9, 11.05), integers (30, 100, 0), scientific or exponential notations (123e4, 45-e6).

Example:

``Let Age = 24;`` 

``Let num = 11.85;`` 

``Let val = 10e2;`` 

Age here is a Number, it has no quotation mark, unlike when it was used as a string.
Val will be equal to 100, 10 x 10^2.

### Boolean

The “**Boolean**” data type has just two types of value, **true** and **false**. It is mostly used for conditional testing (if, else statements) as it is going to be either one or the other (either true or false).
Example:

``Let a = true;``

``Let b = false;``
``Let x = “I am a boy”;``
``Let y = 20;``
``x == y`` should return false because the value of each variable is different from the other.

### Arrays
The “**array**” data type is a list of items (strings, numbers, arrays, and or objects), separated with a comma and enclosed in square **[ ] ** brackets. Arrays are mostly used to group related data, it can consist of items with similar data types or a mixture of different data types.

Example: 

``Let brands = [ “Dior”, “Channel”, “Gucci” ];``

``Let myArr = [“Emmanuel”, 18, true];``

Brands here is an array of fashion brand names and they are string data types; while **myArr**  is also an array with different data types: “emmo” is a string, 18 is a number, and true is a Boolean.

To access each of the values stored in an array, you have to know the index of the item in that array. Arrays are **zero-indexed**, meaning that the first item stored in an array has an index of 0, the second will be 1 and it increments for each successive data stored in the array.
To then access the array, you will write out the array name and the index of the item you want to get will be placed in a square bracket. Like this: arrayName[index];
To access Gucci in the brand's array, we increment from 0 for each item stored in the array, so  “Dior” will be 0, “Channel” will be 1 and “Gucci” will be 3. Then to get “Gucci” we write this:
Brands[2]; this will be give us “Gucci”.

### Objects
The “**object**” data type is a list of items (strings, numbers, arrays, and or objects), written as **name:value pair**, separated by a comma and enclosed in curly brackets. Objects are mostly used to group related datas together, like arrays, it can also consist of items with similar data types or a mixture of different data types.
Example:
Let person = { 
    firstName:"John", 
    lastName:"Doe", 
    age:50, 
    nice: true,
    hobbies: [“swimming”, “dancing”, “coding”]
};
The object (person) in the example above has 5 properties: firstName, lastName, age, nice  and hobbies. You will notice that the data item is placed after a word and a semicolon (:). The word is known as a property of the object.
firstName is a string, lastName is a string, age is a number, nice is a boolean and hobbies is an array;
To access the property of the Object, we can use this: ‘person.firstName’, where person is the name of the object and firstName is the property we are trying to access. Another way to access the property is to say ‘person[“firstName”]’, this should return the same value you get when you use ‘person.firstName’;
person.nice will return true
person.hobbies will return [“swimming”, “dancing”, “coding”]
person.hobbies[1] will return “dancing”
person[“hobbies”][1] will return “dancing”

Undefined
The “undefined” data type is assigned by default to a variable, when it is declared, but nothing has been assigned to it. We can also assign the undefined data type to a variable, but it is better to just declare a variable without assigning a value to it to give it the undefined value. This shows that the variable doesn’t have a value.
Example:
Let name;
name here has been declared, but no value has been assigned to it, so it will have a default value of undefined.

Null
The “null” data type is a special value that represents empty or unknown value. It is mostly used to denote that the variable is empty.
Example:
Let name = null;
This shows that name here is empty.

The typeof Operator
the typeof Operator is used to get the data type of a variable or a data, it returns the data type of the variable or data written after it.
Example:
Let name = “Emmanuel”;
typeof name; this returns string, as name contains a string value.
typeof 18; this returns number;
typeof true; this returns a Boolean;
let brands = [ “Dior”, “Channel”, “Gucci” ];
typeof brands; this returns array, because brands contains an array.



