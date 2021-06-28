# HTML Tables; JS Constructor Functions

## Tables

**How to create tables?**

*Basic Table Structure*

### \<table>


The \<table> element is used
to create a table. The contents
of the table are written out row
by row.

- \<tr>

You indicate the start of each
row using the opening \<tr> tag.
(The tr stands for table row.)
It is followed by one or more
\<td> elements (one for each cell
in that row).
At the end of the row you use a
closing \</tr> tag.

- \<td>

Each cell of a table is
represented using a \<td>
element. (The td stands for
table data.)
At the end of each cell you use a
closing \</td> tag.


- \<th>

The \<th> element is used just
like the \<td> element but its
purpose is to represent the
heading for either a column or
a row. (The th stands for table
heading.)

Even if a cell has no content,
you should still use a \<td> or
\<th> element to represent
the presence of an empty cell
otherwise the table will not
render correctly. (The first cell
in the first row of this example
shows an empty cell.)

Using \<th> elements for
headings helps people who
use screen readers, improves
the ability for search engines
to index your pages, and also
enables you to control the
appearance of tables better
when you start to use CSS.



- Spanning ColumnS

Sometimes you may need the
entries in a table to stretch
across more than one column.

The colspan attribute can be
used on a \<th> or \<td> element
and indicates how many columns
that cell should run across.

In the example on the right
you can see a timetable with
five columns; the first column
contains the heading for that
row (the day), the remaining four
represent one hour time slots.

If you look at the table cell that
contains the words 'Geography'
you will see that the value of the
colspan attribute is 2, which
indicates that the cell should run
across two columns. In the third
row, 'Gym' runs across three
columns.



- Spanning ColumnS

Sometimes you may need the
entries in a table to stretch
across more than one column.

The colspan attribute can be
used on a \<th> or \<td> element
and indicates how many columns
that cell should run across.

In the example on the right
you can see a timetable with
five columns; the first column
contains the heading for that
row (the day), the remaining four
represent one hour time slots.

If you look at the table cell that
contains the words 'Geography'
you will see that the value of the
colspan attribute is 2, which
indicates that the cell should run
across two columns. In the third
row, 'Gym' runs across three
columns.



- Spanning Rows

You may also need entries in
a table to stretch down across
more than one row.

The rowspan attribute can be
used on a \<th> or \<td> element
to indicate how many rows a cell
should span down the table.

In the example on the left you
can see that ABC is showing a
movie from 6pm - 8pm, whereas
the BBC and CNN channels are
both showing two programs
during this time period (each of
which lasts one hour).

- Long Tables

There are three elements that
help distinguish between the
main content of the table and
the first and last rows (which can
contain different content).

These elements help people
who use screen readers and also
allow you to style these sections
in a different manner than the
rest of the table (as you will see
when you learn about CSS).

\<thead>

The headings of the table should
sit inside the <thead> element.

\<tbody>

The body should sit inside the
\<tbody> element.

\<tfoot>

The footer belongs inside the
\<tfoot> element.


*Summary* Tables

1. The \<table> element is used to add tables to a web
page.

2. A table is drawn out row by row. Each row is created
with the \<tr> element.

3. Inside each row there are a number of cells
represented by the \<td> element (or \<th> if it is a
header).

4. You can make cells of a table span more than one row
or column using the rowspan and colspan attributes.

5. For long tables you can split the table into a \<thead>,
\<tbody>, and \<tfoot>.

## WHAT IS A FUNCTION?

Functions let you group a series of statements together to perform a
specific task. If different parts of a script repeat the same task, you can
reuse the function (rather than repeating the same set of st atements).

-----------------------------------------------------

A JavaScript function is a block of code designed to perform a particular task.

A JavaScript function is executed when "something" invokes it (calls it).

 defined with the function keyword, followed by a name, followed by parentheses ().

Function names can contain letters, digits, underscores, and dollar signs (same rules as variables).

The parentheses may include parameter names separated by commas:
(parameter1, parameter2, ...)

The code to be executed, by the function, is placed inside curly brackets: {}

Function parameters are listed inside the parentheses () in the function definition.

Function arguments are the values received by the function when it is invoked.

Inside the function, the arguments (the parameters) behave as local variables.

- Function Invocation

The code inside the function will execute when "something" invokes (calls) the function:

When an event occurs (when a user clicks a button)
When it is invoked (called) from JavaScript code
Automatically (self invoked)

- Function Return

When JavaScript reaches a return statement, the function will stop executing.

If the function was invoked from a statement, JavaScript will "return" to execute the code after the invoking statement.

Functions often compute a return value. The return value is "returned" back to the "caller"

## Objects

In real life, a car is an object.

A car has properties like weight and color, and methods like start and stop:

All cars have the same properties, but the property values differ from car to car.

All cars have the same methods, but the methods are performed at different times.

Objects are variables too. But objects can contain many values.
The values are written as name:value pairs (name and value separated by a colon).

You define (and create) a JavaScript object with an object literal:

The name:values pairs in JavaScript objects are called properties:

You can access object properties in two ways:

 -----------------------------------------
objectName.propertyName

or

objectName["propertyName"]

----------------------------------------

- Object Methods

Objects can also have methods.

Methods are actions that can be performed on objects.

Methods are stored in properties as function definitions.


- The this Keyword

In a function definition, this refers to the "owner" of the function.

In the example above, this is the person object that "owns" the fullName function.

In other words, this.firstName means the firstName property of this object.


You access an object method with the following syntax:

objectName.methodName()

*Do Not Declare Strings, Numbers, and Booleans as Objects!*

When a JavaScript variable is declared with the keyword "new", the variable is created as an object:

Avoid String, Number, and Boolean objects. They complicate your code and slow down execution speed.

