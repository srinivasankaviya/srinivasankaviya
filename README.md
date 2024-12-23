import random

def haunted_house():
    print("Welcome to the Haunted House!")
    current_room = 'entrance'

    while True:
        if current_room == 'entrance':
            print("\nYou are at the entrance of the haunted house.")
            choice = input("Where do you want to go? (bedroom, kitchen, library, living room): ").lower()
            if choice in ['bedroom', 'kitchen', 'library', 'living room']:
                current_room = choice
            else:
                print("Invalid choice. Try again.")

        elif current_room == 'bedroom':
            print("\nYou enter the bedroom.")
            print("A ghost appears! 👻")
            print("""
               .-.
              (o o) 
              | O |
              '---'
            """)
            input("Press Enter to leave the room.")
            current_room = 'entrance'

        elif current_room == 'kitchen':
            print("\nYou enter the kitchen.")
            print("On the table, you see three potions:")
            print("1. Red Potion")
            print("2. Blue Potion")
            print("3. Green Potion")
            choice = input("Which potion do you choose? (1, 2, 3): ")
            if choice == '1':
                print("You feel a surge of energy! You are now stronger.")
            elif choice == '2':
                print("You feel dizzy! You should be more careful next time.")
            elif choice == '3':
                print("You feel a wave of calm. You regain your confidence.")
            else:
                print("That's not a valid choice.")
            input("Press Enter to leave the room.")
            current_room = 'entrance'

        elif current_room == 'library':
            print("\nYou enter the library.")
            print("You find a secret passage leading to the kitchen!")
            current_room = 'kitchen'

        elif current_room == 'living room':
            print("\nYou enter the living room.")
            question = random.randint(1, 10)
            answer = int(input(f"What is {question} + {question}? "))
            if answer == question + question:
                print("Correct! You may proceed.")
                current_room = 'entrance'
            else:
                print("Wrong answer! You have lost your way in the haunted house.")
                break  # End the game if the user answers incorrectly

if __name__ == "__main__":
    haunted_house
