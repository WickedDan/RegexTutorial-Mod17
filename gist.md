# Regex Turtorial

Welcome to a Regex Tutorial. I will be proving you with an example of a regular expression. Then breaking it down, highlighting the components used while summarizing each components use/importance giving smaller examples as well.

## Summary

> <h2>/^(?=.*[A-Z])(?=.*[a-z])(?=.*[0-9])(?=.*\W)(?!.*[#]).{6,22}$/<h2>
Regular expressions are a series of special characters that define a search pattern. Above is an example of a regex that represents a password.
The requirements for the password are one uppercase letter, one lowercase letter, one digit, a special character excluding #s and has to be 6 to 22 characters long.

## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [Grouping Constructs](#grouping-constructs)
- [Bracket Expressions](#bracket-expressions)
- [Character Classes](#character-classes)
- [The OR Operator](#the-or-operator)
- [Flags](#flags)
- [Character Escapes](#character-escapes)

## Regex Components

### Anchors
> <h3>/^...$/<h3>
- The ^ and $ characters are anchors in regular expressions.
- The ^ anchor indicates that the string must start with the characters following it.
- The $ anchor signifies that the string must end with the characters preceding it.

### Quantifiers
> <h3>/^(?..*...)(?..*...)(?..*...)(?..*..)(?..*...).{6,22}$/<h3>
- Quantifiers set the limits of the string that your regex matches.
- *—Matches the pattern zero or more times
- +—Matches the pattern one or more times
- ?—Matches the pattern zero or one time
- {}—Curly brackets can provide three different ways to set limits for a match:
- { n }—Matches the pattern exactly n number of times
- { n, }—Matches the pattern at least n number of times
- { n, x }—Matches the pattern from a minimum of n number of times to a maximum of x number of times

### Grouping Constructs
> <h3>/^(...)(...)(...)(...)(...)...$/<h3>
The primary way you group a section of a regex is by using parentheses (()). 
Each section within parentheses is known as a subexpression.
Subexpressions look for an exact match unless they're told to do otherwise.
Grouping constructs have two primary categories: capturing and non-capturing.
Capturing groups capture the matched character sequences for possible re-use (including a numbered backreference) while non-capturing groups do not. A grouping construct can be made non-capturing by adding the characters ?: at the beginning of an expression inside the parentheses.

### Bracket Expressions
> <h3>/^...[A-Z]...[a-z]...[0-9]...$/<h3>
Bracket expressions outline the characters we want to include. You may also represent range with a hyphen(-).

### Character Classes
> <h3>/^...*\W...$/<h3>
A character class defines a set of characters that can match a part of an input string. Some common character classes include:
- .: Matches any character except a newline.
- \d: Matches any digit (equivalent to [0-9]).
- \w: Matches any alphanumeric character or underscore (equivalent to [A-Za-z0-9_]).
- \s: Matches any whitespace character, including tabs and line breaks.
- These classes can be inverted by capitalizing them, such as \D for non-digits, \W for non-word characters, and \S for non-whitespace characters.

### The OR Operator
> <h3>/^Did not use in this example$/<h3> 
- Using the OR operator (|), the expression [abc] could be written as (a|b|c).
- (abc):(xyz)
- And then use the OR operator to convert it to the following:
- (a|b|c):(x|y|z)
- Now, both of the strings "abc:xyz" and "acb:xyz" would match, as well as "a:z", but "xyz:abc" would not.

### Flags
> <h3>/^Did not use in this example$/<h3>
Flags in regex are added at the end of a pattern, after the second slash, to define additional functionality. 
Here are the six flags:
- g: Global search, finds all matches in a string.
- i: Case-insensitive search, ignores case differences.
- m: Multi-line search, treats input as multiple lines.
- s: Makes the wild character . match newlines as well.
- y: Makes the expression start its searching from the index indicated in its lastIndex property.
- u: Makes the expression assume individual characters as code points, not code units, and thus match 32-bit characters as well.

### Character Escapes
> <h3>/^...\#...$/<h3>
In regex, a backslash () is used to escape characters that would otherwise be interpreted as part of the regex syntax. For instance, the open curly brace ({) normally indicates the start of a quantifier, but if you use a backslash before it (\{), it will be treated as a literal open curly brace instead. This escaping is particularly useful when you need to search for special characters that have special meanings in regex. However, within bracket expressions, special characters, including the backslash, do not have their usual special meanings.

## Author

This informational tutorial was created and written by Daniel Contreras. Github user WickedDan
https://github.com/WickedDan
