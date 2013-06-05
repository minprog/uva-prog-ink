# Questions

## Mutability

We've learned about many Python data structures (strings, lists, tuples,
dictionaries). For both "mutable" and "immutable", please give a short (5
words or fewer) definition, and then list what data structure(s) have that
characteristic.

Mutable:

<textarea name="a[3-1-1]"></textarea>

Immutable:

<textarea name="a[3-1-2]"></textarea>

## Finding Bugs

The following set of instructions were given to Ben Bitdiddle, and he produced
the code below. Find at least three bugs he made, and say how to fix them.

Instructions: Write a negate function that takes a number and returns the
negation of that number. Also write a large num function that takes a number,
and returns True if that number is bigger than 10000, and False otherwise.
Additionally, write some code to test your functions.

	def negate(num):
		return -num

	def large_num(num):
		res = (num > 10000)

	negate(b)
	neg_b = num
	print 'b:', b, 'neg_b:', neg_b

	big = large_num(b)
	print 'b is big:', big

Bugs:

1. <textarea name="a[3-2-1]"></textarea>

2. <textarea name="a[3-2-2]"></textarea>

3. <textarea name="a[3-2-3]"></textarea>

## A Mystery Program

Ben next turned in the following uncommented code (WTF?? WHY) to the
assistants. Help us figure out what it does!

	 1 print "Think of a number between 1 and 100, but don't tell me what you choose."
	 2 min_n = 1
	 3 max_n = 100
	 4 right_answer = False
	 5
	 6 while not right_answer:
	 7     mid_n = (max_n + min_n + 1)/2
	 8     answer = raw_input('Is it ' + str(mid_n) + '? ')
	 9     if answer[0] == 'y':
	10         right_answer = True
	11     elif answer.startswith('higher'):
	12         min_n = mid_n + 1
	13     elif answer.startswith('lower'):
	14         max_n = mid_n - 1
	15     else:
	16         print "Sorry, I don't understand your answer."
	17
	18 print 'Woohoo! I got it!'

1. The while loop exits when the variable right answer is True. What will
   cause right answer to be true?

   <textarea name="a[3-3-1]"></textarea>

2. How many times will the program print out 'Woohoo! I got it!'?

   <textarea name="a[3-3-2]"></textarea>

3. What are we using the variable answer for?

   <textarea name="a[3-3-3]"></textarea>

4. The program makes a guess in line 8. What user responses will be understood
   by the program after it makes its guess?

   <textarea name="a[3-3-4]"></textarea>

5. If the program gets the response 'higher', what does that tell it about its
   guess?

   <textarea name="a[3-3-5]"></textarea>

6. What are the variables min n, max n and mid n used for?

   <textarea name="a[3-3-6]"></textarea>

This is an example of binary search, a simple but important algorithm in
computer science. If you're curious, or confused, read the Wikipedia article
on binary search to find out more and get a good explanation of what's going
on here.
