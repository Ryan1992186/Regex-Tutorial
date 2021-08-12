# Regex-Tutorial

# Title Regex Tutorial
For this assignment we were asked to watch a brief video on regular expressions or (Regex) in order to learn more about regular expressions and their uses and functions within coding. 

## Summary
The regex code that I will be examining is the regex that is often most used with matching any patterns of text, regular expressions are often used to find matching patterns in text or data sets. The example that I observed in this tutorial video was a data set of phone #'s. 

321-555-4321 

out of a range of numbers consisting of. 

1234567890. 

\d\d\d.\d\d\d.

it would search the first 6 digits out of the phone # listed above and match/compare that pattern to the data set listed below it. I learned this is useful for searching potential strings or pieces of data that might corralate with eachother. 

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
.\$^{}|()[]?**+

### Anchors
An example that I found of a string anchor and a line anchor, a string anchor maybe used to find a specific word or phrase or set of number within a string either at the beginning or end. a few examples I found online include:

Example 1: ^. would match a in abc/ndef - string anchor.

line anchor is typically used if you have a string that consists of multiple different lines where instead of just searching one single character in a single string like you would with string anchors, this would search by multiple lines in a single string. 

Example 2: ^ will match after each line break, so ^. matches a and d in abc\ndef

### Quantifiers
We use quantifiers to specify how many times a character, group, or character class needs to be present in the input for a match to be found. A really good example of this I found through a microsoft word doc: https://docs.microsoft.com/en-us/dotnet/standard/base-types/quantifiers-in-regular-expressions

In the example they provided. 

string pattern = @"\b91*9*\b"; - \b starts the word boundary which must match a 9 followed by a zero or more 1 characters, and 9* must match zero or more 9 characters. and \b ends the word boundary search. 

string input = "99 95 919 929 9119 9219 999 9919 91119";

foreach (Match match in Regex.Matches(input, pattern))
   Console.WriteLine("'{0}' found at position {1}.", match.Value, match.Index);

// The example displays the following output:
//       '99' found at position 0.
//       '919' found at position 6.
//       '9119' found at position 14.
//       '999' found at position 24.
//       '91119' found at position 33.

I found this example interesting because it seemed like the more complex examples that were given on the document page, regex seems complicated until you realize it's nothing more than a way to compare data patterns. 

### Grouping Constructs
Grouping Constructs is typically used when regular expressions grow in complexity, to do this you can check multiple parts of a string to determine if different sections have different requirements. To do this you need paratheses (). Each expression in the parantheses is considered to be a 'subexpression'. When you place a part of a regular expression inside the paratheses. You can group it and add quantifiers to it. 

A good example of this would be finding a anchor tag in a HTML document. In order to do this you would use the expression below.

/(a href=)(["'])(.?)(["'])(.?)(</a>)/gmi

### Bracket Expressions
Brack expressions are tools for searching and selecting different types of data, they don't require a string to meet every single requirement in a patter. They only need one string, this means that [a-z0-9_-] searches for numeric characters and or sepcial symbols that are included within brackets. 

### Character Classes
Regex character classes are defined as a set of characters, any of them can occur in a input string to fufill the match. some common examples of these would be defined as below. 

Syntax	Description
.	Wildcard (matches any character)
\d	Matches any digit 0123456789
\w	Matches "word" (letters, digits, and _)
\W	Matches non-word characters
\t	Matches tab characters
\r	Matches return
\S	Matches non-whitespace
Citation	MIT.edu PDF

So as a example. /^[A-Z]{1}[\d]{3}\-[\d]{4}\-[\d]{4}$/gm

is the same thing as /^[A-Z]{1}[0-9]{3}\-[0-9]{4}\-[0-9]{4}$/gm

### The OR Operator
The OR operator or "|" in regex, tells the code to look for multiple sets of data but not mix. so in essense /^ocean|blue/gmi might find ocean is green, but might be blue. 

### Flags
Flags are there to make regex expressions more versatile, there are a total of six flags that can be used. 

/i for case-insensitive matching
/m Multi-line Search
/g which tells the engine to find all occurrences of pattern in one or many strings instead of stopping at first match only (/g stands for global)
/s allows . to match newline characters
/u tells the engine to treat a pattern sequence as a string of unicode characters
/d generates indices for substring matches

### Character Escapes
Character escapes within Regex are used to escape characters that might have some sort of special meaning. For example the open curly brackets are typically used as a indication of a quanitifer, but adding a \ before it means that you are seeking the character and not the beginning of another type of identifier. 

Slashes in your regex expression signifies ending one pattern and starting another. You never need these when searching strings with specific data and symbols within them because there is always only one instance per string that needs escaping. 

## Author
Ryan Hillier - Full Stack Web Development, enjoys reading and learning new coding languages, my main strengths I have yet to locate as I am still learning in progress, but in my spare time I am attempting to learn more Python, React, CSS, and Javascript. Always commited to learning more. 

For any questions, please feel free to contact me me at:

Ryan1992186@gmail.com
https://github.com/Ryan1992186