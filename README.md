# Import random module for generating computer's choice
import random

# Rock Paper Scissors game
# A simple greeting
print("Do you want to play Rock Paper Scissors ?\nLet's play")

# Print game rules
print("Rules : Rock beats scissors. Paper beats Rock. Scissors beats paper")

# Initialize point system
# points for user and code_points for computer
points = 0
code_points = 0

# List of game options
game_option = ["rock", "paper", "scissors"]

# Loop to play the game
while True:
    # Get user's choice and convert it to lowercase
    user_input = input("Enter your choice (Rock/Paper/Scissors) : ").lower()
    
    # Generate computer's choice randomly
    code_choice = random.choice(game_option)
    
    # Print computer's choice
    print(f"Computer chose {code_choice}")

    # Check for match draw
    if user_input == code_choice:
        print("Match Draw")
    
    # Check for user's win
    elif user_input == "rock" and code_choice == "scissors" or user_input == "scissors" and code_choice == "paper" or user_input == "paper" and code_choice == "rock":
        points += 1
        print(f"You won! Now you have {points} points")
    
    # Check for computer's win
    elif user_input == "scissors" and code_choice == "rock" or user_input == "rock" and code_choice == "paper" or user_input == "paper" and code_choice == "scissors":
        code_points += 1
        print(f"You lost the match. Now Computer has {code_points} points")
    
    # Handle invalid input
    else:
        print("Invalid input")
    
    # Print current scores
    print(f"Your score = {points}")
    print(f"Computer score = {code_points}")

    # Ask user if they want to play more
    request = input("Do you want more matches? Say (yes/no) : ").lower()
    
    # Set up to end the game
    if request == "no":
        # Print final scores
        print(f"Your score = {points}")
        print(f"Computer score = {code_points}")
        
        # Determine the winner
        if points > code_points:
            print(f"Congratulations, you win with {points} points!")
            print(f"Computer has {code_points} points only")
        elif points == code_points:
            print("The game is tied")
        else:
            print(f"Sorry, you lost the game with {points} points")
            print(f"Computer has {code_points} points")
        break
    
    # Continue the game if user wants to play more
    elif request == "yes":
        continue
    
    # Handle invalid input
    else:
        print("Invalid input")
print("Thanks for playing")
print("The end")           

