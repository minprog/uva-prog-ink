# Hangman

For this problem, you will implement a variation of the classic wordgame
Hangman. For those of you who are unfamiliar with the rules, you may read all
about it at [Wikipedia]. In this problem, the second player will always be the computer,
who will be picking a word at random.

[Wikipedia]: http://en.wikipedia.org/wiki/Hangman_(game)

In `hangman.py`, implement a function, `hangman()`, that will start up and
carry out an interactive Hangman game between a player and the computer.

For this problem, you will need the code files `hangman.py` and `words.txt`,
which were included in the download for *Wordgames*. Make sure your file runs
properly before editing. You should get the following output when running the
unmodified version of `hangman.py`.

    Loading word list from file...
    83667 words loaded.

You will want to do all of your coding for this problem within this
file as well because you will be writing a program that depends on
each function you write.

## Requirements

Here are the requirements for your game:

1. The computer must select a word at random from the list of available words
that was provided in `words.txt`. The functions for loading the word list and
selecting a random word have already been provided for you in `hangman.py`.

2. The game must be interactive: it should let a player know how many letters
the word the computer has picked contains and ask the user to supply guesses.
The user should receive feedback immediately after each guess. You should also
display to the user the partially guessed word so far, as well as either the
letters that the player has already guessed or letters that the player has yet
to guess.

3. A player is allowed some number of guesses. Once you understand how the game
works, pick a number that seems reasonable to you. Make sure to remind the
player of how many guesses s/he has left after each turn.

4. A player loses a guess only when they guess incorrectly.

5. The game should end when the player constructs the full word or runs out of
guesses. If the player runs out of guesses ("loses"), reveal the word to the
player when the game ends.

The output of an example game may look like this:

    >>>
    Welcome to the game, Hangman!
    I am thinking of a word that is 4 letters long.
    -------------
    You have 8 guesses left.
    Available letters: abcdefghijklmnopqrstuvwxyz
    Please guess a letter: a
    Good guess: _ a _ _
    ------------
    You have 8 guesses left.
    Available letters: bcdefghijklmnopqrstuvwxyz
    Please guess a letter: s
    Oops! That letter is not in my word: _ a _ _
    ------------
    You have 7 guesses left.
    Available letters: bcdefghijklmnopqrtuvwxyz
    Please guess a letter: t
    Good guess: t a _ t
    ------------
    You have 7 guesses left.
    Available letters: bcdefghijklmnopqruvwxyz
    Please guess a letter: r
    Oops! That letter is not in my word: t a _ t
    ------------
    You have 6 guesses left.
    Available letters: bcdefghijklmnopquvwxyz
    Please guess a letter: m
    Oops! That letter is not in my word: t a _ t
    ------------
    You have 5 guesses left.
    Available letters: bdefghijklmnopquvwxyz
    Please guess a letter: c
    Good guess: t a c t
    ------------
    Congratulations, you won!

Do not be intimidated by this problem! It's actually easier than it looks. Make
sure you break down the problem into logical subtasks. What functions will you
need to have in order for this game to work?

Before you start, create an initial design using pen and paper. Divide your
program into smaller subtasks and indicate how they relate. Show your design to
one of the course assistants and discuss!

## Hints:

* You should start by using the provided functions to load the words and pick a
  random one.

* Consider using `string.lowercase`.

* Consider writing helper functions. For instance, we found that creating
  functions to fill in guessed letters (generating strings like `ta_t`) and to
  display unused letters made partitioning the problem easier.
