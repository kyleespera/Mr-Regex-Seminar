# Tutorial: How to Match URLs Using Regex
This tutorial explains how to match a URL using regular expressions (regex).

## Summary
This section breaks down the regular expression that matches a URL.
Please refer to the reference section to understand what the various components mean.
Here is the regex for matching a URL:

/^(https?:\/\/)?([\da-z\.-]+)\.([a-z\.]{2,6})([\/\w \.-]*)*\/?$/

## Step One: Understanding Anchors
Firstly, we identify the anchors to delineate the start and end of our regex:

Start: ^(https?:\/\/)?([\da-z\.-]+)\.([a-z\.]{2,6})([\/\w \.-]*)*\/?
End: The end of our regex pattern is implied by the anchor $.

## Step Two: Deconstructing the Pattern
We break down the regex into various components, including capturing groups and literals:

(https?:\/\/)?
([\da-z\.-]+)
\.
([a-z\.]{2,6})
([\/\w \.-]*)*
\/?
## Step Three: Detailed Explanation of Each Component
(https?:\/\/)?
https represents the literal characters for 'https'.
? following https? indicates a match for 'http' with an optional 's'.
:\/\/ includes literal characters and an escape sequence for '://'.
This segment matches the protocol part of a URL, specifically 'http://' or 'https://'.
([\da-z\.-]+)
The square brackets [ ] define a character class to match any character listed within.
\d matches any single digit.
a-z matches any lowercase letter within the range a to z.
\. and - are escaped period and literal dash respectively, included in the character class.
The + quantifier requires at least one or more of the characters specified.
This part matches the domain name, which may consist of digits, letters, periods, or dashes.
\.
The escaped \. represents a literal period.
This dot typically separates the domain name from the domain extension.
([a-z\.]{2,6})
Another character class [ ] matching lowercase letters and a period.
{2,6} quantifier matches a string of characters with a length between 2 to 6.
This portion matches the domain extension, like '.com', '.info', etc.
([\/\w \.-]*)*
The character class includes an escaped slash \/, alphanumeric character plus underscore \w, space , period, and dash.
The * quantifier allows for zero or more occurrences of these characters.
This segment can match additional URL path, query parameters, or fragments.
\/?
An escaped slash \/ is used to optionally match the trailing slash at the end of a URL.
The ? quantifier matches zero or one occurrence of the preceding element.
This allows for URLs that end with or without a slash.
## Expanded RegEx Reference Guide
### Literal Characters
Definition: Literal characters are matched exactly as they appear.
Example: The regex a matches the character 'a'.
Ranges: Defined using -. For instance, [a-z] includes all lowercase alphabetic characters.
### Escape Operator
Definition: The escape character \ indicates that the subsequent character has a special meaning or should be treated as a literal if it is a reserved character.
Example: The regex \. is used to match a literal period (.) instead of any character.
### Anchors
Purpose: Anchors denote the position in the input string relative to which the match must occur.
^ - Start of a string.
$ - End of a string.

### Quantifiers
Function: Quantifiers specify how many instances of a character, group, or character class must be present for a match.
* - Matches zero or more times.
+ - Matches one or more times.
? - Matches zero or one time.
{n} - Matches exactly n times.
{n,} - Matches at least n times.
{n,m} - Matches between n and m times.
### OR Operator
Usage: The pipe | allows for the matching of either the expression before or after it.
Example: cat|dog matches either "cat" or "dog".
### Character Classes
Concept: Character classes provide a shorthand for matching predefined sets of characters.
. - Matches any character except newline (\n).
\d - Matches any digit, equivalent to [0-9].
\w - Matches any word character, equivalent to [A-Za-z0-9_].
\s - Matches any whitespace character including spaces, tabs, and line breaks.
### Flags
Definition: Flags alter how the search is performed.
g - Global search (matches all occurrences).
i - Case-insensitive search.
m - Multi-line search (anchors apply to the start and end of each line).
### Grouping and Capturing
Mechanism: Parentheses () are used to create a subexpression that can be matched and captured for later use.
### Bracket Expressions
Description: Brackets [] are used to define a set of characters to match any one character from the set.
### Greedy and Lazy Match
Greedy: By default, quantifiers are greedy, meaning they match as much text as possible.
Lazy: Adding a ? after a quantifier makes it lazy, meaning it matches as little text as possible.
### Boundaries
Word Boundary (\b): A position between a word character and a non-word character.
Non-Word Boundary (\B): A position between two word characters or two non-word characters.
### Back-references
Utility: Back-references \n match the same text as previously matched by the nth capturing group.
Example: (\w)a\1 matches "baba" or "caca" where \1 refers to the first group.
### Look-ahead and Look-behind
Look-ahead (?=...): Asserts that what immediately follows the current position in the string is the specified pattern.
Look-behind (?<=...): Asserts that what immediately precedes the current position in the string is the specified pattern.


## Author
GitHub - https://github.com/kyleespera

