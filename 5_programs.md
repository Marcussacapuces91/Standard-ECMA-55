# Programs
## General Description 

BASIC is a line-oriented language. A BASIC program is a sequence of lines, the last of which shall be an end-line and each of which contains a keyword. Each line shall contain a unique line-number which serves as a label for the statement contained in that line. 

## Syntax 

1. program = block* end-line 
2. block = (line/for-block)* 
3. line = line-number statement end-of-line 
4. line-number = digit digit? digit? digit? 
5. end-of-line = [implementation-defined]
6. end-line = line-number end-statement end-of-line 
7. end-statement = END 
8. statement = data-statement / def-statement / dimension -statement / gosub-statement / goto-statement / if-then-statement / input-statement / let-statement / on-goto-statement / option-statement / print-statement / randomize-statement / read-statement / remark-statement / restore-statement / return-statement / stop-statement

## Examples 

    999 END 
    
## Semantics 

A BASIC program shall be composed of a sequence of lines ordered by line-numbers, the last of which contains an end-statement. Program lines shall be executed in sequential order, starting with the first line, until 

- some other action is dictated by a control statement, or
- an exception condition occurs, which results in a termination of the program, or
- a stop-statement or end-statement is executed.
    
Special conventions shall be observed regarding spaces. With the following exceptions, spaces may occur anywhere in a BASIC program without affecting the execution of that program and may be used to improve the appearance and readability of the program. 

Spaces shall not appear:

- at the beginning of a line
- within keywords
- within numeric constants
- within line numbers
- within function or variable names
- within two-character relation symbols 

All keywords in a program shall be preceded by at least one space and, if not at the end of a line, shall be followed by at least one space. 

Each line shall begin with a line-number. The values of the integers represented by the line-numbers shall be positive nonzero; leading zeroes shall have no effect. Statements shall occur in ascending line-number order. 

The manner in which the end of a statement line is detected is determined by the implementation; e.g. the end-of-line may be a carriage-return character, a carriage-return character followed by a line-feed character, or the end of a physical record. Lines in a standard-conforming program may contain up to 72 characters; the end-of-line indicator is not included within this 72 character limit. 

The end-statement serves both to mark the physical end of the main body of a program and to terminate the execution of the program when encountered. 

## Exceptions 

None. 

## Remarks 

Local editing facilities may allow for the entry of statement lines in any order and also allow for duplicate line-numbers and lines containing only a line-number. Such editing facilities usually sort the program into the proper order and in the case of duplicate line-numbers, the last line entered with that line-number is retained. In many implementations, a line containing only a line-number (without trailing spaces) is usually deleted from the program. 
