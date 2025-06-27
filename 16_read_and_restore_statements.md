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

[Back](./)