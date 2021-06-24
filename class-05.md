# HTML Images; CSS Color & Text
## Images

**Adding Images**
- \<img> images.html HTML
To add an image into the page
you need to use an \<img>
element. This is an empty
element (which means there is
no closing tag). It must carry the
following two attributes:

*src*

This tells the browser where
it can find the image file. This
will usually be a relative URL
pointing to an image on your
own site. (Here you can see that
the images are in a child folder
called images — relative URLs
were covered on pages 83-84).

*alt*

This provides a text description
of the image which describes the
image if you cannot see it.


*title*

You can also use the title
attribute with the \<img> element
to provide additional information
about the image. Most browsers
will display the content of this
attribute in a tootip when the
user hovers over the image.

The text used in the alt attribute
is often referred to as alt text.
It should give an accurate
description of the image content
so it can be understood by
screen reader software (used by
people with visual impairments)
and search engines.

If the image is just to make a
page look more attractive (and
it has no meaning, such as a
graphic dividing line), then the
alt attribute should still be used
but the quotes should be left
empty.

**Height & Width of Images**

- You will also often see an \<img>
element use two other attributes
that specify its size:

- height

This specifies the height of the
image in pixels.

- width

This specifies the width of the
image in pixels.
Images often take longer to
load than the HTML code that
makes up the rest of the page.
It is, therefore, a good idea to
specify the size of the image
so that the browser can render
the rest of the text on the page
while leaving the right amount of
space for the image that is still
loading.

**Aligning Images Horizontally**

- align

The align attribute was
commonly used to indicate how
the other parts of a page should
flow around an image. It has
been removed from HTML5
and new websites should use
CSS to control the alignment of
images 
I have discussed it here because
you are likely to come across
it if you look at older code, and
because some visual editors still
insert this attribute when you
indicate how an image should be
aligned.
The align attribute can take
these horizontal values:

*left*

This aligns the image to the left
(allowing text to flow around its
right-hand side).

*right*

This aligns the image to the right
(allowing text to flow around its
left-hand side).

*top*

This aligns the first line of the
surrounding text with the top of
the image.

*middle*

This aligns the first line of the
surrounding text with the middle
of the image.

*bottom*

This aligns the first line of the
surrounding text with the bottom
of the image.

**Three Rules for Creating Images**


1. Save images in
the right format

- Websites mainly use images in
jpeg, gif, or png format. If you
choose the wrong image
format then your image might
not look as sharp as it should
and can make the web page
slower to load.

2. Save images at
the right size

- You should save the image at
the same width and height it will
appear on the website. If
the image is smaller than the
width or height that you have
specified, the image can be
distorted and stretched. If the
image is larger than the width
and height if you have specified,
the image will take longer to
display on the page.

3. Use the correct
resolution

- Computer screens are made up
of dots known as pixels. Images
used on the web are also made
up of tiny dots. Resolution refers
to the number of dots per inch,
and most computer screens only
show web pages at 72 pixels
per inch. So saving images at
a higher resolution results in
images that are larger than
necessary and take longer to
download.

**Fi gure and Fi gure Caption**

*\<figure>*

Images often come with
captions. HTML5 has introduced
a new \<figure> element to
contain images and their caption
so that the two are associated.
You can have more than one
image inside the \<figure>
element as long as they all share
the same caption.

*\<figcaption>*

The \<figcaption> element has
been added to HTML5 in order
to allow web page authors to add
a caption to an image.
Before these elements were
created there was no way to
associate an \<img> element with
its caption.
Older browsers that do not
understand HTML5 elements
simply ignore the new elements
and display the content of them.

## Color

**Foreground Color**

The color property allows you
to specify the color of text inside
an element. You can specify any
color in CSS in one of three ways:

- rgb values

These express colors in terms
of how much red, green and
blue are used to make it up. For
example: rgb(100,100,90)

- hex codes

These are six-digit codes that
represent the amount of red,
green and blue in a color,
preceded by a pound or hash #
sign. For example: #ee3e80

- color names

There are 147 predefined color
names that are recognized
by browsers. For example:
DarkCyan
We look at these three different
ways of specifying colors on the
next double-page spread.
CSS3 has also introduced
another way to specify colors
called HSLA,

