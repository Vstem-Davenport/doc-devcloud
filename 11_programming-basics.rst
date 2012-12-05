.. _programming_basics:

#############################
 Ruby Programming Concepts
############################# 

Executing Ruby
=============================

There are multiple ruby execution modes: script or program files (program.rb), 
interactive ruby commands (irb), and embedded ruby (script.erb).

Ruby Files
-----------------------------

.. sidebar:: Example Ruby files

   Create an edit a file, :file:`hello.rb`.
   Enter the text and save the file::
     
     #!/usr/bin/ruby
     puts 'Hello world'

   Then click the :guilabel:`Run` button in the menu bar.

Ruby program files use the extension :file:`.rb`. Any ruby file may be executed
with the command::

  ruby filename

To avoid calling the ruby interpreter explicitly, a "shebang" statement may be
added in the first line of the file::

  #! /usr/bin/ruby

IRB
-----------------------------

.. sidebar:: Example interactive Ruby

  Open a Cloud9 terminal window, and type::

    irb

IRB, or interactive Ruby, is an interactive environment for Ruby scripting. 
IRB is a Ruby command line, run inside the system console. Exit IRB back to the
shell command prompt by typing :command:`exit`.

|

----------

Variables 
=============================

| A variable is a named space in memory that stores some data. 
| A variable is identified by its name.
| A variable exists within a scope, and is deleted by a garbage collector when 
  it is no longer needed.

---------

.. sidebar:: Assigning variables

  Look for a variable named ``x``::

    x

  Assign a value to ``x``::

    x = 1

Assignment
-----------------------------

To create a variable in ruby, you assign it an initial value.
The ``=`` in ruby is known as the assignment operator. It is used like:
``variable_name = variable_value``

|
|
|
|
|

---------

Data Types
-----------------------------

.. sidebar:: Using data types

  Assign a boolean::

    x = true

  Assign a string::

    x = "This is a string"

  Assign an integer::

    x = 1

  Assign a float::
    
    x = 0.1

  Assign an array::

    x = ["Item 1", "Item 2", "Item 3"]

  Assign a hash::

    x = {:name => "variable x", :value => 1}

  Type a variable by assignment::

    x.is_a? Hash
    x = 1
    x.is_a? Hash

Ruby uses the following basic types for variables:

+ Boolean
+ String
+ Integer
+ Decimal / Float
+ Array
+ Hash

The type of a variable is determined by syntax of the assigned data value. 
Ruby is a dynamically typed language. That means that changing the value of a 
variable implicitly changes its type, since a variable inherits its data type 
from its value.

|

+------------+---------------------------------------+
| Datatype   | variable syntax                       |
+============+=======================================+
| Boolean    | unquoted ``true`` or ``false``        |
+------------+---------------------------------------+
| String     | "Text enclosed in quotes"             |
+------------+---------------------------------------+
| Integer    | A number without a decimal point      |
+------------+---------------------------------------+
| Float      | A number with a decimal point         |
+------------+---------------------------------------+
| Array      | | A comma-separated list of values    |
|            | | enclosed by square brackets         |
+------------+---------------------------------------+
| Hash       | | A comma-separated key-value pair    |
|            | | enclosed by curly braces            | 
+------------+---------------------------------------+  

|
|

---------

Arithmetic
-----------------------------

.. sidebar :: Arithmetic operations
 
  Enter the statements::

    x = 1
    x - 0 * 2
  
  Result: ``1``

  Enter the statements::

    (x - 0) * 2

  Result: ``2``

In Ruby, you can do all of the normal mathematical arithmetic on integer and 
decimal/float variables.

+-------------------+----------------+---------------+
| Operation         | Operand        | Sample Syntax |
+-------------------+----------------+---------------+
| Addition          | ``+``          | ``x + 2``     |
+-------------------+----------------+---------------+
| Subtraction       | ``-``          | ``x - 2``     |
+-------------------+----------------+---------------+
| Multiplication    | ``*``          | ``x * 2``     |
+-------------------+----------------+---------------+
| Division          | ``/``          | ``x / 2``     |
+-------------------+----------------+---------------+
| Modulus           | ``%``          | ``x % 2``     |
+-------------------+----------------+---------------+

The order of operations is the same as in regular math. Parentheses are used to 
group operations, and have the highest order of precedence, just as in regular 
math.

Arithmetic + Assignment
-----------------------------

Arithmetic and assignment may be combined with a single operator which performs 
the given arithmetic operation on the variable, and assigns the result of that 
operation to the new value of the variable, replacing the old value.

For example:

