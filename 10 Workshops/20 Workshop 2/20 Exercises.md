# 2.0 From last week

As a warm-up, two exercises that you should now be able to do quickly using your
knowledge from last week. Put both programs in a file called `lastweek.py`.

## Chef's menu

Write a program that first displays a simple cafe menu (see example below),
asks the user to enter the number of a choice, and either prints the
appropriate action OR prints an error message that their choice was not valid.

Example output:

    1. Soup and salad
    2. Pasta with meat sauce
    3. Chef's special
    Which number would you like to order? 2
    One Pasta with meat sauce coming right up!

Another example output:

    1. Soup and salad
    2. Pasta with meat sauce
    3. Chef's special
    Which number would you like to order? 5
    Sorry, that is not a valid choice.

## Vowels

Also write a small program that takes a string and prints to the user all vowels in the string, in order of appearance.

Put this string atop the program in order to test it:

	vowely_string = "tim the beAver"

This means you do not need to ask the user for input.

# 2.1 Print vs Return

**Important**: most of the other exercises should be put in a file called
`homework2.py`. You should make sure this file runs without any user input
(unless it's a game) and gives correct output for every exercise. The same goes
for most files you submit from now on.

This isn't really an exercise, just an important bit of reading. These two
functions are defined:

	def f1(x):
	    print x + 1
	
	def f2(x):
	    return x + 1

Run this code in the shell. What happens when we call these functions?

	>>> f1(3)
	4
	>>> f2(3)
	4

It looks like they behave in exactly the same way. But they really don't. 
Try this:

	>>> print f1(3)
	4
	None
	>>> print f2(3)
	4

In the case of `f1`, the function, when evaluated, prints `4`; then it returns
the value `None`, which is printed by the Python shell. In the case of `f2`,
it doesn't print anything, but it returns `4`, which is printed by the Python
shell. Finally, we can see the difference here:

	>>> f1(3) + 1
	4
	Traceback (most recent call last):
	   File "<stdin>", line 1, in ?
	TypeError: unsupported operand type(s) for +: 'NoneType' and 'int'
	>>> f2(3) + 1
	5

In the first case, the function doesn't return a value, so there's nothing 
to add to 1, and an error is generated. In the second case, the function 
returns the value 4, which is added to 1, and the result, 5, is printed by 
the Python read-eval-print loop.

But for just about everything we do, it will be returned values that matter, 
and printing will be used only for debugging, or to give information to the
user.

Print is very useful for debugging. It's important to know that you can
print out as many variables and strings as you want in one line, when they 
are separated by commas. Try this:

	>>> x = 100
	>>> print 'x:', x, 'x squared:', x*x, 'sqrt(x):', x**0.5
	x: 100 x squared: 10000 sqrt(x): 10.0

# 2.2 Your first function

**Note:** So far we have been using `raw_input` to get user input. For the
remainder of this course we will move away from this tool, instead writing
**functions** that take in parameters as opposed to prompting the user for
input. So, for this and all following problems, do not use `raw_input` unless
explicitly told to do so.

Recall how we define a function using `def`, and how we pass in parameters. In
homework2.py, paste your code from exercise 1.7. Then, transform it into a function that takes parameters, instead of
asking the user for input. Make sure to return your answer, rather than
printing it.

Think a bit about the name you give to the function. Discuss with your 
neighbor what name would be best.

# Intermezzo: testing

In order to quickly evaluate the code you have written, and to get some
practice in writing tests, you are to include **at least 3** test cases below
your code for each exercise.

# 2.3 Testing your function

Because rock, paper, scissors now is a function that returns a value, you can
easily call it in a test. Write three test cases for rock, paper, scissors. Put
them directly below your function and mark in a comment that they are testing
statements.

# 2.4 Writing simple methods

In this problem you'll be asked to write two simple methods (*method* is an
interchangeable term for *function*). Be sure to test your functions well,
including at least 3 test cases for each method.

