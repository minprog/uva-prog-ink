# 3.0 The game of Nims/Stones

In this game, two players sit in front of a pile of 100 stones. They take
turns, each removing between 1 and 5 stones (assuming there are at least 5
stones left in the pile). The person who removes the last stone(s) wins.

Because this game is interactive (you will not test it automatically), put it
in a separate file named `nims.py`. Do create a function called `play_nims`, as
follows:

    def play_nims(pile, max_stones):
        """
        An interactive two-person game; also known as Stones.
        @param pile: the number of stones in the pile to start
        @param max_stones: the maximum number of stones you can take on one turn
        """

Check out the lines of text in between the sets of `"""`, underneath the
definition. This is called a *docstring*, and is handy to use to tell other
programmers what parameters to pass in, and what your program does.

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

# 3.1 Report Card with GPA

This exercise and most others should be going into a file called `homework3.py`.

Write a function report card where the user can enter each of his grades,
after which the program prints out a report card with GPA (*see* [Urban
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

# 3.2 More About Dictionaries

Put these lists in your code:

    NAMES = ['Alice', 'Bob', 'Cathy', 'Dan', 'Ed', 'Frank',
             'Gary', 'Helen', 'Irene', 'Jack', 'Kelly', 'Larry']

    AGES = [20, 21, 18, 18, 19, 20, 20, 19, 19, 19, 22, 19]

These lists match up, so Alice's age is 20, Bob's age is 21, and so on. Write a
function combine lists that combines these lists into a dictionary (hint: what
should the keys, and what should the values, of this dictionary be?). Then,
write a function people that takes in an age and returns the names of all the
people who are that age.

Test your program's functions by running these lines:

    print 'Dan' in people(18) and 'Cathy' in people(18)
    print 'Ed' in people(19) and 'Helen' in people(19) and \
	      'Irene' in people(19) and 'Jack' in people(19) and 'Larry'in people(19)
    print 'Alice' in people(20) and 'Frank' in people(20) and 'Gary' in people(20)

    print people(21) == ['Bob']
    print people(22) == ['Kelly']
    print people(23) == []

All lines should print `True`. The last line is an "edge condition" that we're
testing; your `people` function should be able to handle this condition (hint:
what is this condition?) by simply returning an empty list...

# Double check

For every problem, check the following:

* Have you put the problem in a function?
* Have you added the problem to the right Python file?
* Have you put your name on top of that file?
* Have you made sure the program is NOT interactive (e.g. we don't have to type
  anything) except 3.1?
* Have you written at least three tests to show the program is correct, or even
  more tests if the problem prescribes this?
* Do the tests give the expected output?

# 3.3 Recursion

For each of these parts, you need to write one function with three tests!

1. Write a function that takes in two numbers and recursively multiplies them
   together.

2. Write a function that takes in a $$"base"$$ and an $$"exp"$$ and recursively
   computes $$"base"^"exp"$$.

3. Write a function using recursion to print numbers from $$n$$ to 0.

4. Write a function using recursion to print numbers from 0 to $$n$$ (you just
   need to change one line in the program of problem 1).

5. Write a function using recursion that takes in a string and returns a
   reversed copy of the string. The only string operation you are allowed to use
   is string concatenation (recall how you concatenate two strings?).

6. Write a function using recursion to check if a number $$n$$ is prime (you have
   to check whether $$n$$ is divisible by any number below $$n$$).

7. Write a recursive function that takes in one argument $$n$$ and computes
   $$F_n$$, the $$n$$-th value of the Fibonacci sequence. The Fibonacci
   sequence is defined by the relation:

   $$F_n = F_(n−1) + F_(n−2)$$

   but
   
   $$F_0 = 0$$ and $$F_1 = 1$$

   Visit the Wikipedia page on the [Fibonacci Number] for more information if
   you're still confused.

[Fibonacci Number]: http://en.wikipedia.org/wiki/Fibonacci_number

# Hacker: Zeller's Algorithm, revisited

This is similar to the *Program* from Week 1, but in this version we will be
writing a function that takes parameters, and using dictionaries to facilitate
"pretty printing" (where the answer is given to the user in a nice looking
fashion). For the rules of the algorithm, please take a look at the description
written in the Week 1 section.

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

# Hacker: Palindromes!

Write a function is palindrome which takes a string as parameter, and returns
True if the string is a palindrome (meaning it is the same forwards as
backwards), and False otherwise. This problem is kind of tricky so feel free to
ask for help; turn in any progress you make on it as well as comments
explaining what does and doesn't work. For an additional challenge, try writing
this as a recursive function.

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
