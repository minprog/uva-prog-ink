## 1. Expressions and types <small>(1 point each)</small>

Assume that we execute the following assignment statements:

    width = 17
    height = 12.0
    delimiter = '.'

For each of the following expressions, write the value of the expression and
the type (of the value of the expression).

> |`width / 2`|<input type="text">|<input type="text">|
> |`width / 2.0`|<input type="text">|<input type="text">|
> |`height / 3`|<input type="text">|<input type="text">|
> |`1 + 2 * 5`|<input type="text">|<input type="text">|
> |`delimiter * 5`|<input type="text">|<input type="text">|

## 2. Booleans <small>(1 point each)</small>

Consider the Boolean expression `not (p or not q)`. Give:

> | |value of the expression|
> |p is True, q is True|<input type="text">|
> |p is True, q is False|<input type="text">|
> |p is False, q is True|<input type="text">|
> |p is False, q is False|<input type="text">|

## 3. Modulo <small>(3 points)</small>

Given a variable `n`, which of the following expressions computes the ten's
digit of `n`? Specifically, if `n` is an integer like `123`, then we want the
expression to evaluate to `2`. You may assume for simplicity that `n` is
non-negative.

* `((n - n % 10) / 10) % 10`
* `((n - n % 10) % 100) / 10`
* `(n / 10) % 10`
{: .radios}

## 4. Syntax check <small>(5 points)</small>

Which of the following arithmetic expressions are syntactically correct?

* `7 / +4`
* `9 + * 4`
* `9 - (2 - (4 * 3)`
* `(8 + (1 + (2 * 4) - 3))`
* `5 - 1 - 3 - 7 - 0`
{: .checkboxes}

## 5. Operator abuse <small>(1 point)</small>

Assume you have values in the variables x and y. Which statement(s) would result in x having the sum of the current values of x and y?

* `x = x + y`
* `x += x + y`
* `x = y + x`
* `y += x`
{: .checkboxes}

## 6. Mystery line <small>(1 point)</small>

	tax_rate = 0.15
	income = 40000
	deduction = 10000

	# Calculate income taxes
	tax = (income - deduction) * tax_rate

	print tax

What is the line starting with a #?

* This text is used as a file name for the code.
* The text is stored in a special variable called `#`.
* This is a syntax error.
* This is a comment aimed at the human reader. Python ignores such comments.
* This text is printed on the console.
{: .radios}

## 7. Just another syntax check <small>(5 points)</small>

Which of the following are syntactically correct strings?

* `"It's a beautiful day."`
* `'Hello'`
* `[Hello]`
* `Hello`
* `"Hello"`
{: .checkboxes}

## 8. The human interpreter <small>(5 points)</small>

Here's a program. Your job is to write down what it would print to the console if you were to run it in the Python interpreter. Assume it does not contain syntactical errors.

    x = "abcaef"
    for i in range(1,len(x)):
        if x[i] <= x[i-1]:
            print False
        else:
            print True

## 9. Programmology

Given this program:

    def is_sorted(x):
        for i in range(1,len(x)):
            if x[i] <= x[i-1]:
                return False
        return True

1. (5 points) What does `def` on line 1 do?

    <textarea>

2. (5 points) If `x` is `"abcadef"`, what range of numbers will come out of `range(1,len(x))`?

    <textarea>

3. (5 points) What does the `return` keyword on line 5 do?

    <textarea>

## 10. Keywords <small>(2 points each)</small>

What do these Python keywords or standard functions do? Explain as well as you can in a maximum of 2 sentences per keyword.

1. `else`
    <textarea>

2. `import`
    <textarea>

3. `in`
    <textarea>

4. `or`
    <textarea>

5. `len`
    <textarea>

## 11. Find the error <small>(10 points)</small>

The program below contains one semantic error --- in other words, it does not what its name implies. Circle the error and suggest a correction.

    def is_sorted(x):
        for i in range(1,len(x)):
            if x[i] <= x[i-1]:
                return False
        return True

(This is the same program as above. In the real exam, multiple questions will often use different programs.)

> <textarea>

## 12. Write around

Write another version of the program below, using a while loop instead of a for loop. For extra credit, write it using recursion.

(This program still contains the error but it should not of course.)

    def is_sorted(x):
        for i in range(1,len(x)):
            if x[i] <= x[i-1]:
                return False
        return True

(5 points) Using a while loop:

> <textarea>

(10 points) Using recursion:

> <textarea>

## 13. Human compiler <small>(3 points each)</small>

The program below contains two syntactical errors. Your job as the Python interpreter is to find them and explain the error.

	def max_of_2(a, b):
	    if a > b
	        return a
	    else:
	        return b

	def max_of_3(a, b, c):
	return max_of_2(a, max_of_2(b, c))

Explanation of errors:

<textarea>

<textarea>

## 14. Error determination <small>(2 points)</small>

The following program will most certainly cause a runtime error. What kind of error will be reported if you run it anyway?

	def recurse():
	    recurse()

* `NameError: name 'recurse' is not defined`
* `TypeError: string indices must be integers`
* `RuntimeError: maximum recursion depth exceeded`
* `IndexError: string index out of range`
* `KeyError: 'recurse'`
{: .radios}

## 15. The big one <small>(5 points each)</small>

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