1. Write a method `is_divisible` that takes two integers, `m` and `n`. The
   method returns `True` if `m` is divisible by `n`, and returns `False`
   otherwise.

   Here's three test cases for that one:

		# tests for is_divisible
		print "is_divisible(10, 5) == True",  is_divisible(10, 5) == True
		print "is_divisible(18, 7) == False", is_divisible(18, 7) == False
		print "is_divisible(42, 0) == ",      is_divisible(42, 0) == False
	
   Look at the conditions that they test and try to make sure your future 
   test cases are comprehensive.

2. Imagine that Python doesn't have the `!=` operator built in. Write a
   method `not_equal` that takes two parameters and gives the same result 
   as the `!=` operator. Obviously, you cannot use `!=` within your 
   function! Test if your code works by thinking of examples and making sure
   the output is the same for your new method as `!=` gives you.

# 2.5 The `random` module

First, have a short look at the three examples of using the `random` module on the Python website. You can find lots of such examples there.

1. Now, write a method `rand_divisible_3` that takes no parameters, generates and prints a random number, and finally returns `True` if the randomly generated number is divisible by 3, and `False` otherwise. For this method we'll use a new module, the `random` module. At the top of your code, add the line `import random`. We'll use this module to generate a random integer using the function `randint`, which works as follows:

		random.randint(lo, hi)

   where `lo` and `hi` are integers that tell the code the range in which to
   generate a random integer (this range is *inclusive*). 0 to 100 is probably
   a decent range.

2. Write a method `roll_dice` that takes in 2 parameters:

   * the number of sides of the die, and
   * the number of dice to roll

   and generates random roll values for each die rolled. Print out each roll and then return the string "That's all!". An example output:

		>>> roll_dice(6, 3)
		4
		1
		6
		That's all!

# 2.6 Working with lists

Check out this function that sums all numbers in a list:

	def sum_all(number_list):
	    # number_list is a list of numbers
	    total = 0
	    for num in number_list:
	        total += num

	    return total

Note how we specify, with a comment, what the type of the **parameter** must
be. Here's two tests:

	# tests for sum_all
	print "sum_all of [4, 3, 6] is:", sum_all([4, 3, 6])
	print "sum_all of [1, 2, 3, 4] is:", sum_all([1, 2, 3, 4])

Now make a new function `cumulative_sum` that returns a new list where the 
$$i$$-th element is the sum of the first $$i+1$$ elements from the original list.
For example, the cumulative sum of `[4, 3, 6]` is `[4, 7, 13]`.

Such a useful function!

# 2.7 Additional list practice

You'll probably also need some practice with lists. Write a function
`list_intersection` that takes two lists as parameters. Return a list that gives
the intersection of the two lists; so, a list of elements that are common to
both lists.

	def list_intersection(list1, list2):
		# your code here

Put the following test cases below your program and make sure your results 
are the same. Order doesn't matter, as long as the list contains the same 
elements.

	# tests for list_intersection
	list_intersection([1, 3, 5], [5, 3, 1])               # [1, 3, 5]
	list_intersection([1, 3, 6, 9], [10, 14, 3, 72, 9])   # [3, 9]
    list_intersection([2, 3], [3,  3,  3,  2, 10])        # [3, 2]
    list_intersection([2, 4, 6], [1, 3, 5])               # []

# 2.8 Plotting

Ooooh this is nice! Easy graphical output with Python. This exercise will learn
you how to integrate other people's functions into your own program. Pyplot is
a library of functions that make it easy to plot data.

Work through the [Pyplot tutorial] and create a file called `pyplot.py` to save
your tutorial tests. Put each example in a separate function!

[Pyplot tutorial]: http://matplotlib.org/users/pyplot_tutorial.html

# 2.9 Pig Latin

Write a function `pig_latin` that takes in a single word, then converts the
word to Pig Latin. To review, Pig Latin takes the first letter of a word, 
puts it at the end, and appends "ay". The only exception is if the first 
letter is a vowel, in which case we keep it as it is and append "hay" to
the end. So:

|english  |pig latin|
|---------|---------|
|boot     |ootbay   |
|image    |imagehay |

It will be useful to define a list at the top of your code file called 
`VOWELS`. This way, you can check if a letter `x` is a vowel with the 
expression `x in VOWELS`. Remember: to get a word except for the first 
letter, you can use `word[1:]`.

Test your function with some interesting tests of which you already know
the answer!
