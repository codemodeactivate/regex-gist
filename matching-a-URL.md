# Regex Tutorial: Matching a URL

In this tutorial, we'll break down a regular expression that is designed to match URLs. URLs are pervasive in digital content, and being able to reliably extract them using a regular expression can be a valuable tool for many tasks, from web scraping to data cleaning.

## Summary

The regular expression we're examining is ^(https?:\/\/)?([\da-z\.-]+)\.([a-z\.]{2,6})([\/\w \.-]*)*\/?$. This regex can match a wide range of URLs, from simple domain names to more complex URLs with multiple paths and parameters.
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
^ and $ are used to denote the start and end of a line, respectively. This regex matches URLs that are on a line by themselves.
### Quantifiers
?, +, * are quantifiers. ? means zero or one, + means one or more, and * means zero or more.
### Character Classes
[\da-z\.-] and [a-z\.]{2,6} are character classes. They match a sequence of alphanumeric characters, dots, or hyphens, and a sequence of lower-case letters or dots of length 2 to 6, respectively. For example, in www.example.com, [\da-z\.-]+ matches www.example, and [a-z\.]{2,6} matches com.
### Grouping and Capturing
Parentheses () are used for grouping and capturing. In this regex, there are several groups created for capturing the protocol, domain name, domain extension, and path. For example, in the URL https://www.example.com/path/to/file, (https?:\/\/)? captures https://, ([\da-z\.-]+) captures www.example, ([a-z\.]{2,6}) captures com, and ([\/\w \.-]*)* captures /path/to/file.
### Bracket Expressions
In this regex, bracket expressions are used in the character classes [\/\w \.-]* to match path and file names in the URL. For example, in the URL path /path/to/file, the bracket expression matches each segment between slashes, allowing for alphanumeric characters, underscores, dots, spaces, and hyphens.
### Greedy and Lazy Match
The * quantifier is greedy, meaning it will match as much as it can. This allows for the matching of long path segments in a URL. For example, in the URL http://www.example.com/path/to/file, ([\/\w \.-]*)* will greedily match the entire /path/to/file segment, not just /path.
## Author
This tutorial was created by [Jeff Zenko](https://github.com/codemodeactivate)
