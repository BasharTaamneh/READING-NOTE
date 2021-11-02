# Automation 
## Python Regular Expression Tutorial

<br>

* Regular Expressions, often shortened as regex, are a sequence of characters used to check whether a pattern exists in a given text (string) or not. If you've ever used search engines, search and replace tools of word processors and text editors - you've already seen regular expressions in use. They are used at the server side to validate the format of email addresses or passwords during registration, used for parsing text data files to find, replace, or delete certain strings, etc. They help in manipulating textual data, which is often a prerequisite for data science projects involving text mining.

- In Python, regular expressions are supported by the re module. That means that if you want to start using them in your Python scripts, you have to import this module with the help of import:

```py
import re

```

- The `re` library in Python provides several functions that make it a skill worth mastering. You will see some of them closely in this tutorial.

## Basic Patterns: Ordinary Characters

- You can easily tackle many basic patterns in Python using ordinary characters. Ordinary characters are the simplest regular expressions. They match themselves exactly and do not have a special meaning in their regular expression syntax.

***Examples are 'A', 'a', 'X', '5'***
*Ordinary characters can be used to perform simple exact matches:*


```py
pattern = r"Cookie"
sequence = "Cookie"
if re.match(pattern, sequence):
    print("Match!")
else: print("Not a match!")

>>> Match!
```
Most alphabets and characters will match themselves, as you saw in the example.

The `match()` function returns a match object if the text matches the pattern. Otherwise, it returns` None`. The `re `module also contains several other functions, and you will learn some of them later on in the tutorial.

For now, let's focus on ordinary characters!

Do you notice the `r` at the start of the pattern `Cookie?`
This is called a raw string literal. It changes how the string literal is interpreted. Such literals are stored as they appear.

For example, `\` is just a backslash when prefixed with an `r` rather than being interpreted as an escape sequence. You will see what this means with special characters. Sometimes, the syntax involves backslash-escaped characters, and to prevent these characters from being interpreted as escape sequences; you use the raw `r` prefix.

**TIP**: You don't actually need it for this example; however, it is a good practice to use it for consistency.

## Wild Card Characters: Special Characters

* Special characters are characters that do not match themselves as seen but have a special meaning when used in a regular expression. For simple understanding, they can be thought of as reserved metacharacters that denote something else and not what they look like.

Let's check out some examples to see the special characters in action...

But before you do, the examples below make use of two functions namely: search() and group().
With the search function, you scan through the given string/sequence, looking for the first location where the regular expression produces a match.
The group function returns the string matched by the re. You will see both these functions in more detail later.

- Back to the special characters now.

[` . `] - A period. Matches any single character except the newline character.

```py
re.search(r'Co.k.e', 'Cookie').group()

>>> 'Cookie'
```

[` ^ `]- A caret. Matches the start of the string.

This is helpful if you want to make sure a document/sentence starts with certain characters.

```py 
re.search(r'^Eat', "Eat cake!").group()

## However, the code below will not give the same result. Try it for yourself:
# re.search(r'^eat', "Let's eat cake!").group()

>>> 'Eat'
```

[`$`] - Matches the end of string.

This is helpful if you want to make sure a document/sentence ends with certain characters.

```py
re.search(r'cake$', "Cake! Let's eat cake").group()

## The next search will return the NONE value, try it:
# re.search(r'cake$', "Let's get some cake on our way home!").group()

>>> 'cake'

```
`[abc]` - Matches a or b or c.
`[a-zA-Z0-9]` - Matches any letter from `(a to z) ` or  `(A to Z)` or  `(0 to 9)`.

**TIP**: Characters that are not within a range can be matched by complementing the set. If the first character of the set is ^, all the characters that are not in the set will be matched.

```py
re.search(r'[0-6]', 'Number: 5').group()

>>>'5'
## Matches any character except 5
re.search(r'Number: [^5]', 'Number: 0').group()

## This will not match and hence a NONE value will be returned
#re.search(r'Number: [^5]', 'Number: 5').group()

>>>'Number: 0'

