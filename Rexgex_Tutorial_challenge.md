# Regex_Tutorial_challenge

A regular expression, often abbreviated as "regex" or "regexp," is a powerful and concise pattern-matching language used for searching, matching, and manipulating text data. It provides a way to describe complex search patterns that can match strings based on specific rules or patterns within the text. Regular expressions are widely used in programming, text editors, and various software applications for tasks such as data validation, text extraction, and text transformation.

## Summary

Described in this tutorial will be the various components for the regex that matches an email, 
Matching an Email: /^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/

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
In regular expressions (regex), anchors are special characters or tokens that represent specific positions within the input text where a match must occur. Anchors are used to enforce rules about where in the text a regular expression pattern should find a match. They don't match any characters themselves but define the positions or boundaries for matching.

In the above regex, the caret (^) character is used to start the string of characters, and it indicates that the match must occur at the beginning of the input string. The dollar sign ($) is used at the end of the regex pattern. It indicates that the match must occur at the end of the input string. 

### Quantifiers

Quantifiers in regular expressions are symbols or metacharacters that allow you to specify how many times a particular element in your regex pattern should occur. They provide a way to define repetition and are crucial for specifying patterns that can match a variable number of characters.

Two common quantifiers are + (plus) and {m, n} (curly braces with a minimum and maximum value). Let's explore how these quantifiers are used in the regex pattern to specify the number of characters allowed in different parts of an email address.

In a regular expression (regex) pattern for email validation like ^([a-z0-9_.-]+)@([\da-z.-]+)\.([a-z.]{2,6})$, quantifiers such as + and {2,6} are used to specify the number of characters allowed in different parts of the email address. The + means that the preceding element (like [a-z0-9_.-] or [\da-z.-]) must appear at least once but can repeat multiple times. For example, [a-z0-9_.-]+ ensures that the username part of the email address must contain at least one character but can have more. On the other hand, {2,6} specifies that the top-level domain (TLD) part of the email address must consist of between 2 and 6 characters, accommodating common TLDs like "com" or "org." 

### OR Operator

There is no OR Operator in this regex tutorial. 

### Character Classes

Character classes in regular expressions (regex) are used to define sets of characters that can match a single character in the input text. They are enclosed in square brackets [ ] and allow you to specify a range or list of characters that the regex engine should consider as valid matches. 

The character class is used for the domain name part of the email address. It includes lowercase letters from 'a' to 'z', digits (represented by \d), dot ('.'), and hyphen ('-'). In this context, it allows for domain names to consist of lowercase letters, digits, dots, and hyphens, which are common characters in domain names like "example.com" or "my-site.org."

### Flags

Flags, also known as regex modifiers or options, are additional settings that can be applied to regular expressions (regex) patterns to change their behavior during pattern matching. 

Flag are implemented with the characters g, i, and m. There are no flags in this regex tutorial. 

### Grouping and Capturing

Parentheses () are used to create groups and capture matched portions of the text. This allows you to extract specific parts of a matched string. Characters insode of the () are labeled as subexpressions.

In the context of your email regex pattern ^([a-z0-9_.-]+)@([\da-z.-]+)\.([a-z.]{2,6})$, there are three sets of parentheses, each serving a different capturing purpose:

([a-z0-9_.-]+): This captures the username part of the email address. It captures one or more lowercase letters, digits, underscores, dots, or hyphens and stores this part of the email address in a capture group.

([\da-z.-]+): This captures the domain name part of the email address. It captures one or more digits, lowercase letters, dots, or hyphens and stores this part in a separate capture group.

([a-z.]{2,6}): This captures the top-level domain (TLD) part of the email address. It captures between 2 and 6 lowercase letters or dots and stores this part in yet another capture group.

For example, if you use this regex pattern to match the email address "janedoe@example.com," the capture groups would capture the following portions of the email:

Capture Group 1: "janedoe"
Capture Group 2: "example"
Capture Group 3: "com"
You can access these captured values programmatically in many programming languages, allowing you to extract and manipulate specific parts of the matched text.

### Bracket Expressions


### Greedy and Lazy Match

### Boundaries

### Back-references

### Look-ahead and Look-behind

## Author

A short section about the author with a link to the author's GitHub profile (replace with your information and a link to your profile)