Foreground Color
color
Above each CSS rule in this
example you can see how CSS
allows you to add comments
to your CSS files. Anything
between the /* symbols and
the */ symbols will not be
interpreted by the browser.

They are shown in grey above.
The use of comments can help
you to understand a CSS file
(and organise it, by splitting a
long document into sections).
Here, we have used comments
to indicate which method is used
to specify each of the different
types of colors.

- background-color

CSS treats each HTML element
as if it appears in a box, and the
background-color property
sets the color of the background
for that box.
You can specify your choice of
background color in the same
three ways you can specify
foreground colors: RGB values,
hex codes, and color names.

If you do not specify a
background color, then the
background is transparent.
By default, most browser
windows have a white
background, but browser users
can set a background color for
their windows, so if you want
to be sure that the background
is white you can use the
background-color property on
the \<body> element.

- opacity, rgba

CSS3 introduces the opacity
property which allows you to
specify the opacity of an element
and any of its child elements.
The value is a number between
0.0 and 1.0 (so a value of 0.5
is 50% opacity and 0.15 is 15%
opacity).

The CSS3 rgba property allows
you to specify a color, just like
you would with an RGB value,
but adds a fourth value to
indicate opacity. This value is
known as an alpha value and is
a number between 0.0 and 1.0
(so a value of 0.5 is 50% opacity
and 0.15 is 15% opacity). The
rgba value will only affect the
element on which it is applied
(not child elements).

Because some browsers will
not recognize RGBA colors, you
can offer a fallback so that they
display a solid color. If there are
two rules that apply to the same
element, the latter of the two
will take priority. To create the
fallback, you can specify a color
as a hex code, color name or
RGB value, followed by the rule
that specifies an RGBA value. 

If
the browser understands RGBA
colors it will use that rule. If it
doesn't, it will use the RGB value.


## Text

**Specifying Typefaces**

- font-family

The font-family property
allows you to specify the
typeface that should be used for
any text inside the element(s) to
which a CSS rule applies.
The value of this property is the
name of the typeface you want
to use. 

The people who are visiting
your site need the typeface you
have specified installed on their
computer in order for it to be
displayed.

You can specify a list of fonts
separated by commas so that,
if the user does not have your
first choice of typeface installed,
the browser can try to use an
alternative font from the list.

**Size of Type**

The font-size property enables
you to specify a size for the
font. There are several ways to
specify the size of a font. The
most common are:


👉Pixels

Pixels are commonly used
because they allow web
designers very precise control
over how much space their text
takes up. The number of pixels is
followed by the letters px.

👉percentages

The default size of text in
browsers is 16px. So a size of
75% would be the equivalent of
12px, and 200% would be 32px.
If you create a rule to make all
text inside the \<body> element
to be 75% of the default size (to
make it 12px), and then specify
another rule that indicates the
content of an element inside the
\<body> element should be 75%
size, it will be 9px (75% of the
12px font size).

👉ems

An em is equivalent to the width
of a letter m.



###### 18pt 
##### 24pt
#### 36pt
### 48pt
## 60pt
# 72pt Type Scales

 You may have noticed that programs such as
Word, Photoshop and InDesign offer the same
sizes of text.

**text-align**

The text-align property allows
you to control the alignment of
text. The property can take one
of four values:

- left

This indicates that the text
should be left-aligned.

- right

This indicates that the text
should be right-aligned.
center
This allows you to center text.

- justify

This indicates that every line in
a paragraph, except the last line,
should be set to take up the full
width of the containing box.
 
 **Summary** \*TEXT*

 - There are properties to control t XX he choice of font, size,
weight, style, and spacing.

- There is a limited choice of fonts that you can assume
most people will have installed.

- If you want to use a wider range of typefaces there are
several options, but you need to have the right license
to use them.

- You can control the space between lines of text,
individual letters, and words. Text can also be aligned
to the left, right, center, or justified. It can also be
indented.

- You can use pseudo-classes to change the style of an
element when a user hovers over or clicks on text, or
when they have visited a link.