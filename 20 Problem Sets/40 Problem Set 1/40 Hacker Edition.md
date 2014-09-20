# Hacker Edition

This edition, which is entirely optional, consists of an add-on to the
Wordgames you wrote.

## Computer word choose

**This is all dependent on your functions from wordgames.py, so be sure to
complete `wordgames.py` before working on `computer.py`.**

You decide to teach your computer (SkyNet) to play the game you just built so
that you can prove once and for all that computers are inferior to human
intellect. Here, you will make a new version of the `play_hand` function.

First we must create a function that allows the computer to choose a word. We
have provided the function `get_perms(hand, n)` in [`perm.py`](perm.py). When this file is
`import`ed into `computer.py`, you can use it in your own functions.

Look at that function's specification, which will tell you what it does. You do
not need to understand how it works, but if you want to, talk to your assistant.

It is now your responsibility to create the function
`comp_choose_word(hand, word_list)`.

Hint: first try to make a legal player, and then worry about making the
computer player better (if you have time).

## Computer's turn to play a hand

Now you need to write a function similar to `play_hand`. Implement the
`comp_play_hand` function. This function should allow the computer to play the
game through completion.

## u & ur computer

Now that your computer can choose a word, you need to give the computer the
option to play.

Write the code that re-implements the `play_game` function. You will modify the
function to behave as described below in the function's comments.

As before, you should use the `HAND_SIZE` constant to determine the number of
cards in a hand. If you like, you can try out different values for `HAND_SIZE`
with your program.