+---------------+---------------+--------------------------------+-------------+
| Operand       | Initial x     | Sample Use                     | Result x    |
+---------------+---------------+--------------------------------+-------------+
| ``+=``        | 1             | ``x += 2``                     | 3           |
+---------------+---------------+--------------------------------+-------------+
| ``-=``        | 3             | ``x -= 2``                     | 1           |
+---------------+---------------+--------------------------------+-------------+
| ``*=``        | 1             | ``x *= 2``                     | 2           |
+---------------+---------------+--------------------------------+-------------+
| ``/=``        | 2             | ``x /= 2``                     | 1           |
+---------------+---------------+--------------------------------+-------------+
| ``%=``        | 1             | ``x %= 1``                     | 0           |
+---------------+---------------+--------------------------------+-------------+

----------

String Concatenation
------------------------------------

If you want to add some data on to a string, you can use the ``+`` for this.

For example, if you want to have a string variable called "formatted_x" 
that uses the value of the integer variable "x" in it:

    ``formatted_x = "$" + x + ".00"``

Note that the string portions to be concatenated are surrounded by quotes, and 
anything not surrounded by quotes represents a variable or method's *value*. 

Also note that if you change the value of x, this *will not* update the value
of formatted_x, since the *value* of x was inserted into formatted_x, not the 
variable itself. If you wanted to auto-update formatted_x every time that x is
changed, you would have to use a method... read on to find out how.

Comparison
------------------------------------

You may sometimes want to compare the value of a variable to something else.
In Ruby, you can do this using the and, or, and is equal to operators:

+-------------------+---------------------+-----------------------------------+
| Operation         | Operand             | Sample Syntax                     |
+-------------------+---------------------+-----------------------------------+
| And               | ``&&``              | ``x && y``                        |
+-------------------+---------------------+-----------------------------------+
| Or                | ``||``              | ``x || y``                        |
+-------------------+---------------------+-----------------------------------+
| Is Equal To       | ``==``              | ``x == y``                        |
+-------------------+---------------------+-----------------------------------+

An example use of the "And"/"Or" comparisons:

"And" and "Or" are used to compare two boolean variables to each other. Say that 
you have these variables which describe a fast food order: ::

    sandwich = "cheeseburger"
    condiments = ["pickles", "mustard", "ketchup"]
    combo = true
    size = "medium"
    drink_upsize = true
    order = {
      :sandwich => sandwich,
      :condiments => condiments,
      :combo => combo,
      :size => size,
      :drink_upsize => drink_upsize
    }

... and you want to know whether this order is a combo with an upsized drink: ::

    combo && drink_upsize

This returns true, but if you set one of those variables equal to false, it does 
not: ::

    drink_upsize = false
    combo && drink_upsize

So you can see that the "And" comparison checks whether both of the given values
are true, and if not, it returns false.

The "Or" comparison checks to see if either one, or both, of the given values is
true, and if not, returns false. So: ::

    combo || drink_upsize

Returns true.

An example use of the "Is Equal to" comparison:

The "Is Equal To" comparison can be used on two values of *any type* to 
determine if they equal each other. ::

  combo == true
  --> true

  combo == drink_upsize 
  --> false

  combo == "true"
  --> false

  sandwich == "burger"
  --> false

WARNING: Do not confuse ``==`` with ``=``!

Conditionals
-----------------------------

If...Else
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Conditional statements are the simplest form of branching in coding. The first 
condtional is the if...else. It's just used to say: if this codition is true, 
do one thing, if it's not, do another thing. For example: ::

    if order[:sandwich] == "cheeseburger"
      puts "You ordered a cheeseburger"
    end

    if order[:sandwich] == "cheeseburger"
      puts "You ordered a cheeseburger!"
    else 
      puts "You didn't order a cheeseburger."
    end
   
So the structure of the if...else is::

  if conditional statement
    code to run if conditional returns true
  else
    code to run if conditional returns false
  end

Notice you always need an "end" after any conditional statement, to let the
interpreter know where the code that belongs to your branch ends. If you don't
have it, you will get an error.

If...Elsif
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Using ``elsif`` (short for "else if", and used only in Ruby) allows you to add 
more than one conditional to the same statement as your if or if...else. 
For example::

  if order[:sandwich] == "cheeseburger"
    puts "You ordered a cheeseburger!"
  elsif order[:sandwich] == "burger"
    puts "You ordered a burger!"
  end   

  if order[:sandwich] == "cheeseburger"
    puts "You ordered a cheeseburger!"
  elsif order[:sandwich] == "burger"
    puts "You ordered a burger!"
  else 
    puts "You didn't order a burger at all."
  end   

Unless
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

``Unless`` is just the opposite of ``if``. Use it when you want some code to run, 
unless this one particular condition is met. For example::

    unless order[:combo] == false
      puts "You get fries and a drink with that sammy!"
    end

    unless order[:drink_upsize]
      puts "You get a" + order[:size] + " fries and drink with that sammy!"
    end

Methods
------------------------------------


Nil and Blank
------------------------------------


Blocks, Loops, Conditionals
------------------------------------

Get User input
------------------------------------

Coding Best-Practices: KISS, DRY
------------------------------------

Put it all together
------------------------------------

See if you can write a ruby script in a .rb file that will take an order when it
is run.

