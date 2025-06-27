# Read and Restore Statements

## General Description

The read-statement provides for the assignment of values to variables from a sequence of data created from
data-statements (see [17](17_data_statement.md)). The restore-statement allows the data in the program to be reread. The
general syntactic forms of the read and restore statements are

    READ variable, ..., variable 
    RESTORE

## Syntaxe

1. read-statement       = `READ` variable-list
2. restore-statement    = `RESTORE`

## Examples

```BASIC
    READ X, Y, Z        READ X(l), A$, C
```

## Semantics

The read-statement causes variables in the variable-list to be assigned values, in order, from the sequence of data
(see [17](17_data_statement.md)). A conceptual pointer is associated with the data sequence. At the initiation of
execution of a program, this pointer points to the first datum in the data sequence. Each time a read-statement is
executed, each variable in the variable-list in sequence is assigned the value of the datum indicated by the pointer and
the pointer is advanced to point beyond that datum.

The restore-statement resets the pointer for the data sequence to the beginning of the sequence, so that the next
read-statement executed will read data from the beginning of the sequence once again.

The type of a datum in the data sequence shall correspond to the type of the variable to which it is to be assigned;
i.e., numeric-variables require unquoted-strings which are numeric-constants as data and string-variables require
quoted-strings or unquoted-strings as data. An unquoted-string which is a valid numeric representation may be assigned
to either a string-variable or a numeric-variable by a read-statement. 

If the evaluation of a numeric datum causes an underflow, then its value shall be replaced by zero. 

Subscript expressions in the variable-list are evaluated after values have been assigned to the variables preceding them
(i.e. to the left of them) in the list.

## Exceptions

- The variable-list in a read-statement requires more data than are present in the remainder of the data-sequence
  (fatal).
- An attempt is made to assign a string datum to a numeric variable (fatal).
- The evaluation of a numeric datum causes an overflow (non-fatal, the recommended recovery procedure is to supply
  machine infinity with the appropriate sign and continue). 
- A string datum contains too many characters (fatal). 

## Remarks

It is recommended that implementations report an underflow as exception and continue.

[Back](./)