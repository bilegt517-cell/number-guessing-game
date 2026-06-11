# number-guessing-game
import random 

difficulty = input("Choose a difficulty level: 1 for Easy, 2 for Medium, 3 for Hard: ")
                    

if difficulty == "1":
    attempts = 10
elif difficulty == "2":
    attempts = 5
elif difficulty == "3":
    attempts = 3
else:
    print("Invalid input. Please choose a valid difficulty level.")

number = random.randint(1, 100)
guess = input("Guess a number between 1 and 100: ")
while attempts > 0:
    if guess.isdigit():
        guess = int(guess)
        if guess < number:
            print("Too low! Try again.")
        elif guess > number:
            print("Too high! Try again.")
        else:
            print("Congratulations! You've guessed the number!")
            break
    else:
        print("Invalid input. Please enter a number.")
    
    attempts -= 1
    if attempts > 0:
        guess = input(f"You have {attempts} attempts left. Guess again: ")
    else:
        print(f"Game over! The correct number was {number}.")

