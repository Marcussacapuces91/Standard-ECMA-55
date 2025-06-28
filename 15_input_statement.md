---
prev: 14_print_statement.html
next: 16_read_and_restore_statements.html
---

# Input Statement

## General Description

Input-statements provide for user interaction with a running program by allowing variables to be assigned values that 
are supplied by a user. The input-statement enables the entry of mixed string and numeric data, with data items being
separated by commas. The general syntactic form of the input-statement is

    INPUT variable, ..., variable

## Syntax

1. input-statement    = `INPUT` variable-list 
2. variable-list      = variable (comma variable)*
3. input-prompt       = [implementation-defined]
4. input-reply        = input-list end-of-line
5. input-list         = padded-datum (comma padded-datum)*
6. padded-datum       = space* datum space*
7. datum              = quoted-string / unquoted-string

## Examples

```BASIC
    INPUT X       INPUT X, A$, Y(2)      INPUT A, B, C
    3.14159       2,SMITH,-3             25,0 ,-15
```

## Semantics

An input-statement causes the variables in the variable-list to be assigned, in order, values from the input-reply. In
the interactive mode, the user of the program is informed of the need to supply data by the output of an input-prompt.
In batch mode, the input-reply is requested from the external source by an implementation-defined means. Execution of 
the program is suspended until a valid input-reply has been supplied.

The type of each datum in the input-reply shall correspond to the type of the variable to which it is to be assigned;
i.e. , numeric-constants shall be supplied as input for numeric-variables, and either quoted-strings or unquoted-strings
shall be supplied as input for string-variables. If the response to input for a string-variable is an unquoted-string,
leading and trailing spaces shall be ignored (see [4](4_characters_and_strings.md)).

If the evaluation of a numeric datum causes an underflow, then its value shall be replaced by zero.

Subscript expressions in the variable-list are evaluated after values have been assigned to the variables preceding them
(i.e. to the left of them) in the variable-list.

No assignment of values in the input-reply shall take place un¬ til the input-reply has been validated with respect to
the type of each datum, the number of input items, and the allowable range for each datum.

## Exceptions

- The type of datum does not match the type of the variable to which it is to be assigned (nonfatal, the recommended
  recovery procedure is to request that the input-reply be re-supplied).
- There is insufficient data in the input-list (nonfatal, the recommended recovery procedure is to request that the
  input-reply be resupplied).
- There is too much data in the input-list (nonfatal, the recommended recovery procedure is to request that the
  input-reply be resupplied).
- The evaluation of a numeric datum causes an overflow (non-fatal, the recommended recovery procedure is to request that
  the input-reply be resupplied).
- A string datum contains too many characters (nonfatal, the recommended recovery procedure is to request that the
  input-reply he resupplied).

## Remarks

This Standard does not require an implementation to perform any editing of the input-reply, though such editing may be 
performed by the operating environment.

It is recommended that the input-prompt consists of a question-mark followed by a single space.

This Standard does not require an implementation to output the input-reply.

It is recommended that implementations report an underflow as an exception and allow the input-reply to be resupplied.
