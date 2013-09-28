# Pig Latin sentences

This problem builds on the work you did in the exercise about Pig Latin. Save
your work for this problem in a new file, `pig_latin.py`; you may wish to reuse
the code you wrote before to help with this exercise.

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
	'my name is john smith'

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

# Hacker edition: List comprehensions

List comprehensions follow naturally from set builder notation and lambda calculus. They are very cool and make your life a lot easier. Don't worry if you don't get them yet.

Read about list comprehensions on pages 34-35 of the 6.01 [course notes]; the Wikipedia article on them are good, and [this site] is concise and good.

Put these exercises in `comprehensions.py`.

1. Write a list comprehension that prints a list of the cubes of the numbers 1 through 10.

2. Write a list comprehension that prints out the possible results of two coin flips (one result would be 'ht'). (Hint - how many results should there be?)

3. Write a function that takes in a string and uses a list comprehension to return all the vowels in the string. 6
￼￼￼￼￼￼
4. Run this list comprehension in your prompt:

		[x+y for x in [10,20,30] for y in [1,2,3]]

   Figure out what is going on here, and write a nested for loop that gives you the same result. Make sure what is going on makes sense to you!

[course notes]: http://ocw.mit.edu/courses/electrical-engineering-and-computer-science/6-01sc-introduction-to-electrical-engineering-and-computer-science-i-spring-2011/unit-1-software-engineering/object-oriented-programming/MIT6_01SCS11_chap02.pdf

[this site]: http://www.secnetix.de/olli/Python/list_comprehensions.hawk

And now, your challenge:

1. Write a function that takes in a list of elements of different types and uses a list comprehension to return all the elements of the list of type int. Note: The function isinstance will be of help here. Google "Python isinstance" and see if you can figure out what it does, or type help(isinstance) at the Python shell.

2. Write a list comprehension which solves the equation $$y = x^2 + 1$$. Your solution should print out a list of $$[x, y]$$ pairs; use the domain $$x in [−5, 5]$$ and the range $$y in [0, 10]$$.

3. Similarly, write a list comprehension that finds the integer solutions $$[x, y]$$ for a circle of radius 5.

4. Make your own list comprehension challenge! Write a comment of what you're trying to do in your code, then put the list comprehension below the comment.
