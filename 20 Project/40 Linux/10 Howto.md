You can use Pygame on Linux, as installed on the faculty computers.

## Configuring for first use

* Boot the computer into Linux by pressing F2 during startup. Watch closely to
  see the menu asking to press F1 or F2.

* Logon to Linux using your regular credentials.

* Open a new Terminal window and download `virtualenv` using the following
  command:

        curl -O https://pypi.python.org/packages/source/v/virtualenv/virtualenv-1.9.tar.gz

  This program will create a *virtual environment* in which you can install
  Pygame yourself.

* This is a software package, which is compressed using `tar` and `gzip`. Uncompress it using

        tar xvf virtualenv-1.9.tar.gz

* If all is well, install `virtualenv` using

        virtualenv-1.9/virtualenv.py --no-site-packages --distribute -p /usr/bin/python2 ~/virtualenv

* Then, activate the virtual environment using

        source virtualenv/bin/activate

* Now you are ready to install Pygame! Type in this command:

        pip install hg+http://bitbucket.org/pygame/pygame

  It will take a while to do this. If it appears to be hanging, try pressing
  `<ENTER>`.

## Editing Python files

A good editor for Python in Linux is `gedit`. You can start it from the
Applications menu, then *Accessories*, then *gedit*.

When you save your file (or open), you see that you have exactly the same files
in Linux as you have in Windows! So if you want to, you can open your programs
from last week.

Alas, `gedit` does not have the F5 shortcut that IDLE has to run your program
at once. To run your program, head back to the Terminal, navigate to your
python files, and run your program:

    cd python
    python game.py

This runs `game.py`, but only if you saved a file called `game.py` in the
`python` folder!

## Activating the virtual environment next time

When you come back to program some more, you can again boot into Linux, open
the terminal and start editing. But you always need to re-activate your virtual
enviroment in order to be able to use Pygame.

    source virtualenv/bin/activate

You also need to do this in any new Terminal window that you open.
