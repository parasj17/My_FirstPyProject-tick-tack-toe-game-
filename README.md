# My_FirstPyProject-tick-tack-toe-game-
def accept_input():
    print ('Welcome to the game!')
    choice = int(input('Select player 1 or 2: '))
    if choice == 1:
        user1 =input('Enter name for player 1: ')
        user2 =input('Enter name for player 2: ')
    elif choice == 2:
        user2 =input('Enter name for player 2: ')
        user1 =input('Enter name for player 1: ')    
    else:
        print ('Invalid option!')
        return None, None

    print ("Let's start!")
    return user1, user2
user1, user2 = accept_input() 
print ('Player 1: ', user1) 
print ('Player 2: ', user2)

def enter_marker ():

    marker = ''
    while marker != 'X' and marker != 'O':
        marker = input (f"{user1} please enter a valid marker X or O: ").upper()

        if marker != 'X' and marker != 'O':
            print ('Invalid marker! Please select X or O')
            continue

def accept_input():
    print ('Welcome to the game!')
    choice = int(input('Select player 1 or 2: '))
    if choice == 1:
        user1 =input('Enter name for player 1: ')
        user2 =input('Enter name for player 2: ')
    elif choice == 2:
        user2 =input('Enter name for player 2: ')
        user1 =input('Enter name for player 1: ')    
    else:
        print ('Invalid option!')
        return None, None

    print ("Let's start!")
    return user1, user2
user1, user2 = accept_input() 
print ('Player 1: ', user1) 
print ('Player 2: ', user2)

def enter_marker ():

    marker = ''
    while marker != 'X' and marker != 'O':
        marker = input (f"{user1} please enter a valid marker X or O: ").upper()

        if marker != 'X' and marker != 'O':
            print ('Invalid marker! Please select X or O')
            continue
    current_player, current_marker = user1, player1_marker

    for turn in range(9):  
        display_board(board)

        while True:
            pos = input(f"{current_player} ({current_marker}), choose your position (1-9): ")

            if not pos.isdigit():
                print("Please enter a number between 1-9.")
                continue

            pos = int(pos)
            if pos not in board:
                print('Invalid position! Select a number between (1-9).')
            elif board[pos] != ' ':
                print('Spot already taken, please select another spot.')
            else:
                board[pos] = current_marker
                break

        if check_winner(board, current_marker):
            display_board(board)
            print(f"{current_player} wins!")
            return
            
        if current_player == user1:
            current_player, current_marker = user2, player2_marker
        else:
            current_player, current_marker = user1, player1_marker
            current_player, current_marker = user1, player1_marker

    display_board (board)
    print ('It is a tie')

game_start()




    
