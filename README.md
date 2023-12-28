# Wordle-project

import random
import sys

def main():
    # Get a random word.
    answer = getRandomWord()
    guess = ""
    attempt = 0
    while attempt < 6 and guess != answer:
        guess = input("Enter a 5 letter guess?\n")
        if len(guess) == 5:
            attempt += 1
            for i in range(len(guess)):
                if guess [i] == answer[i]:
                    print(f"{guess[i]} - Green")
                elif guess[i] in answer:
                    print(f"{guess[i]} - Yellow")
                else:
                    print(f"{guess[i]} - Red")

        if attempt < 6 and guess == answer:
            print(f"You Won! That took {attempt} guess(es).")
            break
        elif attempt == 6 and guess != answer:
            print(f"You lost. The answer was {answer}.")
            break
    # PUT YOUR CODE HERE.
    # Start by asking the user for their initial guess
    # Ask them to "Enter a 5 letter guess?"
    # Start with section 3 in the starter doc.
    

# A helper method that prints the guess with the
# correct colors to the console.
# Example usage:
# printGuessColors("broke", "broke") should print the five lines:
#
# b - Green
# r - Green
# o - Green
# k - Green
# e - Green
def printGuessColors(guess, answer):
    return


# A helper method that determines the color
# of the letter in the guess. This function
# should return "Green", "Red", or "Yellow"
def letterColor(index, guess, answer):
    return


# A method that gets a random word from a file.
# You should not change this function.
def getRandomWord():
    # Choose the word to be the answer for testing purposes.
    if len(sys.argv) > 1:
        return sys.argv[1]
    else:
        file = open("words.txt", "r")
        # Strip removes the new line at the end of each word.
        words = [word.strip() for word in file.readlines()]

        return random.choice(words)


main()
