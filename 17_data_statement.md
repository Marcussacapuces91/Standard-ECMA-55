# Data Statement 

## General Description 

The data-statement provides for the creation of a sequence of representations for data elements for use by the
read-statement. The general syntactic form of the data-statement is 

    DATA datum, ..., datum

where each datum is either a numeric constant, a string-constant or an unquoted string.

## Syntax

1. data-statement   = `DATA` data-list  
2. data-list        = datum (comma datum)*
 
## Examples

```BASIC
DATA 3.14159, PI, 5E-10, ","
```

## Semantics

Data from the totality of data-statements in the program are collected into a single data sequence. The order in which
data appear textually in the totality of all data-statements determines the order of the data in the data sequence.

If the execution of a program reaches a line containing a data-statement, then it shall proceed to the next line with no
other effect.

## Exceptions

None .

[Back](./)