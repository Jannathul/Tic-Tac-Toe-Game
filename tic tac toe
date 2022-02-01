#choose player

def choose_player():
    player = ''
    
    while not (player == 'X' or player == 'O'):
        player = input('Player 1: Do you want to be X or O? ').upper()

    if player == 'X':
        return ('X', 'O')
    else:
        return ('O', 'X')
player1, player2 = choose_player()


#display board

from IPython.display import clear_output  #This line works only in Jupyter notebook else remove it

def display_board(board):
    
    clear_output()   #This line works only in Jupyter notebook else remove it
    print(board[1]+'|'+board[2]+'|'+board[3])
    print("-----")
    print(board[4]+'|'+board[5]+'|'+board[6])
    print("-----")
    print(board[7]+'|'+board[8]+'|'+board[9])
    
#Choose position

def choose_position(board,player,position):
    board[position]=player

    
#win Check
def win_check(board,player):
    return((board[1]==board[2]==board[3]==player)or(board[4]==board[5]==board[6]==player)or(board[7]==board[8]==board[9]==player)or
      (board[1]==board[4]==board[7]==player)or(board[2]==board[5]==board[8]==player)or(board[3]==board[6]==board[9]==player)or
        (board[1]==board[5]==board[9]==player)or(board[3]==board[5]==board[7]==player))
    
#first player

import random
def first_player():
    flip = random.randint(0,1)
    if flip==0:
        return "player 1"
    elif flip==1:
        return "player 2"
 
 
#free spaces

def free_space(board,position):
    return board[position]==' '

#Board is full

def full(board):
    for i in range(1,10):
        if free_space(board, i):
            return False
    return True

#choose position

def position_choice(board):
    position=0
    while position not in [1,2,3,4,5,6,7,8,9] or not free_space(board,position):
        print("Enter correct position...")
        position=int(input("Choose position : "))
    return position
    
#replay

def replay():
    replay=input("Do you want to play again?? 'Yes' or 'No'").upper()
    return replay=='YES'   
    


print("Welcome")

while True:
    board=[' ']*10
    
    turn=first_player()
    print(turn+" Will Go First")
    play_game=input("Ready to play? 'yes or no'").lower()
    if (play_game=='yes'):
        game_on=True
    else:
        game_on=False
    while game_on:
        if turn=='player 1':
            display_board(board)
            position=position_choice(board)
            choose_position(board,player1,position)
            if win_check(board,player1):
                display_board(board)
                print("Player 1 Won!!")
                game_on= False
            else:
                if full(board):
                    display_board(board)
                    print("Tie Game!!")
                    
                    break
                else:
                    turn="player 2"
        else:
            display_board(board)
            position=position_choice(board)
            choose_position(board,player2,position)
            if win_check(board,player2):
                display_board(board)
                print("Player 2 Won!!")
                game_on= False
            else:
                if full(board):
                    display_board(board)
                    print("Tie Game!!")
                    
                    break
                else:
                    turn="player 1"
                    
    if not replay():
        break
