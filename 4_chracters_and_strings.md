# Characters and strings
## General Description 

The character set for BASIC is contained in the ECMA 7-bit coded character set. Strings are sequences of characters and are used in BASIC programs as comments (see 19), as string constants (see 6), or as data (see 15). 

## Syntax

1. letter = A/B/C/D/E/F/G/H/I/J/K/L/M/N/O/P/Q/R/S/T/U/V/W/X/Y/Z 
2. digit = 0/1/2/3/4/5/6/7/8/9 
3. string-character = quotation-mark / quoted-string-character
4. quoted-string-character = exclamation-mark / number-sign / dollar-sign / percent-sign / ampersand / apostrophe / left-parenthesis / right-parenthesis / asterisk / comma / solidus / colon / semi-colon / less-than-sign / equals-sign / greater-than-sign / question-mark / circumflex-accent / underline / unquoted-string-character 
5. unquoted-string-character = space / plain-string-character 
6. plain-string-character = plus-sign / minus-sign / full-stop / digit / letter 
7. remark-string = string-character*
8. quoted-string = quotation-mark quoted-string-character* quotation-mark 
9. unquoted-string = plain-string-character / plain-st ring-character unquoted-string-characte r* plain-st ring-character

## Examples

ANY CHARACTERS AT ALL (?!*!!) CAN BE USED IN A "REMARK". "SPACES AND COMMAS CAN OCCUR IN QUOTED STRINGS." COMMAS CANNOT OCCUR IN UNQUOTED STRINGS.

## Semantics

The letters shall be the set of upper-case Roman letters contained in the ECMA 7-bit coded character set in positions 4/1 to 5/10.

The digits shall be the set of arabic digits contained in the ECMA 7-bit coded character set in positions 3/0 to 3/9.

The remaining string-characters shall correspond to the remaining graphic characters in position 2/0 to 2/15, 3/10 to 3/15 and in positions 5/14, 5/15 of the ECMA 7-bit coded character set.

The names of characters are specified in Table 1. 

The coding of characters is specified in Table 2; however, this coding applies only when programs and/or input/output data are exchanged by means of coded media. 

## Exceptions 

None. 

## Remarks 

Other characters from the ECMA 7-bit coded character set (including control characters) may be accepted by an implementation and may have a meaning to some other processor (such as an editor) but have no prescribed meaning within this Standard. Programs containing characters other than the string-characters described above are not standard-conforming programs. 

The several kinds of characters and strings described by the syntax correspond to the various uses of strings in a BASIC program. Remark-strings may be used in remark-statements (see 19). Quoted-strings may be used as string-constants (see 6). Unquoted-strings may be used in addition to quoted-strings as data elements (see 17) without being enclosed in quotation marks; unquoted-strings cannot contain leading or trailing spaces.
