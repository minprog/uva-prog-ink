This week you'll learn about;

* file input/output
* drawing graphics using Pygame

## Assignment

The idea of this exercise is to graphically implement the *Tower of Hanoi*
puzzle. For a description of the puzzle we refer to [Wikipedia]. Make sure you
have read the Pygame basics and practiced with drawing some shapes before
getting started.

[Wikipedia]: http://en.wikipedia.org/wiki/Towers_of_hanoi

## Learn PyGame

Fortunately, PyGame is already installed in the Appliance. You can go ahead and follow this video, and try out PyGame:

<iframe width="420" height="315" src="https://www.youtube.com/embed/f_kFOFYdCiY" frameborder="0" allowfullscreen></iframe>

Do note that we think `setDisplay` is not a great variable name, because it is inconsistent with all of standard Python! We'd rather call it `set_display`.

## Required features of your game

Back to our assignment. Here are the features that your game should provide for the user!

* Graphically represent any state in the Tower of Hanoi puzzle.
* Move discs between towers using the mouse.
* Detect when the game is solved.
* Prevent illegal moves.
* Read a starting state from file like [this one](hanoi.txt). Each line is a
  tower and larger numbers represent larger discs.

## Readings

From [*Making Games with Python and Pygame* (Al Sweigart)](http://inventwithpython.com/pygame/chapters/).

* [Pygame Basics](http://inventwithpython.com/pygame/chapter2.html) (Until the Animation paragraph)
* [Pygame.event Reference](http://www.pygame.org/docs/ref/event.html) (The list of possible event types and their attributes)

## Steps

* During the *first lab session* you will create a design document that, er, documents all design decisions you can come up with.

* At the *end of the first week*, you will have finished a beta version of
  your game.

* At the *end of the second week*, you will have finished a beta version of
  your game.
