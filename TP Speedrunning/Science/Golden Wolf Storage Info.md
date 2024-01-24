# Golden Wolf Storage (GWS)
Glitch found by Zac: [video](https://www.youtube.com/watch?v=lIqrX_CR75I) | [Discord message](https://discord.com/channels/83003360625557504/354966434243280896/950987370122076190)
 
## Explanation
When you enter the Hero's Shade realm, the game stores which wolf you entered from, with an exception being the North Faron one. Upon exiting the Hero's Shade realm, you return to the stored wolf spawn location. However, the game uses 6 flags to know which wolf you entered from, and if these flags are swapped around, you can exit to different wolves, essentially "wrong warping."
 
## Technical
Within the temp region of memory, Golden Wolves use 2 addresses: 80406FA2 and 80406FA3 to store which wolf you entered from, and it uses these values to know which location to take you to upon exiting the Hero's Shade realm. When values are written to these addresses, they set certain flags that normally get cleared when exiting the wolf.
 
Each wolf address, hexadecimal value, and which flag it sets:

| Address  | Wolf          | Hex  | Flag   |
| -------- | ------------- | ---- | ------ |
| 80406FA2 | Ordon Spring  | 0x04 | 0xa04  |
| 80406FA2 | West CT       | 0x02 | 0xa02  |
| 80406FA2 | South CT      | 0x01 | 0xa01  |
| 80406FA3 | Desert        | 0x80 | 0x0b80 |
| 80406FA3 | Kak Graveyard | 0x40 | 0x0b40 |
| 80406FA3 | North CT      | 0x20 | 0x0b20 |
| 80406FA3 | North Faron*  | ---- | ------ |
 
**North Faron wolf is hardcoded to spawn you at North Faron, so it doesn't use either address. But its spawn location can be accessed from other wolves within the `80406FA3` address by having a value below `0x20` when exiting.*
 
When you enter a wolf, it will always set its associated flag if it isn't already set, and will clear its flag on exit. But if you have other flags set upon entering, you can change the exit. For example, if you were to enter Kak graveyard wolf with a value of `0x80` (flag 128), entering the wolf would add `0x40` (flag 64). Since flag 128 remains set, exiting wolf will use the higher number to determine which flag it cares about. In this case, exiting will clear flag 64, but use flag 128 to spawn you at desert, and doesn't clear this flag either.
 
If you exit a wolf without having its flag set (eg. exit Kak graveyard wolf without flag 64 being set) (note: this is only possible with hacks), it will jump to the other GWS address for where to exit. As an example, if you somehow cleared South CT wolf's flag 1 while in the Hero's Shade realm, and `80406FA3` has a value of `0x20` (flag 32) set, exiting South CT wolf would take you to North CT exit.
 
[More technical mumbo jumbo](https://discordapp.com/channels/955542723782389820/955543849529409606/1063855281538338826) (TP devs server)
 
## Additional Notes
- GWS addresses are reused through various events, some of which are documented here, but there may be more:
	- Talking to Fado for goats 1 prompt sets `80406FA2 => 0x10` (flag 16)
	- Entering Link's house after goats 1 sets `80406FA3 => 0x04` (flag 4)
- Cutscenes that clear TD do not clear GWS
- Savewarping & BiT clear GWS
- The flags for addresses are: 1, 2, 4, 8, 16, 32, 64, 128. Flags 8 and 16 are unused for golden wolves
- Getting Ending Blow from any wolf doesn't clear the wolf's flags. So for example, getting Ending Blow from Ordon Spring wolf will keep 0x04 set instead of clearing it on exit as normal.
 
## TP Being TP Again
Notice that North CT is the lowest priority for wolves in the `80406FA3` address. Because of that, it will never be possible to use GWS to do EHC, as any flag set on `80406FA3` will be of a higher priority, resulting in exiting to a different wolf.