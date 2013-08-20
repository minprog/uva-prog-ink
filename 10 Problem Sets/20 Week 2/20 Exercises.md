**Important**: most of these exercises should be put in a file called
`homework2.py`. You should make sure this file immediately runs and gives
correct output for every exercise. The same goes for all other files you
submit.

# 2.0 Print vs Return

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

In the first case, the function doesn't return a value, so there’s nothing 
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

# Intermezzo: Functions

> Note: So far we have been using raw_input to get user input. For the 
> remainder of this course we will move away from this tool, instead writing
> **functions** that take in parameters as opposed to prompting the user for 
> input. So, for this and all following problems, do not use raw_input unless
> explicitly told to do so.

# 2.1 Defining A Function

Recall how we define a function using `def`, and how we pass in parameters. 
In homework2.py, paste your code from exercise 1.7 (the rock, paper, scissors
game). Then, transform it into a function that takes parameters, instead of
asking the user for input. Make sure to return your answer, rather than 
printing it.

Think a bit about the name you give to the function. Discuss with your 
neighbor what name would be best.

# Intermezzo: Testing

> In order to quickly evaluate the code you have written, and to get some
> practice in writing test, you are to include **at least 3** test cases
> below your code for each exercise.

# 2.2 Testing your function

Because rock, paper, scissors now is a function that returns a value,
you can easily call it in a test. Write three test cases for
rock, paper, scissors. Put them directly below your function and mark in a
comment that they are testing statements.

# 2.3 Writing simple methods

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

# 2.4 Additional List Practice

After the crash course last week, you'll probably need some more practice
with lists.

Write a function list_intersection that takes two lists as parameters. Return
a list that gives the intersection of the two lists --- a list of elements 
that are common to both lists.

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

# 2.5 The `math` module

In this exercise, we will play with some of the functions provided in the 
`math` module. A **module** is a Python file with a collection of related 
functions. To use the module, you need to add the following line at the 
top of your program, right underneath the comments with your name:

	import math

If you want to find out what is $$sin(90^circ)$$, you first need to convert 
from degrees to radians and then use the `sin` function in the `math`
module:

	radians = (90.0 / 360.0) * 2 * math.pi
	print math.sin(radians)

You can do this work in the Python Shell by typing import math and then 
these lines.

For mathematical functions, you can generally call `math.func`, where
`func` is whatever function you want to call. For example, if you want the
sine of an angle a (where a is in radians), you can call `math.sin(a)`.
For logarithms, the function `math.log(n)` calculates the natural logarithm 
of `n` (So that's $$ln(n)$$ not $$log(n)$$!). You can calculate the log of
any base b using `math.log(n, b)`. The `math` module even includes
**constants** such as $$e$$ (`math.e`) and $$pi$$ (`math.pi`).

Documentation for the math module is available at:  
<http://docs.python.org/release/2.6.6/library/math.html>

Many computations can be expressed concisely using the "multadd" operation,
which takes three operands and computes $$a ∗ b + c$$. One of the purposes of
this exercise is to practice pattern matching: the ability to recognize a
specific problem as an instance of a general category of problems.

In the last part, you get a chance to write a method that invokes a method
you wrote. Whenever you do that, it is a good idea to test the first method 
carefully before you start working on the second. Otherwise, you might find
yourself debugging two methods at the same time, which can be very difficult.

1. Write a function `multadd` that takes three parameters, `a`, `b` and `c`.
   Test your function well before moving on.

2. Underneath your function definition, compute the following values using 
   `multadd` and print out the result:

   `angle_test = ` $$sin(pi/4) + cos(pi/4)/2$$
	
   `ceiling_test = ` $$\|~276/19~\| + 2 log_7(12)$$

   If you are unfamiliar with the notation $$\|~x~\|$$, this represents the 
   **ceiling** of a number. The ceiling of some `float x` means that we
   always "round up" `x`. For example, $$\|~2.1~\| = \|~2.9~\| = 3.0$$.
   Look at the `math` module documentation for a way to do this!

   If everything is working correctly, your output should look like:

       sin(pi/4) + cos(pi/4)/2 is: 1.06066017178
       ceiling(276/19) + 2 log_7(12) is: 17.5539788165

3. 	Write a new function called `yikes` that has one argument and uses the
    multadd function to calculate the following:

	$$xe^(-x) + sqrt(1-e^(-x))$$
	
	There are two different ways to raise $$e$$ to a power: check out the
	`math` module documentation. Be sure to `return` the result!
	Try $$x=5$$ as a test; your output should look like:
	
		yikes(5) is 1.0303150673

# 2.6 More functions

Here's two more functions to try your hand at.

1.	Write a method `rand_divis_3` that takes no parameters, generates and
	prints a random number, and finally returns `True` if the randomly 
	generated number is divisible by 3, and `False` otherwise. For this 
	method we'll use a new module, the `random` module. At the top of your
	code, underneath `import math`, add the line `import random`. We'll 
	use this module to generate a random integer using the function 
	`randint`, which works as follows:

		random.randint(lo, hi)

	where `lo` and `hi` are integers that tell the code the range in which
	to generate a random integer (this range is *inclusive*). 0 to 100 is
	probably a decent range.

2.	Write a method roll dice that takes in 2 parameters:

	* the number of sides of the die, and
	* the number of dice to roll
	
	and generates random roll values for each die rolled. Print out each
	roll and then return the string "That's all!". An example output:
	
    	>>> roll_dice(6, 3)
		4
		1
		6
		That's all!

# 2.7 Working with lists

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

# 2.8 Plotting

Ooooh this is nice! Graphical output with Python.

Work through the [Pyplot tutorial](http://matplotlib.org/users/pyplot_tutorial.html)
and create a file called `pyplot.py` to save your tutorial tests. Put each 
example in a separate function!

# 2.9 Pig Latin

Write a function pig_latin that takes in a single word, then converts the
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

## Sentences

Converting one word to Pig Latin is okay, but it would be more useful to be
able to convert whole sentences; so for this exercise, we'll use `raw_input`
to ask the user for a full sentence and translate it, word by word. It's
tricky for us to deal with punctuation and numbers with what we know so far,
so instead, ask the user to enter only words and spaces. You can convert 
their input from a string to a list of strings by calling split on the 
string; also, you can use lower to make a string all lowercase:

	>>> phrase = 'My namE is JohN SmIth'
	>>> word_list = phrase.split()
	>>> print word_list
	['My', 'namE', 'is', 'JohN', 'SmIth']
	>>> lowercase_phrase = phrase.lower()
	>>> print lowercase_phrase
	’my name is john smith’

Using such a list of words, you can go through each word and convert it to 
Pig Latin.

It will make your life much easier --- and your code much better --- if you
separate tasks into functions, e.g. have a function that converts one word
to Pig Latin rather than putting it into your main program code (you
already have that one!).

Extensions: once you have your program working, make it interactive such
that it keeps translating phrases into Pig Latin until the user enters in
the phrase QUIT. Or you can add in some more complex Pig Latin rules:
for example, words that start with "th", "st", "qu", "pl", or "tr" should
move *both* of those letters to the end.

|english|pig latin|
|-------|---------|
|stop   |opstay   |
|there  |erethay  |

There are many other Pig Latin rules that you can find online if you want
a true converter. Finally, you could try and deal with punctuation by 
looking for it within a string and moving it to the end of the word (the
solutions I wrote only handle commas, periods, !, ?, : and ; that appear 
at the ends of words, as they are pretty simple to handle).