```

[`\`] - Backslash. Perhaps, the most diverse metacharacter!!

If the character following the backslash is a recognized escape character, then the special meaning of the term is taken (Scenario 1)
Else if the character following the `\` is not a recognized escape character, then the `\` is treated like any other character and passed through (Scenario 2).
`\` can be used in front of all the metacharacters to remove their special meaning (Scenario 3).

```py

## (Scenario 1) This treats '\s' as an escape character, '\s' defines a space
re.search(r'Not a\sregular character', 'Not a regular character').group()

>>> 'Not a regular character'

## (Scenario 2) '\' is treated as an ordinary character, because '\r' is not a recognized escape character
re.search(r'Just a \regular character', 'Just a \regular character').group()

>>> 'Just a \regular character'

## (Scenario 3) '\s' is escaped using an extra `\` so its interpreted as a literal string '\s'
re.search(r'Just a \\sregular character', 'Just a \sregular character').group()

>>> 'Just a \\sregular character'

```

`\w` - Lowercase 'w'. Matches any single letter, digit, or underscore.

`\W `- Uppercase 'W'. Matches any character not part of \w (lowercase w).

`\s` - Lowercase 's'. Matches a single whitespace character like: space, newline, tab, return.

`\S` - Uppercase 'S'. Matches any character not part of \s (lowercase s).

`\d `- Lowercase d. Matches decimal digit 0-9.

`\D` - Uppercase d. Matches any character that is not a decimal digit.

`\t` - Lowercase t. Matches tab.

`\n` - Lowercase n. Matches newline.

`\r` - Lowercase r. Matches return.

`\A `- Uppercase a. Matches only at the start of the string. 
Works across multiple lines as well.

`\Z `- Uppercase z. Matches only at the end of the string.

**TIP:** ^ and \A are effectively the same, and so are $ and \Z. Except when dealing with MULTILINE mode. Learn more about it in the flags section.

`\b` - Lowercase b. Matches only the beginning or end of the word.

## Repetitions

`*` It becomes quite tedious if you are looking to find long patterns in a sequence. Fortunately, the re module handles repetitions using the following special characters:

`+` - Checks if the preceding character appears one or more times starting from that position.

`*` - Checks if the preceding character appears zero or more times starting from that position.

`?` - Checks if the preceding character appears exactly zero or one time starting from that position.

`{x} `- Repeat exactly x number of times.

`{x,}` - Repeat at least x times or more.

`{x, y}` - Repeat at least x times but no more than y times.


## Summary table

```py

Character(s)	   		   		What it does
###################################################################################################
.	      A period. Matches any single character except the newline character.	   		   		

^	   	A caret. Matches a pattern at the start of the string.

\A	   		Uppercase A. Matches only at the start of the string.

$		   	Dollar sign. Matches the end of the string.

\Z		   	Uppercase Z. Matches only at the end of the string.

[ ]		   	Matches the set of characters you specify within it.

\		   	∙ If the character following the backslash is a recognized escape character, then the special meaning of the term is taken.
	   		   		   	
∙ 	   	Else the backslash () is treated like any other character and passed through.

∙ 	   	It can be used in front of all the metacharacters to remove their special meaning.

\w	   		Lowercase w. Matches any single letter, digit, or underscore.

\W	   		Uppercase W. Matches any character not part of \w (lowercase w).

\s	   		Lowercase s. Matches a single whitespace character like: space, newline, tab, return.

\S	   		Uppercase S. Matches any character not part of \s (lowercase s).

\d		   	Lowercase d. Matches decimal digit 0-9.

\D		   	Uppercase D. Matches any character that is not a decimal digit.

\t	   		Lowercase t. Matches tab.

\n		   	Lowercase n. Matches newline.

\r	   		Lowercase r. Matches return.

\b	   		Lowercase b. Matches only the beginning or end of the word.

+		   	Checks if the preceding character appears one or more times.

*		   	Checks if the preceding character appears zero or more times.

?		   	∙ Checks if the preceding character appears exactly zero or one time.

∙ 	   	Specifies a non-greedy version of +, *

{ }		   	Checks for an explicit number of times.

( )		   	Creates a group when performing matches.

< >	   		Creates a named group when performing matches.

```