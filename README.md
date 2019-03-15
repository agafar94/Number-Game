# Number-Game
Computer generates a number and the player tries to find it in several attempts.
"""
@author: Civan Ulucan Dayan
VERSION: 16
DATE: Wed Mar 13 21:34:08 2019
DESCRIPTION: Number Guess Game
First Static Code Analysis: 3.35
Last Static Code Analysis: 10.0
"""
import random # Importing the random number generator library
INPUT_NUMBER_ENTRY = 0  # Number of try initialization
print('Hello player, What is your username?')
INPUTNAME = input()
COMPUTERNUMBER = random.randint(1, 50) # Generate a random number between 1 and 50
print('Alright, ' + INPUTNAME + ', we are all set, Guess the number between 1 and 50.')
while INPUT_NUMBER_ENTRY < 6: # if the guess is right, *break* breaks the loop
    NUMBERGUESSED = input('Take a guess.')
    if NUMBERGUESSED.isdigit():
        NUMBERGUESSED = int(NUMBERGUESSED)
        INPUT_NUMBER_ENTRY = INPUT_NUMBER_ENTRY + 1
        if NUMBERGUESSED < COMPUTERNUMBER:
            print('Your guess is low.')
        elif NUMBERGUESSED > COMPUTERNUMBER:
            print('Your guess is high.')
        elif NUMBERGUESSED == COMPUTERNUMBER:
            break
    else:
        print('Please enter only integer between 1 and 50')
        print('Note that your chanses are decreasing.')
        INPUT_NUMBER_ENTRY = INPUT_NUMBER_ENTRY + 1
if NUMBERGUESSED == COMPUTERNUMBER: # With respect to two outcomes, process two outputs
    INPUT_NUMBER_ENTRY = str(INPUT_NUMBER_ENTRY)
    print('! You guessed the number in ' + INPUT_NUMBER_ENTRY + ' guesses!')
if NUMBERGUESSED != COMPUTERNUMBER:
    COMPUTERNUMBER = str(COMPUTERNUMBER)
    print('Nope. The number I thought was ' + COMPUTERNUMBER)
