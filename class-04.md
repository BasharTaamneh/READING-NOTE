# Links

**Writing Links**

Links are created using the \<a> element. Users can click on anything
between the opening \<a> tag and the closing \</a> tag. You specify
which page you want to link to using the href attribute.

The text between the opening
\<a> tag and closing \</a> tag
is known as link text. Where
possible, your link text should
explain where visitors will be
taken if they click on it (rather
than just saying "click here").
Below you can see the link to
IMDB that was created on the
previous page.

Many people navigate websites
by scanning the text for links.
Clear link text can help visitors
find what they want. This
will give them a more positive
impression of your site and may
encourage them to visit it for
longer. (It also helps people
using screen reader software.)

To write good link text, you can
think of words people might
use when searching for the
page that you are linking to.
(For example, rather than write
"places to stay" you could use
something more specific such as
"hotels in New York.")

![](https://d2h0cx97tjks2p.cloudfront.net/blogs/wp-content/uploads/sites/2/2020/06/Links-in-HTML.jpg)

**Opening Links in a New Window**

- *target*

If you want a link to open in a
new window, you can use the
target attribute on the opening
\<a> tag. The value of this
attribute should be _blank.

One of the most common
reasons a web page author
might want a link to be opened
in a new window is if it points to
another website. In such cases,
they hope the user will return
to the window containing their
site after finishing looking at the
other one.

Generally you should avoid
opening links in a new window,
but if you do, it is considered
good practice to inform users
that the link will open a new
window before they click on it.

\<a href="http://www.imdb.com" target="_blank"> Internet Movie Database</a> (opens in new window)

<a href="http://www.imdb.com" target="_blank"> Internet Movie Database</a> (opens in new window)


**Linking to a Specific Part of the Same Page**

At the top of a long page
you might want to add a list
of contents that links to the
corresponding sections lower
down. Or you might want to add
a link from part way down the
page back to the top of it to save
users from having to scroll back
to the top.

Before you can link to a specific
part of a page, you need to
identify the points in the page
that the link will go to. You do
this using the id attribute (which
can be used on every HTML
element). You can see that the
\<h1> and \<h2> elements in this
example have been given id
attributes that identify those
sections of the page.

The value of the id attribute
should start with a letter or an
underscore (not a number or
any other character) and, on a
single page, no two id attributes
should have the same value.

To link to an element that uses
an id attribute you use the \<a>
element again, but the value of
the href attribute starts with
the # symbol, followed by the
value of the id attribute of the
element you want to link to. In
this example, \<a href="#top">
links to the \<h1> element at
the top of the page whose id
attribute has a value of top.

## Summary

- Links are created using the \<a> element.
-  The \<a> element uses the href attribute to indicate
the page you are linking to.
- If you are linking to a page within your own site, it is
best to use relative links rather than qualified URLs.
-  You can create links to open email programs with an
email address in the "to" field.
- You can use the id attribute to target elements within
a page that can be linked to.

# Layout

*HTML Layout Elements*

HTML has several semantic elements that define the different parts of a web page:

HTML5 Semantic Elements	

\<header>
 - Defines a header for a document or a section
\<nav> 
- Defines a set of navigation links
\<section>
 - Defines a section in a document
\<article>
 - Defines an independent, self-contained content
\<aside> 
- Defines content aside from the content (like a sidebar)
\<footer>
 - Defines a footer for a document or a section
\<details> 
- Defines additional details that the user can open and close on demand
\<summary> -
 Defines a heading for the \<details> element


 *HTML Layout Techniques*

There are four different techniques to create multicolumn layouts. Each technique has its pros and cons:

- CSS framework
- CSS float property
- CSS flexbox
- CSS grid

# WHAT IS A FUNCTION?

Functions let you group a series of statements together to perform a
specific task. If different parts of a script repeat the same task, you can
reuse the function (rather than repeating the same set of st atements).

*JavaScript Function Syntax*

A JavaScript function is defined with the function keyword, followed by a name, followed by parentheses ().

Function names can contain letters, digits, underscores, and dollar signs (same rules as variables).

The parentheses may include parameter names separated by commas:
(parameter1, parameter2, ...)

The code to be executed, by the function, is placed inside curly brackets: {}


Function parameters are listed inside the parentheses () in the function definition.

Function arguments are the values received by the function when it is invoked.

Inside the function, the arguments (the parameters) behave as local variables.

*Function Invocation*

The code inside the function will execute when "something" invokes (calls) the function:

- When an event occurs (when a user clicks a button)
- When it is invoked (called) from JavaScript code
- Automatically (self invoked)

*Function Return*

When JavaScript reaches a return statement, the function will stop executing.

If the function was invoked from a statement, JavaScript will "return" to execute the code after the invoking statement.

Functions often compute a return value. The return value is "returned" back to the "caller":

*Why Functions?*

You can reuse code: Define the code once, and use it many times.

You can use the same code many times with different arguments, to produce different results.

![](https://i.stack.imgur.com/RH5Gl.png)


# Pair Programming Advantages

There are several compelling reasons you should consider this strategy:

- **Two heads are better than one.**
 If the driver encounters a hitch with the code, there will be two of them who’ll solve the problem.

- **More efficient.**
 Common thinking is that it slows down the project completion time because you are effectively putting two programmers to develop a single program, instead of having them work independently on two different programs. But studies have shown that two programmers working on the same program are only 15% slower than when these programmers work independently, rather than the presupposed 50% slow down.
- **Fewer coding mistakes.**
 Because there is another programmer looking over your work, it results in better code. In fact, an earlier study shows that it results in 15% fewer bugs than code written by solo programmers. Plus, it allows the driver to remain focus on the code being written while the other attends to external matters or interruption.
- **An effective way to share knowledge.**
 Code Fellows talks about how it could help programmers learn from their peers in this blog post. It would allow programmers to get instant face-to-face instruction, which is much better than online tutorials and faster than looking for resources on the Internet. Plus, you can learn things better from your partner, especially in areas that may be unfamiliar to you. Developers can also pick up best practices and better techniques from more advanced programmers. It can also facilitate mentoring relationships between two programmers.
- **Develops your staff’s interpersonal skills.**
 Collaborating on a single project helps your team to appreciate the value of communication and teamwork.
 
In sum, it helps your programmers learn from each other while coming up with programs and applications with better code quality and fewer bugs.