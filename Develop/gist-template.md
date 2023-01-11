# Regex Tutorial

As a current web development student, I have created a Regex Tutorial explaining the definition and examples of how it used in regex that searches for emails. I also have included visual examples. 

## Summary

Regex or also regular expression is a sequence of characters that defines a search pattern. The patterns are used by many different programs and/ or programming languages to search and manipulate strings or look for a set of any characters. Regex is useful to help idenifty if any string conatins some sort of specific search pattern. It is also used to check if a string is vaild address format or replace parts, or to take out info from a string. Normally regex use a combintation of special characters and metacharacters to define the pattern to be attached. 

Example: `/^<([a-z]+)([^<]+)*(?:>(.*)<\/\1>|\s+\/>)$/`

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

1. Special Characters or Metacharacters: These are used to define the search pattern. example: `".","*","+","?","^","$","["," ]","{"," }","|","(", and ")"`.

2. Literal Characters: These are characters that you want match in the string. example: regular expression "goodbye" would match the string "goodbye", literally. `@` this literal character that must be present in the email address. which separates the username and domain name. 

3. `{3,}` Quantifiers: These are used to specify the amount of times based on the types amount. Indicates at least 3 occurances of the preceding character or group. Meaning that the TLD must have at least 3 letters ex: like.come, .net, etc.
4. "^" anchor is start of the string.

5. `[a-zA-Z0-9._%+-]` character set taht matches any one character that can either be a letter(lower or uppercase), number, dot,underscore, perecent sign, plus sign, or dash/hyphen. Making it the first part of the email address which contains a username and domain name. 
6. "[a-zA-Z0-9.-]" Another type of character set that matches any one character that is either a number, letter (lower or upper), a dot, or dash/hyphen. This is the second part of the email address and can contain the domain name and if possible subdomains. 
7. .- Escape character followed by a literal dot. this must be present in the email address, marking the end of the domain and stating the start of the toplevel domain (TLD). ex: gmail.com
8. "[a-zA-Z]" character set that matches any letter whether lower or uppercase. This will match with the (TLD).
9. "$" Anchor is the end of the string. Where the email can't have and trailing characters. 


### Anchors

^abcd$ (string starts in ^ and ends in $)

An anchor in a regex is a special metacharacter that is used to match the position of a character than by itself. There are some common anchors; `^` and `$` characters. The "^" is used for a position, the start of a new line. "$" is used the same as a position, but for the end of the line. When both are used together "^$" is means an empty line. Anchors are useful when you want to spot a patterns only a position at the start or the end, than anywhere within the string. 

### Quantifiers

Quantifiers in regular expressions are used to specify the number of times a element should be matched. When it comes to matching emails, quantifiers can be used to specify the number of times some elements should appear in the email-adress, like usrname, domain-name, and TLD toplevel domain.  A quantifier can be used to specify that the username in an email-address should contain at least one number, letter or special character.  this is achieved by using a quaitifers like "+" after the character set that includes the letters, numbers, special characters. 
ex: ^[a-zA-Z0-9._%+-]+@
 
It will match the start of the email address, and one or more letters, numbers, or special characters that can be used in the username. And a quantifier can be used to specify that the domain name should contain one or more charcters which can include letters, numbers, dots, or dash/hyphens. 
ex:  @[a-zA-Z0-9.-]+\.

