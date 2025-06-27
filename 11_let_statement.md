# `LET` statement
## General Description 

A let-statement provides for the assignment of the value of an expression to a variable. The general syntactic form of the let-statement shall be

    LET variable = expression

## Syntax

1. let-statement = numeric-let-statement / string-let-statement
2. numeric-let-statement = LET numeric-variable equals-sign numeric-expression 
3. string-let-statement = LET string-variable equals-sign string-expression 

## Examples

```BASIC
    LET P = 3.14159 
    LET A(X,3) = SIN(X)*Y + 1 
    LET A$ = "ABC" 
    LET A$ = B$ 
```
 
## Semantics

The expression is evaluated (see 8) and its value is assigned to the variable to the left of the equals sign. 

## Exceptions

A string datum contains too many characters (fatal).
