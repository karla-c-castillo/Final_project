### DO NOT CHANGE CODE IN THIS BLOCK ###
import random

# Enemies defined in different dictionaries
vampire = {"name": "Vampire", "attack":"1d5", "defense": "1d3", "maxhp":50, "curhp":50 }
goblin = {"name": "Goblin", "attack":"1d3", "defense": "1d1", "maxhp":30, "curhp":30 }
ghost = {"name": "Ghost", "attack":"1d5", "defense": "1d5", "maxhp":50, "curhp":50 }
dracula = {"name": "Dracula", "attack":"2d5", "defense": "1d4", "maxhp":200, "curhp":200 }

# A LIST of DICTIONARIES for enemies
enemies = [vampire, goblin, ghost, dracula]

# Player dictionary
player = {"name":"", "attack":"2d5", "defense": "1d3", "maxhp":200, "curhp":200}
###########################################
# START YOUR CODE BELOW THIS LINE
###########################################
# NAME: KARLA CASTILLO CARRILLO
# Project Python - Final
# Professor Rich
# MGT 205 Information Systems
##############################

# Global variable value trackers
total_enemy = 0
total_player = 0

def do_battle(player, enemy):
# print enemey and player
  print(player['name']," encounters a random",enemy['name'])

  # store player name into player 1 ..etc
  player_one = player['name']
  player_two = enemy['name']

  # store their current hitpoints 200 hp for player
  player_one_health =  player['curhp']
  player_two_health = enemy['curhp']

  # Loop until someone dies.....
  while(True):
    # roll for both players
    player_turn_attack = get_roll(player['attack'])
    player_turn_defense = get_roll(player['defense'])

    enemy_turn_attack = get_roll(enemy['attack'])
    enemy_turn_defense = get_roll(enemy['defense'])

    total_player = get_damage(player_turn_attack,player_turn_defense) # ex '3d5'-'1d5' = total damage
    total_enemy = get_damage(enemy_turn_attack,enemy_turn_defense) # 

    print(f"{player_one},does {total_enemy} damage to {player_two}") # string interpolation for player and dmg
    print(f"{player_two},does {total_player} damage to {player_one}") # string interpolation for enemy and dmg

    player_one_health -= total_player # current hit = current hit - get dmg
    player_two_health -= total_enemy # ditto but for enemey

    # print only if health is greater than or equal to 0 so no non negative numbers
    if(player_one_health >= 0):
      print(player['name'],"hp: ",player_one_health)
    
    if(player_two_health >= 0):
      print(enemy['name'],"hp: ",player_two_health)

   # If enemy health is <= 0 ever, return true, others return false for player
    if(player_two_health <= 0):
      return True
    if(player_one_health <= 0 ):
      return False

def get_damage(attack, defense):
  damage = 0
  if(defense > attack):
    return damage
  else:
    return int(attack)-int(defense)

def get_roll(rollstring):
  # parsing '3d5' for example i = rollstring[0] = 3
  i = (int(rollstring[0]))
  j = (int(rollstring[2])-1) # j = rollstring[2] = 5
  accumulator = 0 # store total
  start = 0
  for x in range(start,i): # loop until n = 0 < i = 3
    accumulator += random.randint(0,j) # Random number 0 <-> j = 5 in ex

  return accumulator # return total = 3d5 so 3 loops between random numbers 0-5 for ex

# This is a complete function; do not modify
def main_menu_goto_battle():
    enemy = enemies[random.randint(0,len(enemies)-1)]
    if do_battle(player, enemy):
        print(f"The {enemy['name']} has died, hurray!")
        enemy['curhp'] = enemy['maxhp']
        input("Press enter to return home")
    else:
        print(f"Oh no! {player['name']}")

    return

# This is a complete function; do not modify
def main_menu_heal():
    print(f"The player takes rest under a healing fountain. HP restored!")
    player['curhp'] = player['maxhp']
    input("Press enter to return home")
    return

# This is a complete function; do not modify
def main_menu():
    # Player dies if player HP reaches 0 or less
    while player['curhp'] > 0:
        # Display menu
        print(f"{player['name']} currently has {player['curhp']} hp\n")
        print("1 : Go to Battle")
        print("2 : Heal")

        x = input("What to do next > ")
        # Get input from player
        if x =="1":
            main_menu_goto_battle()
        elif x=="2":
            main_menu_heal()
        else:
            print("No such action")

    print("Player is dead!")

###### DO NOT CHANGE THIS CODE #########
player['name'] = input("What is the player's name? ")
main_menu()
########################################
