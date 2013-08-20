**Important**: most of these exercises should be put in a file called
`homework3.py`. You should make sure this file immediately runs and gives
correct output for every exercise. The same goes for all other files you
submit.

# 3.0 Quadratic Formula

Write a function roots that computes the roots of a quadratic equation. Check
for [complex roots] and print an error message saying that the roots are
complex.

[complex roots]: http://en.wikipedia.org/wiki/Square_root#Square_roots_of_negative_and_complex_numbers

* Hint 1: Your function should take three parameters. What are they?
* Hint 2: We know the roots are complex when what condition about the
  discriminant is met?

**Important**. Be sure to use a variety of test cases, that include complex
roots, real roots, and double roots.

Optional: For an extra challenge, compute and print out the complex roots.
Python can natively handle complex numbers: [reference].

[reference]: http://infohost.nmt.edu/tcc/help/pubs/python/web/complex-type.html

# 3.1 The game of Nims/Stones

In this game, two players sit in front of a pile of 100 stones. They take
turns, each removing between 1 and 5 stones (assuming there are at least 5
stones left in the pile). The person who removes the last stone(s) wins.

Because this game is interactive, put it in a separate file named `nims.py`.
Do create a function called `play_nims`, as follows:

	def play_nims(pile, max_stones):
		"""
		An interactive two-person game; also known as Stones.
		@param pile: the number of stones in the pile to start
		@param max_stones: the maximum number of stones you can take on one turn
		"""

Check out the lines of text in between the sets of `'''`, underneath the
definition. This is called a *docstring*, and is handy to use to tell other
programmers what parameters to pass in, and what your program does.

**First**, add a docstring to the function you wrote in the previous problem.

In this problem, you'll write a function to play this game; we've outlined it
for you. It may seem tricky, so break it down into parts. Like many programs,
we have to use nested loops (one loop inside another). In the outermost loop,
we want to keep playing until we are out of stones. Inside that, we want to
keep alternating players. You have the option of either writing two blocks of
code, or keeping a variable that tracks the current player. The second way
could be slightly trickier, but it's definitely do-able!

Finally, we might want to have an innermost loop that checks if the user's
input is valid. Is it a number? Is it a valid number (e.g. between 1 and 5)?
Are there enough stones in the pile to take off this many? If any of these
answers are no, we should tell the user and re-ask them the question.

As always, feel free to ask the assistants for help on any part of this
problem.

