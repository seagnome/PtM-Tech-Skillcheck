<span style="color:red"></span>

# Skill Check Connections

## Objects
All objects directly involved in the skill test.

### Dinorville, Door Guard NPC
Dinorville is an NPC guarding the door to the tavern. They have edited stats (and size), originally based on the BASE_Dilophosaurus_NPC character. They can be convinced via a Deception skill check to open the door. They also carry a key to open the door.

### Hidden Button 
The button is hidden and uninteractable by default, and can be revealed by a perception check rolled near the corner of the building closest to the doors (which was easiest for testing purposes). When used, the button will change the status of the door from opened to closed or vice versa.

### Area Trigger (Invisible)
This was added to facilitate the perception check to discover the hidden button. 

### Doors 
The doors begin the level locked, and can be unlocked by using the button, the key, or by deceiving Dinorville. 

### Player Character
The player character is already in the provided level, and is referenced in scripts and the dialog. 

## Dialog

### dino1.lsj 
The sole dialog file is for the player to talk to Dinorville. There are options to leave the conversation or try to deceive them into opening the door. 
I did throw in an extra flag at the start, but I was unclear on the intention of having it be there after talking to the NPC, so I didn't expand on it given my limited time frame. 
Succeeding in the deception attempt will set a flag to open the door, which is checked upon exiting the conversation with Dinorville. 

## Scripts 

### Deception Check 
This script checks if Dinorville was successfully deceived, activating at the end of conversation with them. If they have, it unlocks and opens the door. This script references the dialog file, the flag set after deceiving Dinorville, 
and the doors (opening them). 
This script caused me the biggest headache, because I kept getting walled by referencing the wrong IDs for DialogEnded. 

### HiddenButton
This script rolls a perception check to see if the player finds the hidden button when they're in its vicinity. If they succeed, the button reveals itself to the player and becomes interactable. 
This script references the player (and their perception roll), the button, and the area trigger. 
The entirety of this script was taken from the Modding discord, in the #guides-and-tutorials > Discovered Hidden Object Shimmer thread. 

### OpenDoor
This script allows the player to use the button to open and close the doors. 
This script references the player, the button, and the doors. 
This script was also sourced, from a very informative video made by Mit on Youtube - https://www.youtube.com/watch?v=PVdf1x0UnT8