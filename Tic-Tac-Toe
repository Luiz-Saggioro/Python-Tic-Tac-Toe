#Declares the board of Tic Tac Toe
board = [[" ", " ", " "],
         [" ", " ", " "],
         [" ", " ", " "]]
side = " "
other_side = " "
results = "TIE"

#Starting the game and giving structions
def Starter(board):
    print("\n\nWelcome to the game of Tic-Tac Toe\n"
          "A Robot is going to play against you\n"
          "To play, choose either X or O to play and then which coordenate you would like to play at\n\n"
          " A |{}|{}|{}|\n".format(board[0][0],board[0][1], board[0][2]),
          "B |{}|{}|{}|\n".format(board[1][0],board[1][1],board[1][2]),
          "C |{}|{}|{}|\n".format(board[2][0],board[2][1],board[2][2]),
          "  1  2  3")

#Checks if anybody won in the game
def check_if_won(board, results):
    results = "Won"
    if board[0][0] == board[0][1] == board[0][2] == "X" or board[0][0] == board[0][1] == board[0][2] == "O": return results, print("{} Won!!!".format(board[0][0]))
    elif board[1][0] == board[1][1] == board[1][2] == "X" or board[1][0] == board[1][1] == board[1][2] == "O": return results, print("{} Won!!".format(board[1][2]))
    elif board[2][0] == board[2][1] == board[2][2] == "X" or board[2][0] == board[2][1] == board[2][2] == "O": return results, print("{} Won!!".format(board[2][2]))
    elif board[0][0] == board[1][0] == board[2][0] == "X" or board[0][0] == board[1][0] == board[2][0] == "O": return results, print("{} Won!!".format(board[2][0]))
    elif board[0][1] == board[1][1] == board[2][1] == "X" or board[0][1] == board[1][1] == board[2][1] == "O": return results, print("{} Won!!".format(board[2][1]))
    elif board[0][2] == board[1][2] == board[2][2] == "X" or board[0][2] == board[1][2] == board[2][2] == "O": return results, print("{} Won!!".format(board[1][2]))
    elif board[0][0] == board[1][1] == board[2][2] == "X" or board[0][0] == board[1][1] == board[2][2] == "O": return results, print("{} Won!!".format(board[1][1]))
    elif board[0][2] == board[1][1] == board[2][0] == "X" or board[0][2] == board[1][1] == board[2][0] == "O": return results, print("{} Won!!".format(board[1][1]))
    else:
        results = "TIE"
        return results

#Receive which side the player chose
def Side_Chosen(side):
    while True:
        side = str(input("Choose X or O: "))
        if side == "0": side = "O"
        side = side.upper()
        if side == "X" or side == "O":
            break
        else:
            print("\nInvalid input, please enter X or O")
    return side

#Choose side of the machine
def Machine_Side(side):
    if side == "X":
        other_side = "O"
    else: other_side = "X"
    return other_side

#Receive the input from the player
def Choose_Coordenate(board, side):
    while True:
        coords0 = input("Enter the coordinates of where you would like to play {}: ".format(side))
        coords = list(coords0)
        valids1 = ["A", "B", "C", "a", "b", "c"]
        valids2 = ["1", "2", "3"]
        if coords[0] in valids1:
            if coords[1] in valids2:
                if coords[0].upper() == "A": coords[0] = 0
                elif coords[0].upper() == "B": coords[0] = 1
                elif coords[0].upper() == "C": coords[0] = 2
                if coords[1] == "1": coords[1] = 0
                elif coords[1] == "2": coords[1] = 1
                elif coords[1] == "3": coords[1] = 2
                if board[coords[0]][coords[1]] == " ":
                    board[coords[0]][coords[1]] = side
                    break
                else: print("\nPlease, enter a valid coordinate")
        else: print("\nPlease, enter a valid coordinate")
    Board_State(board)
    return board

#Show the board state to the player
def Board_State(board):
    print("\n A |{}|{}|{}|\n".format(board[0][0], board[0][1], board[0][2]),
          "B |{}|{}|{}|\n".format(board[1][0], board[1][1], board[1][2]),
          "C |{}|{}|{}|\n".format(board[2][0], board[2][1], board[2][2]),
          "  1  2  3\n")

#Robot Chooses what to play
def Robot_decide(board, other_side):
    import random
    while True:
        coord1 = random.randint(0,2)
        coord2 = random.randint(0,2)
        if board[coord1][coord2] == " ":
            board[coord1][coord2] = other_side
            break
    Board_State(board)
    return board

#Checks if the game is not tied
def Check_Tie(board, results):
    if board[0][0] != " ":
        if board[0][1] != " ":
            if board[0][2] != " ":
                if board[1][0] != " ":
                    if board[1][1] != " ":
                        if board[1][2] != " ":
                            if board[2][0] != " ":
                                if board[2][1] != " ":
                                    if board[2][2] != " ":
                                        if "Won" != results:
                                            results = "Super Tie"
                                            print("The game ended in a tie")
                                            return results

#Driver code
while True:
    Starter(board)
    side = Side_Chosen(side)
    other_side = Machine_Side(side)
    while True:
        Choose_Coordenate(board, side)
        results = check_if_won(board,  results)
        Check_Tie(board, results)
        if results != "TIE":
            break
        Robot_decide(board, other_side)
        results = check_if_won(board, results)
        Check_Tie(board, results)
        if results != "TIE":
            break
    play_again = input("Would you like to play again? \n[Y/N]: ")
    play_again_list = list(play_again)
    if play_again[0].upper() != "Y":
        print("\nThank ou for playing!!!!!")
        break
    else:
        board = [[" ", " ", " "],
                 [" ", " ", " "],
                 [" ", " ", " "]]
        side = " "
        other_side = " "
        results = "TIE"
