# tictactoe
This is a TicTacToe game

''' Task 1: Set the board  '''
# Click on Run and observe the output

import os
import time
import displayboard
import classfunc
print()
print("WELCOME TO TIC-TAC-TOE\n")
print("----------------------")
displayboard.display_board()
time.sleep(20)
os.system("clear")
# Creating the Board() instance
board=classfunc.Board()
# Clear Screen function
def refresh_screen():
  os.system("clear")
  board.display()
# Display the board
board.display()


''' Task 2: Player X - Get Set Go!!'''

while True:
  refresh_screen()
#  # Get X input
  x_choice=int(input("PLAYER X: Please choose a number between 0 - 8: "))
#  #Update board
  while(board.update_cell(x_choice,"X")==-1):
    x_choice=int(input("PLAYER X: Please choose a number between 0 - 8: "))
  board.update_cell(x_choice,"X")  

#  # Refresh the screen
  refresh_screen()
#  #Check if X is the winner
  if board.is_winner("X")==True:
    print("\nX is the winner")
    replay=input("\nDo you want to play again (Y/N): ")
    if replay.upper()=="Y":
      board.reset()
      continue
    else:
      break  
#  #Check for tie
  if board.is_tie():
    print("\nTie Game")
    replay=input("\nDo you want to play again (Y/N): ")
    if replay.upper()=="Y":
      board.reset()
      continue
    else:
      break
  o_choice=int(input("PLAYER O: Please choose a number between 0 - 8"))
 #Update board
  while(board.update_cell(o_choice,"O")==-1):
   o_choice=int(input("PLAYER O: Please choose a number between 0 - 8: "))
   board.update_cell(o_choice,"O")
  # Refresh the screen
   refresh_screen()
 #Check if O is the winner
   if board.is_winner("O")==True:
    print("\nO is the winner")
   replay=input("\nDo you want to play again (Y/N): ")
   if replay.upper()=="Y":
     classfunc.board.reset()
     continue
   else:
     break
 #Check for tie
  if board.is_tie():
   print("\nTie Game")
   replay=input("\nDo you want to play again (Y/N): ")
   if replay.upper()=="Y":
     board.reset()
     continue
   else:
     break        

''' Task 3: Player O - Get Set Go!!'''
# Complete the code for Player O, in exactky the similar way it is done for Player X
# The key tasks to complete are:
# - Get the input from player O
# - Update the board
# - Check if O is the winner
# - Check for a tie
# NOTE: The code should be within the while loop. So to avoid any error you can continue coding after Task 2.

