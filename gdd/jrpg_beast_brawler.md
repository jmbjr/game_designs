## 1. JRPG - Beast Brawler

### 1.1. Overview
Beast Brawler is a very short single player demo "JRPG" where the player controls a 'brawler' who must traverse his or her home island searching for the cause of the terrible darkness that has enveloped the land.  

In Beast Brawler a single hero will battle one or more enemies as he or she travels the land searching for a way to vanquish the BeastLord. Along the way the hero will join forces with an unlikely partner to help the Hero save the day.  

The player must grind beasts in order to build experience points to level up and gain gold to buy upgraded weapons and armour.  

The player must also gather the necessary items to gain access to the BeastLord's lair and vanquish said BeastLord in order to free the land of the BeastLord's tyranny.  

The game should be simple enough that an inexperienced game designer should be able to implement the game "quickly" in the framework/platform/language of thier choice.  Ideally this could be implemented over the weekend (focused effort with a few team-mates) or 1-2 weeks as a solo inexperienced developer.  

### 1.2 Vision Statement
The player should be delivered the following experiences:
* Classic JRPG experience.  Nothing fancy here.
* Quick to complete. 5-15 minutes.  
* Groaning at stupid jokes to help the 5-15 minutes go by quickly.

The game designer should be delivered the following experiences:
* Gain familiararity with commonly used rpg systems (XP, Gold, inventory, special moves, conditional goals, along with presenting a story with a beginning, middle, and end.
* Gain confidence in completing a game where all of the pieces have been provided, they just need to put them together.  
* Opportunity to compare their implementation with other developed implementations to compare/contrast approaches and styles.  There are no wrong answers!

## 2. Core Gameplay


### 2.1 Game Subsystems
Because Beast Brawler is a standard "JRPG", there are the standard JRPG subsystems/ to implement:

* Exploration System (walking around the Overworld and the various environments).
* Battle System (inspired by NES style JRPGs like Dragon Warrior/Quest; Turn based and facing enemies viewing from hero's perspective).
* Main Menu System (inspired by SNES style JRPGs like Final Fantasy 2/3)
* Message Window System (inspired by the same games above. i.e. text bubbles at the bottom of the screen).
* Misc Routines
### 2.1.1 Exploration System
* The player should be able to walk around the 'world', which is just an map/board encompassing the hero's home island.  When the user steps onto tiles that represent locations, the player should be transported to the starting location of the target locale (standard JRPG).  
* As the player walks around the overworld or hostile locations, they should randomly be attacked by beasts that roam there. When a beast attacks, the player is transported to the Battle System view and faces the enemy and must fight until either the hero of the beast dies (or one of them run away). See section 2.1.2 for details.   
* Depending on the location on the overworld or within hostile locations, the beasts that attack should vary.  Generally, the further the hero goes, the more difficult the beasts should become.  See section xxx for frequency distribution details.
* The player can use the 'activation' button to speak with NPCs (non-player characters), or interact with buttons, switches, doors, etc.

### 2.1.2 Battle System
* The battle system consists of several components. 
  * Enemy Layout Panel
  * Enemy Name List Panel
  * Hero Stats Panel
  * Player Battle Options Menu
  * Battle Message Log

* Additionally the battle system must implement the following logical systems/checks/routines
  * "Won the Battle" logic
    * If at the start of a battle turn, all enemies are defeated, the following should occur:
      * For each enemy defeated, award the hero party that enemy's XP (experience points) value
      * For each enemy defeated, award the hero party that enemy's gold value
        * divide the hero party experience by the number of current heroes in the party and increase each hero's current XP by that much
        * if this advances a hero's current XP to equal or greater than the XP required for the next level, run the "Player Leveled Up" logic
        * Update the Battle Message Log.
          * Thou has done well in slaying the foul beasts!
          * Fortune smiles upon thee as your heroes hath gained $value Experience Points and $value Gold pieces.
          * if "Player Leveled Up" then: $playername has gained a level! (then display the updated stats in the Hero Stats Panel. See "Player Leveled Up" logic for details.
  * "Lost the Battle" logic
    * If at the start of a battle turn, all heroes have 0 HP, the following should occur:
      * Change the border color of the Battle Message Log and the font to red.
      * Update the Battle Message Log.
        * Thou hast been defeated! []
      * When the player presses the activation key, run "Reload Heroes After Death" routine
 
* The typical battle flow is:
  * Determine what kind and how many enemies to fight
  * Draw the enemies into the Enemy Layout Panel
  * Display the names of the enemies in the Enemy Name List Panel
  * Display the Hero stats in the Hero Stats Panel
  * Display the default battle options for the hero in the Player Battle Options Menu
  * Display initial battle log text: "A gaggle of slime approaches!"
  * Enter the main battle system loop
    * Check if all enemies are defeated. If so, run "Won the Battle" logic
    * Check if the heroes are defeated. If so, run "Lost the Battle" logic 
    * Determine next entity to act. This will be the entity with the current highest initiative stat.
    * if an enemy has highest initiative:
      * reset their initiative to their starting initiative
      * highlight enemy
      * enemy fight!!!
      * handle stat changes
      * Update Battle Message Log
    * if a player has highest initiative:
      * reset their initiative to their starting initiative
      * highlight player
      * allow Player Battle Menu Option navigation
      * handle picked option
      * handle stat changes
      * Update Battle Message Log
    * Update initiative for all currently alive entities (initiative += delta_initiative)
    
  
### 2.1.3 Main Menu System
* The Main Menu System consists of 
### 2.1.4 Message Window System

### 2.1.5 Misc Routines
* Player Leveled Up
* Reload Heroes After Death

### 2.2 Inputs
This could be somewhat limited based on the platform/framework/language that is picked, but ideally should support:
* Keyboard + Mouse
* Standard 8 button controller (i.e. SNES style or better)
* Touch inputs for mobile devices (Probably difficult or impossible (or expensive) with some frameworks/platforms)

Player should be able to move up/down/left/right. Not diagonal (for Classic reasons).  
There should be a key to bring up the main menu (where the user can access sub-menu items. see 2.1.3.).  
There should be an 'activation' key that the user will use to speak to NPC or to interact with the environment (open doors, click buttons, etc) or to confirm actions in the Battle System or Menus.
When interacting with the Message Window System the user should have a button to speed up the display of the text (see 2.1.4).
There should be a 'cancel' key that the user can use to 'cancel' an activation action (with NPCs, environment actions, in battle, or in the menus).
All controls should be configurable with thought given to accessibility (reference a good guide for designing for accessibility)

## 3. Environment
 
