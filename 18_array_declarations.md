---
prev: 17_data_statement.html
next: 19_remark_statement.html
---

# Array declarations

## General Description

The dimension-statement is used to reserve space for arrays. Unless declared otherwise, all array subscripts shall have
a lower bound of zero and an upper bound of ten. Thus the default space allocation reserves space for 11 elements in
one-dimensional arrays and 121 elements in two-dimensional arrays. By use of a dimension-statement, the subscript(s) of
an array may be declared to have an upper bound other than ten. By use of an option-statement, the subscripts of all
arrays may be declared to have a lower bound of one.

The general syntactic form of the dimension-statement is

    DIM declaration, ..., declaration

where each declaration has the form

        letter (integer)
    or  letter (integer , integer)

The general syntactic form of the option-statement is

    OPTION BASE n

where n is either 0 or 1.

## Syntax

1. dimension-statement      = `DIM` array declaration (comma array-declaration)* 
2. array-declaration        = numeric-array-name left-parenthesis bounds right-parenthesis
3. bounds                   = integer (comma integer)?
4. option-statement         = `OPTION BASE` (0/1)          
 
## Examples

```BASIC
DIM A (6), B(10,10)
```

## Semantics

Each array-declaration occurring in a dimension-statement declares the array named to be either one or two dimensional
according to whether one or two bounds are listed for the array. In addition, the hounds specify the maximum values that
subscript expressions for the array can have.

The declaration for an array, if present at all, shall occur in a lower numbered line than any reference to an element
of that array. Arrays that are not declared in any dimension-statement are declared implicitly to be one or
two dimensional according to their use in the program, and to have subscripts with a maximum value of ten
(see [7](7_variables.md)). 

The option-statement declares the minimum value for all array subscripts; if no option-statement occurs in a program,
this minimum is zero. An option-statement, if present at all, must occur in a lower numbered line than any 
dimension-statement or any reference to an element of an array. If an option-statement specifies that the lower bound
for array subscripts is one, the no dimension-statement in the program may specify an upper bound of zero. A program may
contain at most one option-statement. 

If the execution of a program reaches a line containing a dimension-statement or an option-statement, then it shall
proceed to the next line with no other effect.

An array can be explicitly dimensioned only once.

## Exceptions 

None.
