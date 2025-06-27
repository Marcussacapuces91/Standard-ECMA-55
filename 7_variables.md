# Variables
## General Description

Variables in BASIC are associated with either numeric or string values and, in the case of numeric variables, may be either simple variables or references to elements of one or two dimensional arrays; such references are called subscripted variables.

Simple numeric variables shall be named by a letter followed by an optional digit.

Subscripted numeric variables shall be named by a letter followed by one or two numeric expressions enclosed within parentheses. 

String variables shall be named by a letter followed by a dollar sign. 

Explicit declarations of variable types are not required; a dollar-sign serves to distinguish string from numeric variables, and the presence of a subscript distinguisnes a subscripted variable from a simple one.

## Syntax 

1. variable = numeric-variable / string-variable 
2. numeric-variable = simple-numeric-variable / numeric-array-element 
3. simple-numeric-variable = letter digit? 
4. numeric-array-element = numeric-array-name subscript
5. numeric-array-name = letter
6. subscript = left-parenthesis numeric-expression (comma numeric-expression)? right-parenthesis 
7. string-variable = letter dollar-sign 

## Examples

```BASIC
    X      A5    V(3)    W(X,X+Y/2)
    S$     C$
```

## Semantics

At any instant in the execution of a program, a numeric-variable is associated with a single numeric value and a string-variable is associated with a single string value. The value associated with a variable may be changed by the execution of statements in the program. 

The length of the character string associated with a string-variable can vary during the execution of a program from a length of zero characters (signifying the null or empty string) to 18 characters. 

Simple-numeric-variables and string-variables are declared implicitly through their appearance in a program. 

A subscripted variable refers to the element in the one or two dimensional array selected by the value(s) of the subscript(s). The value of each subscript is rounded to the nearest integer. Unless explicitly declared in a dimension statement, subscripted variables are implicitly declared by their first appearance in a program. In this case the range of each subscript is from zero to ten inclusive, unless the presence of an option-statement indicates that the range is from one to ten inclusive. Subscript expressions shall have values within the appropriate range (see [18](18_array_declarations.md)).

The same letter shall not be the name of both a simple variable and an array, nor the name of both a one-dimensional and a two-dimensional array. 

There is no relationship between a numeric-variable and a string-variable whose names agree except for the dollar-sign. 

At the initiation of execution the values associated with all variables shall be implementation-defined. 

## Exceptions 

A subscript is not in the range of the explicit or implicit dimensioning bounds (fatal). 

## Remarks 

Since initialization of variables is not specified, and hence may vary from implementation to implementation, programs that are intended to be transportable should explicitly assign a value to each variable before any expression involving that variable is evaluated. 

There are many commonly used alternatives for associating implementation-defined initial values with variables; it is recommended that all variables are recognizably undefined in the sense that an exception will result from any attempt to access the value of any variable before that variable is explicitly assigned a value.

[Back](./)
