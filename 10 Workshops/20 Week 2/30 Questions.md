# Questions to answer

## Warm up: recollections

Recall that a string is **immutable**, while a list is **mutable**. What does
this mean? Research it with your neighbor!

<textarea name="a[2-11]"></textarea>

## String operations

String operators might be a little less intuitive than those on numbers. This
exercise will give you a chance to practice those. Given the following 
variables:

	look = 'Look at me!'
	now = ' NOW'

What are the values of the following expressions? Try to guess on your own
before using your interpreter (but feel free to use your interpreter once you 
get stuck).

|expression                           |value                               |
|-------------------------------------|------------------------------------|
|`look[:4]`                           |<input name="a[2-12-1]" type="text">|
|`look[-1]`                           |<input name="a[2-12-2]" type="text">|
|`look*2`                             |<input name="a[2-12-3]" type="text">|
|`look[:-1] + now + look[-1]`         |<input name="a[2-12-4]" type="text">|
|`now[1]`                             |<input name="a[2-12-5]" type="text">|
|`now[4]`                             |<input name="a[2-12-6]" type="text">|
|`look*2 + look[:-1] + now + look[-1]`|<input name="a[2-12-7]" type="text">|

For more on strings, see [the Python docs](http://docs.python.org/release/2.6.6/library/stdtypes.html#string-methods).

## List operations

Say we have this list:

	a_list = [3, 5, 6, 12]

For the following, write the line(s) of code that will emit the given output.
For each problem there may be more than one correct answer; just give one. 

More on lists: [the Python docs](http://docs.python.org/release/2.6.6/tutorial/datastructures.html).

1.	Output: `3`

	<textarea name="a[2-13-1]"></textarea>

2.	Output: `12`

	<textarea name="a[2-13-2]"></textarea>

3.	Output: `[5, 6, 12]`

	<textarea name="a[2-13-3]"></textarea>

4.	Output:

		3
		5
		6
		12

	<textarea name="a[2-13-4]"></textarea>

5.	Output: `[12, 6, 5, 3]`

	<textarea name="a[2-13-5]"></textarea>

6.	Output: `[9, 15, 18, 36]`

	<textarea name="a[2-13-6]"></textarea>

7.	Output: `[False, False, True, True]`

	<textarea name="a[2-13-7]"></textarea>
