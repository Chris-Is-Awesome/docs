## INTRO
You can modify the save files to hack items, auto-complete puzzles, pre-set anything in dungeons, including boss defeats, and much more!
 
First and foremost, a disclosure: This is a form of hacking and is therefore not allowed in speedrunning! If found hacking in a run, your run will be removed and you will be banned from submitting runs to the ID2 leaderboards. Furthermore, there is a chance that if you mess up the code, you can corrupt the save. A corrupted save would not affect the game as a whole, just delete corrupted save and you'll be good!
 
## INFO
ID2 stores save files under the following directory:
 
`C:\Users\[YourName]\AppData\LocalLow\Ludosity\Ittle Dew 2\steam`
 
Each save is labeled as:
 
`file_#.id2`
 
With # being the save slot #.
 
## HOW TO
This doesn't take knowledge of programming, but you do have to be able to skim through 2k+ lines of code to find what you need. The most useful values will be detailed under "DETAILS" section below.
 
To set up a file, you want to start with a legit (unhacked) file already. Go to where the save is stored, open the file in a text editor, copy the code, paste code into a new file and change what you want. Or you can start from scratch if you're more advanced.
 
**IMPORTANT! When saving a file, do save as, no extension, and name it exactly as how the others are ("file_#.id2").**
 
To change a value, simply open the file you want to modify (ie. file_1.id2) inside a text editor or IDE and you can view the file's code. Every value you can think of can be changed from here, from having certain items, setting bosses as defeated, auto-completed puzzles, etc.! It takes some getting used to to figure out what values refer to what, as the variable names are not always clear :p
 
To change true or false (bool) values, 1 = true, 0 = false. Example of a bool value is:
 
`PuzzleDoor_red-4-70: 1;`
 
That value represents a red locked door (meaning enemy combat) in the dungeon of the class that it's in, in this case:

```
    BoilingGrave {
      player {
        vars {
          localKeys: 0;
        }
        seenrooms {
          Y: 1;
          T: 1;
          S: 1;
		......
        }
      }
      R {
        PuzzleDoor_red-4--70: 1;
      }
```

Notice the name "Boiling Grave" at the top. Everything listed below that until the next name falls under that area. So this means "PuzzleDoor_red-4--70" is a combat door inside of Boiling Grave. The exact door is specified by the "R" above it. To get what room the letter leads to, it's trial and error, since the code doesn't make it clear lol But it's the letters used under "seenrooms"
 
Yes, there is a crap load of detail I could give on this but instead of spending weeks writing this, I'll let you figure it out ;)
 
## DETAILS
The main values you might want to change are listed here. I'm skipping over hundreds of other values for the sake of time and simplicity.
 
CTRL + F IS YOUR FRIEND!! Note that anything after the "//" is a comment and is not part of the code. Also, every variable line must end in a semicolon!
 
## Player Inventory
``` 
player
{
	maxHp: // 20-40 are normal ranges
	hp: // Current HP, 20-40 are normal ranges
	vars
	{
		shards: // 0-24 normal
		keys: // # of lock picks
		forcewand: // 1-4, do not write this line if you don't want item (note: 4 is unused lv 4 Force Wand)
		melee: // 1-3, do not write this line if you don't want item (1 = Fire Sword, 2 = Fire Mace, 3 = Chainsaw)
		raft: // # of raft pieces (1-8)
		chain: // 1-3, do not write this line if you don't want item
		amulet: // 1-3, do not write this line if you don't want item
		dynamite: // 1-4, do not write this line if you don't want item (note: 4 is unused lv 4 Dynamite)
		hpcs: // # of boxes of crayons, idk if this affects your health or not (too lazy to test :p)
		icering: // 1-4, do not write this line if you don't want item (note: 4 is unused lv 4 Ice Ring)
		headband: // 1-3, do not write this line if you don't want item
		evilKeys: // # of Forbidden Keys (for S4), 0-4
		tracker: // 1-3, do not write this line if you don't want item
		tome: // 1-3, do not write this line if you don't want item
		usedEvilKeys: // # of keys already in S4 entrance (choosing 4 will unlock S4), 0-4
		outfit: // 0-10 (0-7 are normal, 8 = Apathetic Frog, 9 = That Guy, 10 = Jenny)
	}
}
```
 
## Dungeon Presetting
I'm not going into full detail here but I'll give baseline. Note that anything in brackets ([]) means to substitute what's in the brackets with the exact casing and remove the brackets.
 
```
[DungeonName]
{
	player
	{
		vars
		{
			localKeys: // Number of keys for that dungeon
		}
	}
	logic
	{
		clearedBoss: // Is boss dead or alive? 0 = false, 1 = true
	}
}
```
 
You can specify certain puzzles as complete, but I don't understand the numbering system the code uses so I won't go into that. If you want to preset dungeons, it's easier to just copy the code from a file with the dungeon completed, and paste that code into a new file and change the values from there.
 
Room Values:
Overworld sections, dungeons, portal worlds, and secret areas (ie. Ludo City, Nowhere, etc.) have unique maps. You can access each area's map in code if you know how to reference them. There's way too many to list, but I'll list a few goodies:
 
- All portal worlds and secret areas (with one exception listed below) are labeled as "deep#". So for example, deep1, deep2, deep20, etc. Goes up to 24
- The one exception to the above rule is Promised Remedy (where you get the That Guy outfit). The devs made this area secret to hide it from people trying to hack the save file (like you :p), so they made its value "deep19s" instead of "deep19". "deep19" will instead put you in a test room (see EXTRAS section below!)
- Large areas are split into chunks. Pepperpain Prairie (or VitaminHills in code) for example is split into 3 sections ("VitaminHills1" - West chunk, "VitaminHills2" - East chunk, "VitaminHills3" - North chunk).
- Dungeons are not split into chunks except for Grand Library. The dungeon itself is "GrandLibrary1" whilst the hallway named The Shifting Chamber leading to Passel is labeled "GrandLibrary2".
- Each map has a default spawn point named "StartPoint". This was likely used as a fail safe in case the door value under Start were to ever return null. StartPoints are a unique spawn point that in some cases, would be very convenient to speedrunners (one such case is StartPoint in Tomb of Simulacrum being right in front of chainsaw chest, allowing for 90% of the dungeon to be skipped). Other StartPoints are right near normal entrance or in some odd location (ie. Lonely Road's is near Northern End cave entrance).
- Loading zones, checkpoints, and portals reset door value. Loading zones and portals reset level value.
 
## EXTRAS
Some names within the code are different from actual game. This is likely due to name changes throughout development. An instance of this is Pepperpain Prairie being named "VitaminHills" in code.
 
In the directory with the saves, there are two other files: "default.id2" and "global.id2". Best to leave them alone, but deleting them does nothing as default controls new file creation and global is settings configuration (namely controller inputs) and both are reset on game load. Also, thumbnails of all saves (deleted or not) are stored here as well. Deleting a used thumbnail will result in an X image for the thumbnail in game.
 
UNUSED ITEMS ARE SUPER OP!! Force Wand, Dynamite and Ice Ring have secret Lv. 4 upgrades that can only be accessed by changing their values in code! Furthermore, there's space in health bar for two rows, but second row was likely scrapped as devs felt it was too much health. https://www.youtube.com/watch?v=9cgH9gELl8g&feature=youtu.be
 
Secret test room if you set room under Start to "deep19" (was used in place of "deep19" which is Promised Remedy as an attempt to fool those trying to hack a save file :p (FYI: To access Promised Remedy, room is "deep19s") https://www.youtube.com/watch?v=g3Q-9f1-XP0