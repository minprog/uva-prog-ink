# Getting started: Python and IDLE

This handout will cover how to set up Python and introduce you to IDLE, the Python development environment we will be using throughout this course.

## Setting up Python on Windows

Python should be set up correctly on the Windows machines. Find "Python 2.7" in the Start menu. This should start up the Python development environment named *IDLE*.

## On your own machine

If you are working on your own machine, you will probably need to install Python. We will be using the standard Python software, available here. You should download and install version 2.7.x, NOT 3.x (this will give you plenty of trouble).

### Windows

Go to the website and download the Windows MSI installer for either x86 or
x86-64, depending on which version of Windows you are running.

### Mac OS X

Download and install the Mac Installer disk image from the Python web site.

### Other Linux

Check which version of Python you have by running

	python -V

at a terminal. If you have a newer version of Python already installed,
for example Python 2.7.x or 3.1.x, you can set Python 2.6 as the default
by following the instructions listed here. Otherwise, you should be able
to do one of the following options:

	sudo apt-get install python2.6

if you don't already have Python 2.6 installed; if you do, run

	sudo apt-get install idle

to install Idle for Python 2.6. If you have Python and Idle installed with
a newer version of Python (eg Python 3.1... Python 2.7 won't cause a
conflict for 6.189 and you can leave it alone for now), you'll want to
instead run these two commands to install the correct version of Idle:

	sudo apt-get install idle-python2.6
	sudo ln -s /usr/bin/idle-python2.6 /usr/bin/idle

You should then be able to run Idle by simply running

	idle&

from the command prompt. If you would rather compile from source, visit
the Python 2.7 release page for compressed tarballs. If you're having
problems, please ask an assistant for... assistance (ahem).

**Warning**: On the Python homepage, the latest version available for download is actually 3.0. Do not install this! This version is not backwards compatible with the code that you'll be writing in this course (for example, you have to type `print("test")` instead of `print "test"`). Instead, be sure to download the version listed above.

## Using IDLE

IDLE is the standard Python development environment Its name is an acronym of "Integrated DeveLopment Environment". It works well on both Unix and Windows platforms.

It has a Python shell window, which gives you access to the Python interactive mode. It also has a file editor that lets you create and edit existing Python source files.

During the following discussion of IDLE's features, instead of passively reading along, you should start IDLE and try to replicate the screenshots.

## Interactive Python shell

When you start up IDLE, a window with an interactive Python shell will pop up:

![IDLE Shell](st-shell.png)

You can type Python code directly into this shell, at the `>>>` prompt. Whenever you enter a complete code fragment, it will be executed. For instance, typing:

	>>> print "hello world"

and pressing ENTER, will cause the following to be displayed:

	hello world

Try typing an underscore (`_`). Can you see it? On some operating systems, the bottoms of hanging letters such as 'g' or 'y', as well as underscorces, cannot be seen in IDLE. If this is the case for you, go to **Options -> Configure IDLE**, and change the size of the default font to 9 or 11. This will fix the problem! IDLE can also be used as a calculator:

	>>> 4+4
	8
	>>> 8**3
	512

Addition (`+`), subtraction (`-`), multiplication (`*`), division (`/`), modulo (`%`) and power (`**`) operators are built into the Python language. This means you can use them right away. If you want to use a square root in your calculation, you can either raise something to the power of 0.5 or you can import the `math` module. Do not worry about what it means right now, we will cover this later during the course. Below are two examples of square root calculation:

	>>> 16**0.5
	4.0
	>>> import math
	>>> math.sqrt(16)
	4.0

The math module allows you to do a number of useful operations:

	>>> math.log(16, 2)
	4.0
	>>> math.cos( 0 )
	1.0

Note that you only need to execute the import command once after you start IDLE; however you will need to execute it agin if you restart the shell, as restarting resets everything back to how it was when you opened IDLE. Don't worry too much about this right now; we'll cover it more in depth soon!

## Exercise

This is just for practice, solutions will not be graded or collected in class.

Use IDLE to calculate:

1.	$6 + 4 * 10$

2.	$(6 + 4) * 10$

	Compare this to #1, and note that Python uses parentheses just like you 
	would in normal math to determine order of operations!
	
3.	23.0 to the 5th power

4.	Positive root of the following equation:

	$34x ^ 2 + 68x - 510$  
	
	Recall that given an equation  
	
	$ax ^ 2 + bx + c$  
	
	you can get one root using:
	
	$x_1 = ( -b + sqrt (b ^ 2 - 4ac) ) / ( 2a )$.

## Attribution

The tutorial for IDLE is based on the official IDLE tutorial by Daryl Harms.
