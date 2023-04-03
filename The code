import random
#used to randomly choose the starting player.
def two_players():
    #prompts the players to enter their names and returns their names as a tuple.
    print('Welcome to the 3D World of Tic-Tac-Toe with Team 2!')
    player1 = input('Player 1, please enter your name: ')
    flag = True
    while flag:
        if player1 != "":
            print("Greetings, {}! Get ready to test your strategic thinking and skill!".format(player1))
            flag = False
        else:
            player1 = input('Player 1, please enter your name: ')


    player2 = input('Player 2, please enter your name: ')
    flag1 = True
    while flag1:
        if player2 != "":
            print("Welcome, {}! Get ready to face off against {} in this AWSome game! May the best mind win!".format(
                player2, player1))
            flag1 = False
        else:
            player2 = input('Player 2, please enter your name: ')


    return player1, player2

def choose_starting_player():
    #randomly chooses the starting player using the "random.choice" function from the "random" module.
    player1, player2 = two_players()
    starting_player = random.choice([player1, player2])
    unchoose=player2
    if starting_player==player2 :
        unchoose=player1
    else:
        unchoose=player2
    print("now we will make a random choice")
    print("The starting player is {}!".format(starting_player))
    return starting_player,unchoose


def create_board():
    #create a 3D list to represent the game board
    board = []
    for i in range(3):
        layer = []
        for j in range(3):
            row = []
            for k in range(3):
                row.append(0)
            layer.append(row)
        board.append(layer)
    return board

def draw_board(board,player1,player2):
    #draws the current state of the board using loops and conditional to check if a square is empty or not
    for layer in board:
        print('-' * 25)
        for row in layer:
            # print vertical bar
            print('|', end=' ')
            for square in row:
                if square == player1: # player 1 move
                    print('X', end=' ')
                elif square == player2: # player 2 move
                    print('O', end=' ')
                else: # empty square
                    print('.', end=' ')
                print('|', end=' ')
            print()
    print('-' * 25) #print final horizontal line of hyphens

def get_move(player, board):
    #prompts the player to enter their move and checks if the move is valid
    while True:
        try:
            # get the player's move as a string
            move = input(f"Player {player}, enter your move (layer,row,column): ")
            # split the move string into layer, row, and column
            layer, row, col = map(int, move.split(','))
            # check if the move is valid
            if board[layer][row][col] == 0:
                return layer, row, col
            else:
                print("That square is already taken. Try again.")
        except ValueError:
            print("Invalid input. Try again.")
def check_win(player , board):
    # check for horizontal wins
    for layer in board:
        for row in layer:
            if row.count(player) == 3:
                return True
    # check for vertical wins
    for layer in board:
        for col in range(3):
            if layer[0][col] == player  and layer[1][col] == player and layer[2][col] == player :
                return True
    # check for diagonal wins
    if layer[0][0] == player  and layer[1][1] == player and layer[2][2] == player:
        return True
    if layer[0][2] == player and layer[1][1] == player and layer[2][0] == player:
        return True
    if board[0][0][0] == player and board[1][1][1] == player and board[2][2][2] == player:
        return True
    if board[0][0][2] == player and board[1][1][1] == player and board[2][2][0] == player:
        return True
    if board[0][2][0] == player and board[1][1][1] == player and board[2][0][2] == player:
        return True
    if board[0][2][2] == player and board[1][1][1] == player and board[2][0][0] == player:
        return True
    # check for 3D wins
    if board[0][0][0] == player and board[1][1][1] == player and board[2][2][2] == player:
        return True
    if board[0][0][2] == player and board[1][1][1] == player and board[2][2][0] == player:
        return True
    if board[0][2][0] == player and board[1][1][1] == player and board[2][0][2] == player:
        return True
    if board[0][0][0] == player and board[1][0][1] == player and board[2][0][2] == player:
        return True
    if board[0][2][2] == player and board[1][1][1] == player and board[2][0][0] == player:
        return True
    if board[0][0][0] == player and board[1][1][0] == player and board[2][2][0] == player:
        return True
    if board[0][0][1] == player and board[1][1][1] == player and board[2][2][1] == player:
        return True
    if board[0][0][2] == player and board[1][1][2] == player and board[2][2][2] == player:
        return True
    if board[0][0][0] == player and board[1][0][1] == player and board[2][0][2] == player:
        return True
    if board[0][1][0] == player and board[1][1][1] == player and board[2][1][2] == player:
        return True
    if board[0][2][0] == player and board[1][2][1] == player and board[2][2][2] == player:
        return True
    for row in range(3):
        if layer[row][0] == player and layer[row][1] == player and layer[row][2] == player:
            return True
    for col in range(3):
        if layer[0][col] == player and layer[1][col] == player and layer[2][col] == player:
            return True
    if layer[0][0] == player and layer[1][0] == player and layer[2][0] == player:
        return True
    if layer[0][1] == player and layer[1][1] == player and layer[2][1] == player:
        return True
    if layer[0][2] == player and layer[1][2] == player and layer[2][2] == player:
        return True
    for i in range(3):
        if all(board[i][j][j] == player for j in range(3)):
            return True
        if all(board[i][j][2-j] == player for j in range(3)):
            return True
        if all(board[i][j][i-j] == player for j in range(3)):
            return True
        if all(board[i][j][i+j-2] == player for j in range(3)):
            return True

    for i in range(3):
        for j in range(3):
            if all(board[k][i][j] == player for k in range(3)):
                return True
            if all(board[i][k][j] == player for k in range(3)):
                return True
            if all(board[i][j][k] == player for k in range(3)):
                return True
            if i == j and all(board[k][i][j] == player for k in range(3)):
                return True
            if i + j == 2 and all(board[k][i][j] == player for k in range(3)):
                return True
    return False


def play_game():
    # create the game board and play on 3D
    board = create_board()
    # set the starting player
    play1,play2=choose_starting_player()

    player = play1
    # play the game until there is a winner or the board is full
    while True:
        # draw the board
        draw_board(board,play1,play2)
        # get the player's move
        layer, row, col = get_move(player, board)
        # update the board with the player's move
        board[layer][row][col] = player
        # check if the player has won
        if check_win(player, board):
            draw_board(board,play1,play2)
            print(f"Player {player} wins!")
            break
        # check if the board is full
        if all(all(square != 0 for square in row) for layer in board for row in layer):
            draw_board(board)
            print("It's a tie!")
            break
        # switch to the other player
        player = play2 if player == play1 else play1


flag=True
while True:
    play_game()
    # ask the player if they want to play again
    play_again = input("Do you want to play again? (y/n): ")
    if play_again.lower() != 'y':
     flag=False
    print("Thanks for playing!")