If you choose to write two blocks of code, the basic outline of the program
should be something like this:

	while [pile is not empty]:
		while [player 1's answer is not valid]:
			[ask player 1]
		[execute player 1's move]
		[same as above for player 2]

Be careful with the validity checks. Specifically, we want to keep asking
player 1 for their choice as long as their answer is not valid, BUT we want to
make sure we ask them at least ONCE. So, for example, we will want to keep a
variable that tracks whether their answer is valid, and set it to False
initially.

When you're finished, test each other's programs by playing them!

# 3.2 Report Card with GPA

Write a function report card where the user can enter each of his grades,
after which the program prints out a report card with GPA ([Urban
dictionary]). Remember to ask the user how many classes he took. Think: why
would we need to ask this? Could we write the program a different way, which
wouldn't need that info? Example output is below.

The function should take a list of tuples as its input.

[Urban dictionary]: http://www.urbandictionary.com/define.php?term=gpa

	>>> report_card([('18.02, 94), ('21H.601', 96), ('8.01', 91), ('5.111', 88)])
	REPORT CARD:
	18.02 - 94
	21H.601 - 96
	8.01 - 91
	5.111 - 88
	Overall GPA  92.25

Hints: You'll want to use a for loop, and you'll probably want to keep track
of names and grades seperately; there are a couple ways to do this. Remember,
add to lists with `my_list.append(elt)`.

# 3.3 Collision Detection of Balls

Many games have complex physics engines, and one major function of these
engines is to figure out if two objects are colliding. Weirdly-shaped objects
are often approximated as balls. In this problem, we will figure out if two
balls are colliding. You'll need to remember how to unpack tuples; refer to
the Tuples chapter in *Think Python* or ask an assistant if this is confusing.

We will think in 2D to simplify things, though 3D isn't different
conceptually. For calculating collision, we only care about a ball's position
in space, as well as its size. We can store a ball's position with the $$(x,y)$$
coordinates of its center point, and we can calculate its size if we know its
radius. Thus, we represent a ball in 2D space as a tuple of $$(x, y, r)$$.

To figure out if two balls are colliding, we need to compute the distance
between their centers, then see if this distance is less than or equal to the
sum of their radii. If so, they are colliding.

In `homework3.py`, write a function `ball_collide` that takes two balls as
parameters and computes if they are colliding; your function should return a
Boolean saying whether or not the balls are colliding. Optional: For a little
extra challenge, write your function to work with balls in 3D space. How
should you represent the balls? You will also need to write your own test
cases. Be sure to figure out any edge cases you need to test.

# 3.5 Zeller's Algorithm, revisited

This is similar to the Hacker exercise from Week 1, but in this version we
will be writing a function that takes parameters, and using dictionaries to
facilitate "pretty printing" (where the answer is given to the user in a nice
looking fashion). For the rules of the algorithm, please take a look at the
description written in the Week 1 section.

Calling `zellers("March", 10, 1940)` should give the output: `Sunday`.

Hints:

1. Use a dictionary to map between the month and its numerical value.

2. You can use either a list or dictionary to convert the final output of the
   algorithm to the day of the week.

3. Make sure you handle the following three points correctly.

   * Note: If the month is January or February, then the preceding year is
     used for computation. This is because there was a period in history when
     March 1st, not January 1st, was the beginning of the year.

   * If the computed value of R is a negative number, add 7 to get a
     nonnegative number between 0 and 6.

   * You might need to use one of the following (but, maybe not): To convert
     the string '90' to the number 90, use `int('90')`; to convert the int 90 to
     the string '90', use `str(90)`.

# 3.6 Double check

For every problem, check the following:

* Have you put the problem in a function?
* Have you added the problem to the right Python file?
* Have you put your name on top of that file?
* Have you made sure the program is NOT interactive (e.g. we don't have to type
  anything) except 3.1?
* Have you written at least three tests to show the program is correct, or even
  more tests if the problem prescribes this?
* Do the tests give the expected output?

# 3.7 Palindromes!

Write a function is palindrome which takes a string as parameter, and returns
True if the string is a palindrome (meaning it is the same forwards as
backwards), and False otherwise. Save your work in `palindromes.py`. This
problem is kind of tricky so feel free to ask for help; turn in any progress
you make on it as well as comments explaining what does and doesn't work. For
an additional challenge, try writing this as a recursive function.

Some useful things to remember:

* Use the function `len` to find the length of a string.

* To get just a piece of a string, use the slice operator. For example:

		astring = 'hello'
		substr  = astring[1:-1]  # sets substr to 'ell'

* You can decide for yourself whether you want your function to correctly
  identify palindromes that have spaces (such as 'able was i ere i saw elba').
  Look up `string.join` for a useful function to use.

* `string.lower` may also be a useful function.

* BE SURE TO TEST WELL! Include multiple test cases, including one where the
  word isn't a palindrome, but the first and last letters are equal (such as
  "yummy").

* It is easiest to do this with a while loop, although there are a few
  different ways of structuring such a loop. Think about what conditions need
  to be met for a palindrome to be true, and when you can stop testing for one
  (hint: the words 'ana' and 'anna' are both palindromes; when do we know to
  stop checking?)

# 3.8 Data processing

First, download [population.csv](population.csv) (**download, not open in
Excel!**), containing a list of the population counts in the Netherlands over
the last 60 years. Put it in your N:-drive!

You will need to read this file and plot its data. Have a look at it first,
it's quite small.

Next, open your Python Shell and try to read it into Python:

	>>> import csv
	>>> file = csv.reader(open("n:\population.csv"))
	>>> file.next()
	>>> ['country', 'country isocode', 'year', 'POP']

Cool! Apparently Python can read your file. This first line isn't so
interesting to our program. But it does tell us what data can be found where.

Did you notice that the line is output by Python as an **list**? That is very
convenient. It appears that `csv.reader` will read a line and convert it into
an array containing the data fields.

Now, let's go on:

	>>> file.next()
	>>> ['Netherlands', 'NLD', '1950', '10113.527']

Now, that's the *real* data. Line 2 and all other lines contain the data that
was promised.

Let's parse the data:

	>>> line = file.next()
	>>> line[0]
	'Netherlands'

So you can actually save the next line in a variable and use it as a list.
Column 0 always contains the string `'Netherlands'`. And column 1 always
contains `'NLD'`.

Column 2 and 3 are more interesting. They contain the year and population in
that year. But... they are strings. That's of no use in calculations. And
there's a decimal point in the population count!

## Printing the population list nicely

Your first assignment with this file is to print the data to the screen.
Create a file called `hw6.py` and define a function like this:

	def print_population_list(filename):
		'''
		Prints the population read from a CSV file, containing 
		years in column 2 and population / 1000 in column 3.

		@param filename: the filename to read the data from
		'''

It is called `print_...` so it may print something! It should have this
**exact** output:

	1950: 10113527
	1951: 10264311
	1952: 10381988
	...

... and so on for each line in the data set.

Put your test call right below the function definition:

	print_population_list('N:\population.csv')

## Reading the list into a dictionary

This data connects a population count to a year. So a **dictionary** is the
perfect data structure to put this data in.

Define a function that reads all lines and `return`s the data in a dictionary
object.

	def population_dict(filename):
		"""
		Reads the population from a CSV file, containing 
		years in column 2 and population / 1000 in column 3.

		@param filename: the filename to read the data from
		@return dictionary containing year -> population
		"""

Also, the year in the dictionary should be of a reasonable type. An integer is
ok, but a string is also fine. The population however, is interesting to do
calculations with, so we would like to have that as an integer.

Test the function with this call below your code:

	print population_dict('N:\population.csv')

## Plotting the population

Now that we can read the census data into a dictionary, we can do other stuff
with it.

Create a function that plots data from a dictionary in a graph. Give it a
reasonable name. The function should have an extra parameter that tells us
what the title of the plot should be. Pass this title to `pyplot`.

Of course, because nothing is ever *easy*, you can't feed `pyplot` a
dictionary. It wants lists of the same length: in this case, one containing
the year labels, and one containing the data. How can you extract these lists
from a dictionary? It's quite simple, look it up.

Again, put a test that calls your function in the file! It needs to read a
dictionary and save it, and then pass that dictionary to the plotting function
you just made.

## Calculating year-over-year growth

Now, we want some more statistics. Let's calculate the year-over-year growth
percentage.

Create a function that takes one dictonary as a parameter and returns a new
dictionary containing year-over-year growth rates. You already know how to
extract the population count list from the dictionary. You also know how to
calculate a growth rate from one year to the next. And you know how to save
each calculated rate into a new list.

You probably don't know yet how you can easily create a new dictionary from
the list you just calculated. Say we have created a list `growth_rates` and we
already had the list `years`, then:

	growth_rates = [0.2, 0.23, 0.209, 0.31, ...]
	years = [1950, 1951, 1952, 1953, ...]
	
	growth_rate_dict = dict(zip(years, growth_rates))

`zip` is actually a very cool function. It creates one list from two lists.
Each element of the new list is a tuple, containing one element from list 1
and one element from list 2. And then we put it in the `dict` function to
convert it to a dictionary. Nice!

Plot your new dictionary using the same function that you defined previously.

## Acknowledgements

Thanks to Mark Guzdial's Computational Freakonomics class for a reference to
the data we used here.

The Netherlands population data / PWT 7.1 Alan Heston, Robert Summers and
Bettina Aten, Penn World Table Version 7.1, Center for International
Comparisons of Production, Income and Prices at the University of
Pennsylvania, Nov 2012.
