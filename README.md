# RegEx-Tutorial

What is RegEx you might be asking? 

RegEx! The epitome of validating text in javascript (and maybe other languages! We're going over javascript, but you can choose a different flavor language too!). If you need a validation, then RegEx is for you! RegEx, meaning regular expressions, are used to match character combinations in strings. But chel - What does that mean?! 
It means that you can make a sure a string in your javascript includes certain characters! An email for example, should ALWAYS have an @, ., and a .com/.org/.uk etc. so what if there was an easy way for you to verify that your users typed in a valid email address? by using RegEx! Take a look at this tutorial to learn more! ~~ 

## Summary

RegEx is short for "regular expressions" and according to MDN Documetation, "_Regular expressions are patterns used to match character combinations in strings._" these RegEx can be used in a variety of different methods in javascript, including but not limited to  exec() and test() (methods of RegExp), match(), matchAll(), replace(), replaceAll(), search(), and split() (methods for Strings). You basically make a combination of characters that can tell

regex for verifying an email : `/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`

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

Are primarily found as an end or beginning position in the string. This is primarily found in the form of ^ in the beginning, and $ in the end positions of an expression.

### Quantifiers

A quantifier is a character or group that specifies how often something can happen, or the length of characters, special and/or numbers it could be. An example would be {} which is used to specify a certain number. {1,9}, in the format of {min,max} The preceding item is matched at least min times, but not more than max times.

An example from our email would be the {2,6} towards the end of the string. 

`/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`

### Grouping Constructs
Parentheses are used to define the scope and precedence of the operators (among other uses). For example, gray|grey and gr(a|e)y are equivalent patterns which both describe the set of "gray" or "grey".
A displayed example from our email regex would be ([a-z0-9_\.-]+)
With regards to emails, there are a few "capture groups" utilized: email-name, email provider and domain.
These could be seen as the following: ([a-z0-9_\.-]+), ([\da-z\.-]+), ([a-z\.]{2,6}).  

`/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`

### Bracket Expressions
Bracket expressions can match a variety of things, or exclude a variety of things. In characters alone you can have a range for example [a-z] or you can have single letters like [aoize] and it will match either the range or the single letters. You can also mix and match, like so: [abcx-z]. please note that character excapes are not allowed in bracket expressions for the '-' special character. 

### Character Classes
The character class is the most basic regex concept after a literal match. It makes one small sequence of characters match a larger set of characters. For example, [A-Z] could stand for any uppercase letter in the English alphabet, and \d could mean any digit. 

A few other examples of character classes: 
\d : Matches any digit (Arabic numeral). Equivalent to [0-9]. For example, /\d/ or /[0-9]/ matches "2" in "B2 is the suite number".

\D:Matches any character that is not a digit (Arabic numeral). Equivalent to [^0-9]. For example, /\D/ or /[^0-9]/ matches "B" in "B2 is the suite number".

\w: Matches any alphanumeric character from the basic Latin alphabet, including the underscore. Equivalent to [A-Za-z0-9_]. For example, /\w/ matches "a" in "apple", "5" in "$5.28", "3" in "3D" and "m" in "Émanuel".

an example of the character class from our email example is in the very first set of brackets, [a-z0-9_\.-], you see the characters defined as a-z, meaing all lowerclass. 

`/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`

### The OR Operator

In order to talk about the OR Operator, we will look at the following code for matching a hex code.

6 no- hex code: 
/^#?([a-f0-9]{6})$/

3 no- hex code: 
/^#?([a-f0-9]{3})$/

what the code above will do is it will match where it starts with the # (because all hexcodes start with a hashtag), and then be followed up by either 6 numbers, or 3 numbers. 

[a-f0-9]{6} which will match a 6 character long string that contains a combination of a-f letters and 0-9 numbers.

[a-f0-9]{3} it will match a 3 character long string that contains a combination of a-f letters and 0-9 numbers.


### Flags
Flags are placed at the end of the pattern (after the last forward slash) and tell the regular expression parser how we want to search.

g : "global search" or "find all occurences"
i : "case insensitive" so find both CAT and cat
m : "multiline" will match your pattern over multiple lines

`/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`

Can you spot any flags in the email regex? 

Trick question, there are none. The examplss provided are not in the regex above. 

### Character Escapes

For using special characters, you need to put a backslash in front of it so that it makes it literal instead of special. example: /a\*b/ so it "escapes" the characer. 

## Author

Chel, a mostly front-end developer who isn't fond of backend developement, and got most of this information form wikepedia 

[Link to my GITHUB profile](www.github.com/Sea-Chels)

## Sources


[MDN Documentation](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_Expressions)
[RegEx Testing Website](https://regex101.com/)
[wikepedia Documentation](https://en.wikipedia.org/wiki/Regular_expression#Basic_concepts)

<!-- THEN I see a descriptive title and introductory paragraph explaining the purpose of the tutorial, a summary describing the regex featured in the tutorial, a table of contents linking to different sections that break down each component of the regex and explain what it does, and a section about the author with a link to the author’s GitHub profile
WHEN I click on the links in the table of contents
THEN I am taken to the corresponding sections of the tutorial
WHEN I read through each section of the tutorial
THEN I find a detailed explanation of what a specific component of the regex does
WHEN I reach the end of the tutorial
THEN I find a section about the author and a link to the author’s GitHub profile -->