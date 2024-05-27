# URL Validation with Regular Expressions

Regular expressions (regex) are powerful tools used for pattern matching and text manipulation. In this tutorial, we'll dive into a specific regex pattern designed to validate URLs. By the end of this tutorial, you'll understand how each component of the regex works and be able to apply this knowledge to your projects.

## Summary

This tutorial explores a regex pattern for validating URLs, explaining each component's purpose and functionality. The regex pattern we'll be discussing is:

```
/^(https?:\/\/)?([\da-z\.-]+)\.([a-z\.]{2,6})([\/\w \.-]*)*\/?$/
```

## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [Character Classes](#character-classes)
- [Grouping and Capturing](#grouping-and-capturing)
- [Bracket Expressions](#bracket-expressions)
- [Greedy and Lazy Match](#greedy-and-lazy-match)
- [Boundaries](#boundaries)
  

## Regex Components

### Anchors
Anchors are used to specify the position within the string where the match should occur.

- `^` Asserts the position at the start of the string.
- `$` Asserts the position at the end of the string.
In our regex:
```
/^(https?:\/\/)?...\/?$/
```
- `^` ensures the match starts at the beginning of the string.
- `$` ensures the match ends at the end of the string.

### Quantifiers
Quantifiers specify how many instances of a character, group, or character class must be present for a match.
- `?` Matches 0 or 1 time.
- `*` Matches 0 or more times.
In our regex:
```
/^(https?:\/\/)?...([\/\w \.-]*)*\/?$/
```
- `https?` The `?` makes the `s` optional, allowing for both `http` and `https`.
- `([\/\w \.-]*)*` The `*` allows for zero or more occurrences of the preceding group.

### Character Classes
Character classes match any one of a set of characters.

- `[\da-z\.-]` Matches any digit `\d`, lowercase letter `a-z`, period `.`, or hyphen `-`.
- `[a-z\.]` Matches any lowercase letter or period.
In our regex:
```
/^(https?:\/\/)?([\da-z\.-]+)\.([a-z\.]{2,6}).../
```
- `[\da-z\.-]` Matches the domain part of the URL.
- `[a-z\.]{2,6}` Matches the top-level domain like `.com`, `.org`, etc.

### Grouping and Capturing
Parentheses are used for grouping and capturing.

- `(...)` Groups multiple tokens together and captures the match for later use.
In our regex:
```
/^(https?:\/\/)?([\da-z\.-]+)\.([a-z\.]{2,6})([\/\w \.-]*)*\/?$/
```
- `(https?:\/\/)?` Optionally captures the protocol part.
- `([\da-z\.-]+)` Captures the domain name.
- `([a-z\.]{2,6})` Captures the TLD.
- `([\/\w \.-]*)*` Captures the path.

### Bracket Expressions
Bracket expressions match any one of the enclosed characters.

- `[...]` Matches any single character within the brackets.
In our regex:
```
/^(https?:\/\/)?([\da-z\.-]+)\.([a-z\.]{2,6})([\/\w \.-]*)*\/?$/
```
- `[\da-z\.-]` Matches digits, lowercase letters, periods, or hyphens.
- `[\/\w \.-]` Matches forward slashes, word characters, spaces, periods, or hyphens.

### Greedy and Lazy Match
Greedy matches try to match as much text as possible, while lazy matches try to match as little as possible.

- Greedy: `*`, `+`, `?`
- Lazy: `*?`, `+?`, `??`
In our regex:
```
/^(https?:\/\/)?([\da-z\.-]+)\.([a-z\.]{2,6})([\/\w \.-]*)*\/?$/
```
All quantifiers in this regex are greedy, aiming to match as much text as possible.

### Boundaries
Boundaries help to ensure that the regex matches are in the correct positions within the text.

- `^` Start of string.
- `$` End of string.
In our regex:
```
/^(https?:\/\/)?...\/?$/
```
`^` and `$` ensure that the entire string matches the URL pattern from start to finish.

## Author

This tutorial was written by Braedan Beecher

Please consider viewing other projects I have worked on at my [GitHub Profile](https://github.com/Buk1li)
