## Info
All enemies that can be killed (even some that can't normally be killed) have droptables. These droptables handle what drops enemy leaves when it dies.
Droptables are consistent, meaning you'll always get the same order, so this can be used to our advantage in runs to get optimal lightnings or buffs.
 
There are 4 tiers of droptables (depending on enemy difficulty). Each tier has a "super tier" which gives better drops. There are 2 ways to get super tier:
1. Kill 10 enemies of same tier - without taking damage AND without loading other scenes
2. (if you change scenes) Kill 30 enemies of ANY tier (taking damage doesn't break the chain)
Note that getting super tier by one method will reset the other counter (eg. Killing 10 enemies without changing scenes will reset the other counter (for 30) to 0).
Note that getting a super tier will not skip a drop for normal tier, it just won't count that kill for normal tier.
 
Certain events can change these droptables to make certain items guaranteed or more likely. There are 2 known events that do this:
- Sunshine weather: (random in overworld) For 15-30 seconds, has an 85% chance to replace any heart drop with a lightning
- Hearty status: For 60 seconds, replaces all red heart drops with blue hearts
 
Droptables are saved in save file and each tier is saved separately, so you can have multiple tiers going at once.
 
The items you can get from droptables are:
- Hearts (red, blue, and yellow)
- Fruits for status buffs (tough, dire hit, mighty, hearty)
- Lightnings
 
Normal drop tables always have 16 elements while super tables have 2. Let's look at how the droptables are organized for each tier:
 
## Droptable List
 
### Tier 1
| Index | Item          |
| ----- | ------------- |
| 0     | Heart (red)   |
| 1     | N/A           |
| 2     | N/A           |
| 3     | N/A           |
| 4     | Heart (red)   |
| 5     | N/A           |
| 6     | N/A           |
| 7     | N/A           |
| 8     | N/A           |
| 9     | Heart (red)   |
| 10    | N/A           |
| 11    | N/A           |
| 12    | N/A           |
| 13    | Heart (red)   |
| 14    | N/A           |
| 15    | Apple (Tough) |

### Tier 1 (super)
| Index | Item              |
| ----- | ----------------- |
| 0     | Lightning         |
| 1     | Grapes (Dire Hit) |
 
### Tier 2
| Index | Item            |
| ----- | --------------- |
| 0     | Heart (red)     |
| 1     | N/A             |
| 2     | N/A             |
| 3     | Heart (red)     |
| 4     | N/A             |
| 5     | N/A             |
| 6     | Heart (red)     |
| 7     | Lightning       |
| 8     | N/A             |
| 9     | Heart (red)     |
| 10    | Heart (red)     |
| 11    | N/A             |
| 12    | N/A             |
| 13    | Heart (red)     |
| 14    | N/A             |
| 15    | Banana (Mighty) |

### Tier 2 (super)
| Index | Item                |
| ----- | ------------------- |
| 0     | Heart (blue)        |
| 1     | Strawberry (Hearty) |
 
### Tier 3
| Index | Item              |
| ----- | ----------------- |
| 0     | Heart (red)       |
| 1     | N/A               |
| 2     | Heart (blue)      |
| 3     | N/A               |
| 4     | Heart (red)       |
| 5     | Heart (red)       |
| 6     | Lightning         |
| 7     | Heart (red)       |
| 8     | N/A               |
| 9     | Heart (blue)      |
| 10    | N/A               |
| 11    | N/A               |
| 12    | Heart (red)       |
| 13    | N/A               |
| 14    | Heart (red)       |
| 15    | Grapes (Dire Hit) |
 
### Tier 3 (super)
| Index | Item                |
| ----- | -------------- |
| 0     | Heart (yellow) |
| 1     | Apple (Tough)  |
 
### Tier 4
| Index | Item                |
| ----- | ------------------- |
| 0     | Heart (blue)        |
| 1     | Heart (red)         |
| 2     | Heart (blue)        |
| 3     | Heart (red)         |
| 4     | Lightning           |
| 5     | Heart (red)         |
| 6     | Heart (blue)        |
| 7     | Heart (red)         |
| 8     | N/A                 |
| 9     | Heart (blue)        |
| 10    | Heart (red)         |
| 11    | N/A                 |
| 12    | Heart (blue)        |
| 13    | Heart (red)         |
| 14    | Heart (blue)        |
| 15    | Strawberry (Hearty) |
 
### Tier 4 (super)
| Index | Item            |
| ----- | --------------- |
| 0     | Heart (yellow)  |
| 1     | Banana (Mighty) |
 
## Enemy Tier Assignments
 
### Tier 1
- Fishbun
- Safety Jenny
- Shellbun
- Cowbun
- Stupid Bee
- Candy Snake (coast)
- Mimic
- Hyperdusa (green)
- Gate (grey)
 
### Tier 2
- Hatless Ogler
- Ogler
- Spikebun (small)
- All Turnips with weapons
- Volcano (stationary)
- Rotnips
- Rest of the Mimics
- Hyperdusa (blue)
 
### Tier 3
- Shark Jenny (out of water)
- Volcano (cart)
- Spikebun (gold)
- Bunboy
- Angry Bee
- Dark Ogler (+2 to DT count)
- Jello (red)
- Brutus
- Skullnip
- Skullnip (snow)
- Jello (green)
- Candy Snake (lonely)
- Big Ogler
- Gate (red)
 
### Tier 4
- Coldnip
- Constructs (all)
- Flower Jenny
- Slayer Jenny
- Lemon Jenny
- Hexrot (ice)
- Hexrot (fire)
- Chilly Roger
- Arch Triangle
- Mercury Jello (can't be killed tho)