# Guess-The-Word
A guess the word game made on Python

# Made by ZuperZee

# Guess the word
# Guess the word is a game where there is two player.
# user 1 writes the word user 2 needs to guess.
# Then user 2 can either guess a letter or the whole word.
# If user 2 guesses wrong 5 times he looses
# If user 2 guesses the word right he wins

print("What word should be guessed?")
wordGuess = input()
print("\n\n\n\n\n\n\n\n\n\n\n\n\n\n\n\n\n\n\n\n\n\n\n\n\n\n\n\n\n\n")
wordCheck = wordGuess
wordGuessSpot = ""
for i in range(len(wordGuess)):
    wordGuessSpot += "."
wordGuessed = 0
wordGuess = list(wordGuess)
lives = 5
while wordGuessed != wordCheck != wordGuessSpot and lives > 0:
    print(wordGuessSpot + "\nGuess a letter in the word or the word")
    wordGuessed = input()
    if wordCheck.find(wordGuessed) != -1:
        wordGuessSpot = list(wordGuessSpot)
        for x in range(len(wordCheck)):
            if wordGuessed in wordGuess:
                wordGuessSpot[wordGuess.index(wordGuessed)] = wordGuessed
                wordGuess[wordGuess.index(wordGuessed)] = "."
        wordGuessSpot = "".join(wordGuessSpot)
    else:
        lives -= 1
        print("You have " + str(lives) + " lives left")
if lives > 0:
    print("VICTORY!!! The word was \33[34m" + wordCheck)
else:
    print("The word was " + wordCheck)
