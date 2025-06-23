# Definitions

## BASIC

A term applied as a name to members of a special class of languages which possess similar syntaxes and semantic meanings; acronym for Beginner's All-purpose Symbolic Instruction Code. 

## Batch-mode

The processing of programs in an environment where no provision is made for user interaction.

## End-of-line

The character(s) or indicator which identifies the termination of a line. Lines of three kinds may be identified in Minimal BASIC: program lines, print lines and input reply lines. End-of-line may vary between the three cases and may also vary depending upon context. Thus, for example, an end of input line may vary on a given system depending on the terminal being used in interactive or batch mode.

Typical examples of end-of-line are carriage-return, carriage-return line-feed, and end of record (such as end of card). 

## Error 

A flaw in the syntax of a program which causes the program to be incorrect.

## Exception 

A circumstance arising in the course of executing a program which results from faulty data or computations or from exceeding some resource constraint. Where indicated certain exceptions (non-fatal exceptions) may be handled by the specified proceduresi if no procedure is given (fatal exceptions) or if restrictions imposed by the hardware or operating environment make it impossible to follow the given procedure, then the exception shall be handled by terminating the program. 

## Identifier

A character string used to name a variable or a function. 

## Interactive mode

The processing of programs in an environment which permits the user to respond directly to the actions of individual programs and to control the commencement and termination of these programs. 

## Keyword

A character string, usually with the spelling of a commonly used or mnemonic word, which provides a distinctive identification of a statement or a component of a statement of a programming language. 

The keywords in Minimal BASIC are: BASE, DATA, DEF, DIM, END, FOR, GO, GOSUB, GOTO, IF, INPUT, LET, NEXT, ON, OPTION, PRINT, RANDOMIZE, READ, REM, RESTORE, RETURN, STEP, STOP, SUB, THEN and TO. 

## Line 

A single transmission of characters which terminates with an end-of-line.

## Nesting 

A set of statements is nested within another set of statements when:

  - the nested set is physically contiguous, and
  - the nesting set (divided by the nested set) is non-null.

## Print zone 

A contiguous set of character positions in a printed output line which may contain an evaluated print statement element.

## Rounding 

The process by which the representation of a value with lower precision is generated from a representation of higher precision taking into account the value of that portion of the original number which is to be omitted. 

## Significant digits

The contiguous sequence of digits between the high-order nonzero digit and the low-order non-zero digit, without regard for the location of the radix point. Commonly, in a normalized 
floating point internal representation, only the significant digits of a representation are maintained in the significance.

NOTE: The Standard requires that the ability of a conforming implementation to accept numeric representations be measured in terms of significant digits rather than the actual number of digits (that is including leading or trailing zeroes) in the representation. 

## Truncation 

The process by which the representation of a value with lower precision is generated from a representation of higher precision by merely deleting the unwanted low order digits of the 
original representation.
