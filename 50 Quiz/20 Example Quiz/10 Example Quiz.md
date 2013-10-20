## Expressions and types <small>(1 point each)</small>

Assume that we execute the following assignment statements:

	width = 17
	height = 12.0
	delimiter = '.'

For each of the following expressions, write the value of the expression and
the type (of the value of the expression).

1. `width / 2` <input>
2. `width / 2.0` <input>
3. `height / 3` <input>
4. `1 + 2 * 5` <input>
5. `delimiter * 5` <input>

## Booleans <small>(1 point each)</small>

Consider the Boolean expression `not (p or not q)`. Give:

1. the value of the expression when p is True, and q is True <input>
2. the value of the expression when p is True, and q is False <input>
3. the value of the expression when p is False, and q is True <input>
4. the value of the expression when p is False, and q is False <input>

## Modulo <small>(3 points)</small>

Given a variable `n`, which of the following expressions computes the ten's
digit of `n`? Specifically, if `n` is an integer like `123`, then we want the
expression to evaluate to `2`. You may assume for simplicity that `n` is
non-negative.

* <input type="radio" name="modulo"> `((n - n % 10) / 10) % 10`
* <input type="radio" name="modulo"> `((n - n % 10) % 100) / 10`
* <input type="radio" name="modulo"> `(n / 10) % 10`

## Syntax check <small>(5 points)</small>

Which of the following arithmetic expressions are syntactically correct?

1. <input type="checkbox"> `7 / +4`
2. <input type="checkbox"> `9 + * 4`
3. <input type="checkbox"> `9 - (2 - (4 * 3)`
4. <input type="checkbox"> `(8 + (1 + (2 * 4) - 3))`
5. <input type="checkbox"> `5 - 1 - 3 - 7 - 0`

## Operator abuse

Assume you have values in the variables x and y. Which statement(s) would result in x having the sum of the current values of x and y?

1. <input type="checkbox"> `x = x + y`
2. <input type="checkbox"> `x += x + y`
3. <input type="checkbox"> `x = y + x`
4. <input type="checkbox"> `y += x`

## Mystery line

	tax_rate = 0.15
	income = 40000
	deduction = 10000

	# Calculate income taxes
	tax = (income - deduction) * tax_rate

	print tax

What is the line starting with a #?

1. This text is used as a file name for the code.
2. The text is stored in a special variable called `#`.
3. This is a syntax error.
4. This is a comment aimed at the human reader. Python ignores such comments.
5. This text is printed on the console.

## Just another syntax check

Which of the following are syntactically correct strings?

1. `"It's a beautiful day."`
2. `'Hello'`
3. `[Hello]`
4. `Hello`
5. `"Hello"`

## The human interpreter

Here's a program. Your job is to write down what it would print to the console if you were to run it in the Python interpreter. Assume it does not contain syntactical errors.

    x = "abcaef"
    for i in range(1,len(x)):
        if x[i] <= x[i-1]:
            print False
        else:
            print True

## Programmology

Given this program:

    def is_sorted(x):
        for i in range(1,len(x)):
            if x[i] <= x[i-1]:
                return False
        return True

1. What does `def` on line 1 do?
2. If `x` is `"abcadef"`, what range of numbers will come out of `range(1,len(x))`?
3. What does the `return` keyword on line 5 do?

## Keywords

What do these Python keywords or standard functions do? Explain as well as you can in a maximum of 2 sentences per keyword.

1. `else`
2. `import`
3. `in`
4. `or`
5. `len`

## Find the error

The program below contains one semantic error --- in other words, it does not what its name implies. Circle the error and suggest a correction.

    def is_sorted(x):
        for i in range(1,len(x)):
            if x[i] <= x[i-1]:
                return False
        return True

(This is the same program as above. In the real exam, multiple questions will often use different programs.)

## Write around

Write another version of the program below, using a while loop instead of a for loop. For extra credit, write it using recursion.

(This program still contains the error but it should not of course.)

    def is_sorted(x):
        for i in range(1,len(x)):
            if x[i] <= x[i-1]:
                return False
        return True

## Human compiler

The program below contains two syntactical errors. Your job as the Python interpreter is to find them and report the error.

	def max_of_2(a, b):
	    if a > b
	        return a
	    else:
	        return b

	def max_of_3(a, b, c):
	return max_of_2(a, max_of_2(b, c))

## Error determination

The following program will most certainly cause a runtime error. What kind of error will be reported if you run it anyway?

	def recurse():
	    recurse()

1. `NameError: name 'recurse' is not defined`
2. `TypeError: string indices must be integers`
3. `RuntimeError: maximum recursion depth exceeded`
4. `IndexError: string index out of range`
5. `KeyError: 'recurse'`

## The big one

The following functions are all intended to check whether a string contains any
lowercase letters, but at least some of them are wrong. For each function,
describe what the function actually does (you may assume that the given
parameter is always a string).

Program 1

	def any_lowercase1(s):
	    for c in s:
	        if c.islower():
	            return True
	        else:
	            return False

Program 2

	def any_lowercase2(s):
	    for c in s:
	        if 'c'.islower():
	            return 'True'
	        else:
	            return 'False'

Program 3

	def any_lowercase3(s):
	    for c in s:
	        flag = c.islower()
	    return flag

Program 4

	def any_lowercase4(s):
	    flag = False
	    for c in s:
	        flag = flag or c.islower()
	    return flag

Program 5

	def any_lowercase5(s):
	    for c in s:
	        if not c.islower():
	            return False
	    return True
