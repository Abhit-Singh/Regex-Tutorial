# Regex Tutorial (Email Address Regex)

Regular Expressions, or RegEx, are helpful tools used across many programming languages to find a specified combination of characters. A RegEx allows the programmer to search for any variation of a string matching a pattern instead of being limited to a specific, or "literal", query. For example, in a large database with multiple email address entries, a RegEx pattern search of [any name]@[any domain].[any extension] will easily find all email addresses.

In addition to being powerful search tools, regular expressions can be applied to validate formatting (e.g. passwords and email address), perform quick replacements, and assist with string splitting.

## Summary

The regex I will be explaining in this gist will be one that you can use to match an email address, for example:

```
/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/
```

## Table of Contents

- [Regex Tutorial (Email Address Regex)](#regex-tutorial-email-address-regex)
  - [Summary](#summary)
  - [Table of Contents](#table-of-contents)
  - [Regex Components](#regex-components)
    - [Anchors](#anchors)
    - [Quantifiers](#quantifiers)
    - [Grouping Constructs](#grouping-constructs)
    - [Bracket Expressions](#bracket-expressions)
    - [Character Classes](#character-classes)
    - [The OR Operator](#the-or-operator)
    - [Flags](#flags)
    - [Character Escapes](#character-escapes)
  - [Author](#author)

## Regex Components

Here we go.

### Anchors

The anchors of a regex specify where the search begins and where it ends. This is done using the carat '^' character at the begining of the expression, and the dollar sign '$' character at the end of it.

- Example:
```
/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/
```
- This regular expression for matching an email address shows that the search starts with any letter between a and z, and ends with any letter between a and z between two and six characters long.

### Quantifiers

Quantifiers are characters that you can use to identify groups of metacharacters:

- the asterisk * searches for a match of 0 or more characters
- the plus sign + searches for a match of 1 or more characters
- the question mark ? searches for a match between 0 and 1 character
- using curly braces {} lets you search for a match within a certain range of characters. You can write this either as {min, max} or as {n}, with n specifying a number range.


### Grouping Constructs

You can use parentheses () as a way to group subexpressions together. you can use these groups later for better searching.

### Bracket Expressions

Brackets identify an exact character or set of characters to match when searching. Any individual character inside brackets will be matched, as well as any set of characters. These are referred to as "character classes".

- Example:

```
[abcd]
```

- This expression will match the letters "a" and "c" in the word "catch".

If you include the ^ character inside of your brackets at the start, this will specify characters NOT to be matched. This is also known as a negated character class.

- Example:

```
[^abcd]
```

- This will match any character that is NOT a, b, c, or d.

You can also specify character sets/ranges using a hyphen ("abcd" is the same as "a-d").

### Character Classes

| Character Class | Meaning |
| ----------- | ----------- |
| `a-z` | Match any letter within the range of lowercase a to lowercase z. |
| `0-9` | Match any number from 0 to 9. |
| `_` | Match literal underscores. |
| `\.` | Match literals dot (`.`).  Dots have special functions in regular expression.  The backslash (`\`) is used to escape the character. |
| `-` | Match literal hyphens. |
| `\d` | Match any digit from 0 to 9.  Effectively the same as using `0-9`. |
| `@` | Match literal at signs.  Found following the first parenthetical group in our email RegEx. |

### The OR Operator

The OR Operator is another name for the " | " character. you can use this in search groups such as what was discussed above, if you wish to alternate between characters in a search group.

- Example: "(s|t)he" will search for groupings that contain "s" OR "t", followed by "h", followed by "e". 


### Flags

Flags are additional modifiers that affect the search. There are six of these flags that are used in Javascript, such as:

- 'g' is used to return ALL instances of a search parameter
- 'i' is used to specify that a search parameter is case insensitive

### Character Escapes

The backslash '\' is used to do what is called "escaping characters". This is for when you want to search for a literal character, not use it as a search modifier.

- Example: The dot '.' is typically used to specify a search for any character. However, you can search for a literal dot if you write it as such:
```
/\./
```


## Author

My name is Abhit Singh and I am studying in a coding bootcamp.My main objective to learn from this course is to get a good grasp on both front end and back end.
Github- https://github.com/Abhit-Singh