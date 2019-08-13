## 1. JRPG - Beast Brawler

### 1.1. Overview
Beast Brawler is a very short demo "JRPG" where the player controls a 'brawler' who must traverse his or her home island searching for the cause of the terrible darkness that has enveloped the land.  The player must grind beasts in order to build experience points to level up and gain gold to buy upgraded weapons and armour.  

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

* Exploration System (walking around the Overworld and the various environments.
* Battle System (inspired by NES style JRPGs like Dragon Warrior/Quest; Turn based and facing enemies viewing from hero's perspective).
* Menu System (inspired by SNES style JRPGs like Final Fantasy 2/3)
* Message Window System (inspired by the same games above. i.e. text bubbles at the bottom of the screen).

### 2.1.1 Exploration System
The player should be able to walk around the 'world', which is just an map/board encompassing the hero's home island.  When the user steps onto tiles that represent locations, the player should be transported to the starting location of the target locale (standard JRPG). 
As the player walks around the overworld or hostile locations, they should randomly be attacked by beasts that roam there. When a beast attacks, the player is transported to the Battle System view and faces the enemy and must fight until either the hero of the beast dies (or one of them run away). See section 2.1.2 for details. 
Depending on the location on the overworld or within hostile locations, the beasts that attack should vary.  Generally, the further the hero goes, the more difficult the beasts should become.  See section xxx for frequency distribution details.
The player can use the 'activation' button to speak with NPCs (non-player characters), or interact with buttons, switches, doors, etc.

### 2.1.2 Battle System

### 2.1.3 Menu System

### 2.1.4 Message Window System

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
