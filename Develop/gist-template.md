# Title (replace with your title)

Introductory paragraph (replace this with your text)

## Summary

Regex or also regular expression is a sequence of characters that defines a search pattern. The patterns are used by many different programs and/ or programming languages to search and manipulate strings or look for a set of any characters. Regex is useful to help idenifty if any string conatins some sort of specific search pattern. It is also used to check if a string is vaild address format or replace parts, or to take out info from a string. Normally regex use a combintation of special characters and metacharacters to define the pattern to be attached. 

Example: /^<([a-z]+)([^<]+)*(?:>(.*)<\/\1>|\s+\/>)$/

As you scroll below the content will explain what each section is used for and connected to regex for an email. 

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

Regex is made up of several different components;

1. Special Characters or Metacharacters: These are used to define the search pattern. example: ".","*","+","?","^","$","["," ]","{"," }","|","(", and ")".

2. Literal Characters: These are characters that you want match in the string. example: regular expression "goodbye" would match the string "goodbye", literally. "@" this literal character that must be present in the email address. which separates the username and domain name. 

3. Quantifiers: These are used to specify the amount of times based on the types amount. example: the regular expression "s{4}" would match the string into "ssss" and the "+" used after the character or set s

### Anchors

^abcd$ (string starts in ^ and ends in $)

An anchor in a regex is a special metacharacter that is used to match the position of a character than by itself. There are some common anchors; "^" and "$" characters. The "^" is used for a position, the start of a new line. "$" is used the same as a position, but for the end of the line. When both are used together "^$" is means an empty line. Anchors are useful when you want to spot a patterns only a position at the start or the end, than anywhere within the string. 

### Quantifiers

### OR Operator

### Character Classes

### Flags

### Grouping and Capturing

### Bracket Expressions

### Greedy and Lazy Match

### Boundaries

### Back-references

### Look-ahead and Look-behind

## Author

A short section about the author with a link to the author's GitHub profile (replace with your information and a link to your profile)
