# Regex Tutorial

This is a regex tutorial

## Summary

In this tutorial we will explain how the below regex functions, by breaking down each part of the expression and describing what it does.

/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/

This regex is a pattern used to match and avalidate emai addresses. 
Below is an example JavaScript code to check if an email address matches the pattern:

const emaiRegex = /^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/;

const email = "example@email.com";
if (emailRegex.test(email)) {
    console.log("Valid email address");
} else {
    console.log("Invalid email address");
}

## Table of Contents


- [Regex Tutorial](#regex-tutorial)
  - [Summary](#summary)
  - [Table of Contents](#table-of-contents)
  - [Regex Components](#regex-components)
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
  - [Author](#author)

## Regex Components

### Anchors

In our regex, the anchor is represented by the '^' and thed '$' symbols.

- '^': is the start anchor and indicates that the match should start at the beginning of the string.
- '$': is the end anchor and indicates that the match should end at the end of the string. 

These anchors ensure that the entire string is matched by the regex. So the pattern must match the entire email address and not just a part of it. 


### Quantifiers

'+': it is a quantifier that specifies that the preceding element should occur one or more times. 
For example: '([a-z0-9_\.-]+)' matches one or more lowercase letters, digits, underscores, dots, or dashes. 

'{2,6}': it is a quantifier that specifies a range of occurrences for the preceding element.
in this case, '([a-z\.]{2,6})' matches between 2 and 6 lowercase letters or dots. 
It ensures that the top-level domain part of the email address has a length beween 2 and 6 characters.


### OR Operator

In our regex we don't have an OR Operator, but generally the OR Operator is represented by the '|' symbol. 
It is used to specify multiple alternative patterns within a single group of subexpression. 
The OR operator allows your to match any one of the provided patterns.

### Character Classes

Caracter classes are denoted by square bracktes and provide a way to define a range or a set of characters that can match a single position in the input string.
Here are the character classes used in our regex:

- '[a-z0-9_\.-]': this one matches a single character that can be a lowercase letter, a digit, an underscore, a dot, or a dash.
  It allows for a wide range of valid characters for the username and domain name parts of the email address.
- '[\da-z\.-]': this character class matches a single character that can be a digit, a lowercase letter, a dot, or a dash.
  The '\d' represents any digit, It is used in the domain name part of the email address.
- '[a-z\.]': this character class matches a single lowercase letter or a dot. I is used in the top-level domain part of the email address

### Flags

We don't have any flags in our regex, but generally speaking, flags are optionla settings that can be added after the closing delimiter of a regex to modify it's behavior.
They provide additional functionality and control over how the pattern is matched. 
Common flags used in regexes include: 'i'(case sensitive), 'g'(global), 'm'(multiline).

### Grouping and Capturing

Grouping '()' is used to create logical units within the regex. It allows you to apply quantifiers, alternation, and other operations to a group of characters.
We have three instances of grouping and capturing in our regex:

- '([a-z0-9_\.-]+)': this is the first one and it catpures the username part of the email address.
- '([\da-z\.-]+)': the second one captures the domain name part of the email address.
- '([a-z\.]{2,6})': and the third one captures the top-level domain part of the email address.

### Bracket Expressions

Bracket expressions allow you to specify a set of characters that can match at a particular position in the input string.
We have three bracket expressions used in our regex:

- '[a-z0-9_\.-]': matches a single character that can be a lowercase letter, a digit, an underscore, a dot, or a dash. 
  It allows for  wide range of valid characters for the username and domain name parts of the email.
- '[\da-z\.-]': matches a single character that can be a digit, a lowercase letter, a dot or a dash.
  The '\d' reporesents any digit. It is used in the domain name part of the email address.
- '[a-z\.]': matches a single lowercase letter or a dot. It is used ton the top-level domain part of the email address.

### Greedy and Lazy Match

Greedy matching means that the quantifiers will match as much as possible, while still allowing the overall pattern to match.
It will ensure that the capturing groups capture the longest possible substring that still allows the overall pattern to match.

Lazy matching is an alternative matching behavior where a quantifier matches as few characters as possible while still allowing the overll pattern to match.

By default, quantifiers in regexes are greedy, however, by adding a '?' after a quantifi9er, you can make it lazy and change its behavior.

### Boundaries

The boundaries of a regex ensure that the pattern mathces hte entire email address and doesn't allow any extra characters or invalid format bevore or after it.
There are two boundaries in our regex:

- '^': this is the start of a line anchor. It asserts that the match must start at the beginning of a line.
- '$': this is the end of line anchor. It assertes that the match must occur at the end of a line.

### Back-references

Back-references are indicated by the use of '\' followed by a number or a name corresponding to the capturing group.
They allow you to match a previously captured substring withing the same regex.
We don't currently have a back-reference in our regex.

### Look-ahead and Look-behind

Look-ahead and Look-behind are zero-width assertions in regex that allow for a match of the pattern only if it is followed by or preceded by another pattern,
without including the matched content in the overall match. 

## Author

[Genci Odobashi](https://github.com/odobashigenci)
