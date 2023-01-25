https://github.com/Avatar4640/TicTacToe.git
board = [" "," "," "," "," "," "," "," "," "]

def print_board():
    print(" "+board[0]+" |"+board[1]+" | "+board[2]+" ")
    print("---|---|---")
    print(" "+board[3]+" |"+board[4]+" | "+board[5]+" ")
    print("---|---|---")
    print(" "+board[6]+" |"+board[7]+" | "+board[8]+" ")

def check_win(player):
    if (board[0] == player and board[1] == player and board[2] == player) or \
    (board[3] == player and board[4] == player and board[5] == player) or \
    (board[6] == player and board[7] == player and board[8] == player) or \
    (board[0] == player and board[3] == player and board[6] == player) or \
    (board[1] == player and board[4] == player and board[7] == player) or \
    (board[2] == player and board[5] == player and board[8] == player) or \
    (board[0] == player and board[4] == player and board[8] == player) or \
    (board[2] == player and board[4] == player and board[6] == player):
        return True
    else:
        return False

def check_tie():
    if " " not in board:
        return True
    else:
        return False

player1 = True
while True:
    print_board()
    if player1:
        print("Player 1's turn (X)")
    else:
        print("Player 2's turn (O)")
    choice = int(input("Enter the number of the square where you want to place your mark (0-8): "))
    if board[choice] == " ":
        if player1:
            board[choice] = "X"
        else:
            board[choice] = "O"
    else:
        print("That square is already taken! Try again.")
        continue
    if check_win("X"):
        print_board()
        print("Player 1 wins!")
        break
    elif check_win("O"):
        print_board()
        print("Player 2 wins!")
        break
    elif check_tie():
        print_board()
        print("It's a tie!")
        break
    player1 = not player1
