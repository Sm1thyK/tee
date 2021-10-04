I watched only one hint and this outcome 

############### Blackjack Project #####################
from replit import clear
import random
from art import logo
import time 
#Difficulty Normal 😎: Use all Hints below to complete the project.
#Difficulty Hard 🤔: Use only Hints 1, 2, 3 to complete the project.
#Difficulty Extra Hard 😭: Only use Hints 1 & 2 to complete the project.
#Difficulty Expert 🤯: Only use Hint 1 to complete the project.
############### Our Blackjack House Rules #####################

## The deck is unlimited in size. 
## There are no jokers. 
## The Jack/Queen/King all count as 10.
## The the Ace can count as 11 or 1.
## Use the following list as the deck of cards:
cards = [11, 2, 3, 4, 5, 6, 7, 8, 9, 10, 10, 10, 10]
## The cards in the list have equal probability of being drawn.
## Cards are not removed from the deck as they are drawn.
## The computer is the dealer.

player_card = [10, 10, 5]
computer_card = []
def P_C_SCORE():
  player_Computer_list = [SCORE(player_card), SCORE(computer_card)]
  return player_Computer_list 
# --------------------Create card--------------------
def card_random():
  NUM = random.randint(0, 12)
  return cards[NUM]
def player_list():
  for score in range(2):
    player_card.append(card_random())
  return player_card
def computer_list():
  for score in range(2):
    computer_card.append(card_random())
  return computer_card
# --------------------finding blackjack--------------------
def BLACKJACK(SCORE):
  for N in SCORE:
    if SCORE[0] == 21:
      End_SUM()
      print("==============================")
      print("You are winner")
      print("==============================")
      player_card.clear()
      computer_card.clear()  
      return "True"
    elif SCORE[1] == 21:
      End_SUM()
      print("==============================")
      print("You are lose")
      print("==============================")
      player_card.clear()
      computer_card.clear()  
      return "True"
# --------------------Score over 21-------------------- 
def finding_11(User_list):
  for N in range(0,len(User_list)):
    if User_list[N] == 11:
      return N 
  return N
def player_over_21 ():
  while SCORE(player_card) > 21 :
    if player_card[Num] == 11:
      player_card[Num] = 1
    elif player_card[Num] != 11:
      print("==============================")
      print("You are lose")
      print("==============================")
      player_card.clear()
      computer_card.clear()  
      return "True" 
  return "False"

# --------------------include score--------------------
def SCORE(any_score):
  all_score = 0
  for Score in any_score:
    all_score += Score
  return all_score
# --------------------Display--------------------
def Start_SUM ():
  print(f"------------------------Computer------------------------")
  print(f"Computer's Card: {computer_card[0]} ?")
  print(f"------------------------Player------------------------")
  print(f"player's Card: {player_card} your score: {SCORE(player_card)} ")
def End_SUM ():
  print(f"------------------------Computer------------------------")
  print(f"Computer's Card: {computer_card}")
  print(f"------------------------Player------------------------")
  print(f"player's Card: {player_card} your score: {SCORE(player_card)} ")

# ----------------------------------------------



big_loop = False
while not big_loop:
  loop = False
# ==============START==============
  print(logo)
  computer_card.clear()  
  player_card.clear()
  player_list()
  computer_list()
  while not loop :
# ================================
    Start_SUM()
# check Blackjack 
    if BLACKJACK(P_C_SCORE()) == "True":
      time.sleep(5)
      break
# Score over 21
    Num = finding_11(player_card)
    if player_over_21() == "True":
      time.sleep(5)
      break
    elif player_card[Num] == 1 :
      clear()
      Start_SUM()

    Q1 = str(input("Do you want another card ?///Y or N: ")).lower()
    if Q1 == "y":
      player_card.append(card_random())
    elif Q1 == "n":
      break
  
  while not SCORE(computer_card) >= 17 and SCORE(computer_card) <= 21 and computer_card != []:
    print ("I want another card!!")
    time.sleep(2)
    computer_card.append(card_random())
    SCORE(computer_card) > 21
  if SCORE(computer_card) > 21:
    End_SUM()
    print("==============================")
    print("You are Win")
    print("==============================")
    time.sleep(5)
  elif SCORE(player_card) > SCORE(computer_card):
    End_SUM()
    print("==============================")
    print("You are Win")
    print("==============================")
    time.sleep(5)
  elif SCORE(player_card) < SCORE(computer_card):
    End_SUM()
    print("==============================")
    print("You are lose")
    print("==============================")
    time.sleep(5)
  elif SCORE(computer_card) == 0:
    print("")
  else :
    End_SUM()
    print("==============================")
    print("You are Draw")
    print("==============================")
    time.sleep(5)
  Q2 = str(input("Do you want to play again ?/// Y or N: "))
  if Q2 == "n":
    break
    
  clear()

I did a lot differently. it was a maze but it could run
