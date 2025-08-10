# Besantproject
Project on rock-paper-scissor
import random

def get_computer_choice():
    choices = ['rock', 'paper', 'scissor']
    return random.choice(choices)

def get_user_choice():
    while True:
        user_input = input("Enter your choice (rock, paper, scissor): ").lower()
        if user_input in ['rock', 'paper', 'scissor']:
            return user_input
        else:
            print("Invalid input! Please choose rock, paper or scissor.")

def determine_winner(user, computer):
    if user == computer:
        return "Tie"
    elif (user == 'rock' and computer == 'scissor') or \
         (user == 'paper' and computer == 'rock') or \
         (user == 'scissor' and computer == 'paper'):
        return "User wins"
    else:
        return "Computer wins"

def play_game():
    print("Welcome to Rock, Paper, Scissor Game!")
    while True:
        user_choice = get_user_choice()
        computer_choice = get_computer_choice()
        print(f"User choice: {user_choice}")
        print(f"Computer choice: {computer_choice}")
        
       result = determine_winner(user_choice, computer_choice)
        print(f"Result: {result}")
        
        play_again = input("Play again? (yes/no): ").lower()
        if play_again != 'yes':
            print("Thank you for playing!")
            break

if __name__ == "__main__":
    play_game()
