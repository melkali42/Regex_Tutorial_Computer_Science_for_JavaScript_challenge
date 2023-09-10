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

Square brackets [ ] in regular expressions (regex) are used to define character classes, which specify a set of characters among which a single character must match. Character classes provide a concise way to describe a group of characters that should be considered as valid matches.

Here's how square brackets [ ] are used in character classes, with examples specific to the email regex pattern: 

    Inside square brackets, you can define a range of characters using a hyphen -. For example, [a-z] matches any lowercase letter from 'a' to 'z'. [0-9] matches any digit from '0' to '9'. 
    In the email regex [a-z0-9_.-]: This character class defines a range of characters that are valid for the username part of an email address. It includes lowercase letters, digits, underscores, dots, and hyphens.

    You can list individual characters within square brackets. For example, [aeiou] matches any vowel ('a', 'e', 'i', 'o', 'u'). In the email regex: [\da-z.-]: This character class specifies individual characters that are valid for the domain name part of an email address. It includes digits, lowercase letters, dots, and hyphens.

    You can combine individual characters, ranges, and negation within the same character class. For example, [A-Za-z] matches any uppercase or lowercase letter, [0-9A-F] matches hexadecimal digits, and [^,;] matches any character except a comma or semicolon. In the email regex: [a-z.]: This character class in the top-level domain (TLD) part matches lowercase letters and dots, allowing for TLDs like "com" or "org."

In the email regex pattern ^([a-z0-9_.-]+)@([\da-z.-]+)\.([a-z.]{2,6})$, square brackets are used within character classes to define valid sets of characters for the username, domain name, and TLD parts of the email address. This ensures that the email addresses adhere to the expected character constraints while allowing for variations within those constraints.

### Greedy and Lazy Match

Greedy and lazy matching are concepts in regular expressions (regex) that control how quantifiers (such as *, +, ?, and {}) match and consume characters in the input text. These concepts determine whether a quantifier should match as much as possible (greedy) or as little as possible (lazy).

The tutorial regex example is a greedy regex. This is symbolized by the two "+" characters that are used at the end of the first two subexpressions,([a-z0-9_.-]+) and ([\da-z.-]+). This means the regex will match all of the string patterns that fit the criteria from [] square bracket expressions.

The {2,6} is another quatifier that created the parameters for this matching regex. This regex will match anything that is 2-6 characters long at this part of the regex. 

### Boundaries

In regular expressions (regex), boundaries are used to specify positions within the input text where a match should occur or where it should not occur. They do not match any characters themselves but rather define conditions around where the regex pattern can or cannot match. One common boundary is the word boundary \b, which is used to indicate the boundary between a word character (typically a letter, digit, or underscore) and a non-word character (anything other than a word character). The word boundary \b is used in regex to ensure that a pattern matches only whole words, not substrings within larger words. It is often employed to search for or manipulate complete words in a text.

The boundaries \b are not used in this regex

### Back-references

Back-references in regular expressions (regex) refer to previously captured groups within the same regex pattern. They allow you to use the text matched and captured by one group later in the pattern for comparison or repetition. 

Back-references are not used in this regex. 

### Look-ahead and Look-behind

Look-ahead is used to make the character that immediately follows the look-ahead to be capatilized, while the look-behind is used to make the character that immediately follows the look-behind to be lower case. 

This is not used in this regex. 

## Author

Melissa Kalish is enrolled in the UC Berkeley Extension FSF Coding Bootcamp. I retired from my first career as a Detective Sergeant after 20 years in Law Enforcement. I am starting my second career in coding, cybersecurity and technology. 

Github Profile: https://gist.github.com/melkali42
