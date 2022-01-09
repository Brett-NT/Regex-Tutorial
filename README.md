# Quick Guide to Regex (Regex Tutorial)

This guide is intended to be a comprehensive overview of Regular Expressions are (Regex), the different components of an expression and their functions,
and ultimately, how Regex works as a whole.

## Summary

Regex (short for Regular Expression) is a sequence of characters that specifies a search pattern. Typically, it is used to search for and manage specific elements in text, typically a string.
A common use of Regex is in usernames or passwords, allowing for capital letters, hyphens, underscores, special characters, etc.
Here's an example of Regex:
```
/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/
```
* This Regex cod is used for matching an email address

## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [OR Operator](#or-operator)
- [Character Classes](#character-classes)
- [Flags](#flags)
- [Grouping and Capturing](#grouping-and-capturing)
- [Bracket Expressions](#bracket-expressions)
- [Greedy and Lazy Match](#greedy-and-lazy-match)
- [Boundaries](#boundaries)
- [Back-references](#back-references)
- [Look-ahead and Look-behind](#look-ahead-and-look-behind)

## Regex Components

### Anchors
Anchors are characters that are used to find a specific strings based on characters at the beginning or end of the string.

List of Anchors:
* '^' - looks for the word or characters at the beginning of a string
* '$' - looks for the word or characters at the end of a string that are placed just before this character.

Examples:
```
'^This' - This matches with a string that starts with the word 'This'
'Example$' - This matches with a string that ends with the word 'Example'
^This Example$ - Since it specifies the beginning and end of the string, this will match with a string written exactly as 'This Example'
This Example - This one doesn't specify the beginning or end, so it will match with any string containing 'This Example' somewhere within it.
```

### Quantifiers
Quantifiers are characters that specify how many times a specific character should occur within a matching string.

List of Quantifiers:
* '*' - looks for strings that has the characters preceding it and zero or more of the final character before this quantifier.
* '+' - similar rule as '*', but the last character preceding the quantifier must have one or more occurrances.
* '?' - similar rule as '*' and '+', but the last character preceding the quantifier can only occur zero times or one time.
* '{}' - looks for a string with the last character preceding the quantifier occurring as many times as the number placed inside the brackets.
* '()*' - looks for a string with zero or more occurrances of the string that is placed inside the brackets.

* Examples:
```
'abc*' - matches with a string that contains 'ab' followed by zero or more of 'c' (i.e. 'ab', 'abc', 'abcc', 'abccc', etc.)
'abc+' - matches with a string that contains 'abc' and can be followed by more 'c' (same as '*' but zero occurrances is not acceptable)
'abc?' - matches with a string that contains either 'ab' or 'abc' (allows for zero or one occurrances of last character)
'abc{5}' - matches with a string that contains 'ab' followed by 5 'c' (i.e. 'abccccc')
'abc{5,9}' - matches with a string that contains 'ab' followed by anywhere between 5 and 9 'c' (i.e. 'abccccc' - 'abccccccccc')
'a(bc)*' - matches with a string that contains 'a' followed by zero or more occurrances of 'bc' (i.e. 'a', 'abc', 'abcbc', 'abcbcbc', etc.)
'a(bc){1,3}' - matches with a string that contains 'a' followed by one to three occurrances of 'bc' (i.e. 'abc', 'abcbc', 'abcbcbc')
```

### OR Operator
OR Operators looks for strings with a choice of characters (a string can have this character OR that character)

List of OR Operators:
* '(|)' = matches a string that contains the character preceding the brackets followed by the character on either the left or the right of the vertical bar within the brackets.
* '[]' - matches with a string that contains the character preceding the brackets, and is NOT followed by any characters in the brackets.

* Examples:
```
'a(b|c)' - matches when a string contains 'a' followed by either 'b' or 'c' (i.e. 'ab' or 'ac')
'a[bc]' -matches when a string contains 'a', but doesn't capture 'b' or 'c'
```

### Character Classes
Character Classes are what the the Regex to match with a string out of a defined list of characters.

List of Character Classes:
* '\d' - matches any single character that is a digit.
* '\w' - matches any single character that is a letter in the alphabet (a-z)
* '\s' - matches with whitespace
* '.' - matches any character
* Capitalizing any letter in these classes will cause it to match with the inverse
* '\D' - matches with any non-digit character
* '\W' - matches any non-alphabet letter chatacter
* '\S' - matches with non-whitespace

### Flags
Flags are optional parameters that can be added to the expression that change the way the regex searches for strings. Each letter has a different effect to the search.

List of Flags:
* 'g' - Stands for 'global'. Searches for all occurrances in the test.
* 'm' - Stands for 'multi-line'. When using anchors ('^' and '$', this flag will specify that only the beginning and end of the string need to match, and not the whole string in its entirety.
* 'i' - Stand for Insensitive. disable case-sensitivity on the search

Examples:
```
/Example/g - searches for every occurrance of 'Example'
/Example/m - matches the beginning and end of a string with 'Example', rather than matching the entire string as 'Example'.
/Example/i - matches any occurrance of 'Example', regardless of capitalization (i.e. 'eXamPlE', 'EXampLe', exAMPLE', etc.)
```

### Grouping and Capturing
Grouping does just that. It groups patterns and search rules into a block that can match entire strings with more specificity.

List of Groupings:
* '()' - parentheses will create the capture group
* '(?:)' - using '?:' will disable the capture group
* '(?<>)' - using '?<>' will create a name for the capture group

Examples:
```
x(yz) - this creates a group for 'yz'.
x(?:yz) - this will disable the 'yz' group
x(?<EX>yz - this names the 'yz' group as "EX"

### Bracket Expressions

### Greedy and Lazy Match

### Boundaries

### Back-references

### Look-ahead and Look-behind

## Author

A short section about the author with a link to the author's GitHub profile (replace with your information and a link to your profile)
