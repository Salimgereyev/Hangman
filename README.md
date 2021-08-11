# Hangman
This is more of a “guess the word” game. The core concepts you have to use while developing this project are variables, random, integer, strings, char, input and output, and boolean. In the game, users have to enter letter guesses, and each user will have a limited number of guesses (a counter variable is needed for limiting the guesses). 

import random

name = input("What is your name?\n")
print("Good luck", name)

words = ["rainbow", "computer", "science", "programming", "python", "mathematics", "player", "condition"]
word = random.choice(words)
guesses = ""
turns = 10
print("Guess the characters: ")

while turns > 0:
    failed = 0
    for char in word:
        if char in guesses:
            print(char)
        else:
            print("_")
            failed += 1

    if failed == 0:
        print("You win")
        print("The word is:", word)
        break

    guess = input("Guess the character: ")
    guesses += guess

    if guess not in word:
        print("Wrong")
        turns -= 1
        print("You have ", + turns, " guesses left")

        if turns == 0:
            print("You loose")