A quantifier can be used to speicfy that the TLD of an email address shoudl conatin at least 2 letters to ensure it is properly vaild or in other words a a vaild email address. 
ex: [

### OR Operator

OR Operator in regular expressions allows you to specify a set of alternative patterns that allows a match can be found, represented by the pipe symbol  `|`. It can come in handy when you want to match multiple possible variations of an email address. you could use the OR Operator to match both .com and .co.uk TLD in the email address or also to macth differnt formats of the email addresses. 
ex: ^[a-zA-Z0-9._%+-]+@[a-zA-Z0-9.-]+\.(com|co\.uk)$
The OR Operator will match email addresses that have the same username, domian name, on either the .com or ,co.uk. 


### Character Classes

A character class in a regular expession is a set of characters enclosed in a set of brackets, that can be used to match any one of the characters within the class. Good tool for matching a ceratin set of characters. When it comes to matching email addresses, this can be used to specify the set of characters that are allwoed in certain parts of the email address. 

 ex: ^[a-zA-Z0-9._]+  -specifies that the username in an email can only contain letetrs, numbers, dots, and underscores. 

 ex: ^[a-zA-Z0-9._%+-]+@[a-zA-Z0-9.-]+  -character classes to match a range of characters suing a range idicator. "-"

 You cnan also use negated character classes to match any character that is not wihtin a specfic set of characters. Negated character class is defined by placing a "6" after the opening square bracket. "[^abc]".

 ex: ^[^@]+  -this will match any string that doesn't have "@".

### Flags

In regular expression, certain flags can be used to control how the pattern matching works. there area few common flags:

-'re.IGNORECASE' : This flag causes the regex to be case-insensitive, meaning that uppercase and lowercase letters are treated the same. 
-'re.MULTILINE': This flag treat the begining of the string (^) and end of the string ($) with respect of each line, this means that in a mulitline string they will match string they will match the begining and end of each line, not only the begining and end of the string. 
-'re.DOTALL':  This flag makes the dot meta character(.) match newlinw characters, use it to match everything.
-'re.VERBOSE' : This flag allows you write regex pattern.

### Grouping and Capturing

Grouping and Capturing in regular expression refer in the ablility to group a regex pattern set and capture the matched text as a single unit. Grouping us done by using parentheses '()' and same with combination but with a capturing group '(?P<name>)' or '(?P=name)', this helps us refer back to the named or numbered capturing group. 

### Bracket Expressions

Bracket Expressions in regular expression are a way to match any one of a set of characters, which are defined using square brackets "[]'. Bracket expressions are a powerful feature of regex, providing a way to match a wide range of characters. 

ex: email_regex = r"[a-zA-Z0-9._%+-]+@[a-zA-Z0-9.-]+\.(com|net)"

### Greedy and Lazy Match

Greedy and Lazy Match in a regular expression applies to quantifiers that specify how many times a character or group should be matched. Quantifiers in regex are "greedy", meaning that they will match as many characters as possible while still allowing the pattern to match still. "Lazy" matching is done by adding a '?' after the quantifier making it match the least amount of characters that still allow regex pattern to match. 

greedy ex: email_regex = r"\w+@\w+\.com"
lazy ex: email_regex = r"\w+?@\w+?\.com"

### Boundaries

In regular expression boundaries are special characters that specify the start or end of a word, line, or string. Boundaries are used to match specific positions within a text rather than matching specific characters. `\b`: This boundary character matches the position between a word to non-word character. In other words the start/end string. `^`: This boundary character matches the position at the start of a line. `$`: This boundary ch. matches the position at the end of the string. You are allowed to combine them to match more complex patterns, or can use `\A` (start of string) or `\Z` (end of string). You can use boundary characters to ensure that the match starts or ends in a specific place. 

`\b`: email_regex = r"\b\w+@\w+\.com\b"
`^`: email_regex = r"^\w+@\w+\.com"
`$`: email_regex = r"\w+@\w+\.com$"
### Back-references

In regular expression Back-references are the a way to refer back to a pervious matched group in the pattern. Which are defined using a blackslash `\` followed by the group number. Back-references are useful whne trying to match any kind of patterns that might repeat, or to validate that some parts of  a match set are similar in some way. Being able to use information that you've already used in the regex pattern. 

blackslash ex: email_regex = r"([a-zA-Z0-9._%+-]+)@([a-zA-Z0-9.-]+)\.\2"
### Look-ahead and Look-behind

Look-ahead and Look-behind are special constructs that allow you to assert a certain pattern without having the offical final match. Defined by using `()` and `?=` lastly `?<=`.  Lookahead allows you to check if a kind of pattern is followed by another pattern but without having the final match, `(?=...)`. Lookbehind allows you check if a kind of pattern has come before by any other patterns who doesn't include the final match, `(?<=...)`.

 Look-ahead ex: email_regex = r"\w+@\w+(?=\.com)"
 Look-behind ex: email_regex = r"(?<=\w+)@\w+\.com"

## Author
 Salma Gonzalez: SMU bootcamp

My Github: https://github.com/gsalma99