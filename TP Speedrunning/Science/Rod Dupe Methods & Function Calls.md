Crossposted from [this Discord message](https://discordapp.com/channels/83003360625557504/354966434243280896/607346228338098186) from DB
 
### Works for sure
- re-grabbing something climbable mid air
- getting on Epona or a boar
- jumping on the ice board in Snowpeak 2nd half (I don't think this function is used elsewhere)
- Catching a red angry goat with A on the Ordon Ranch (I don't think this function is used elsewhere)
- Getting force transformed to wolf outside of a cutscene (I can only think of the black fog in Palace)
 
### Next things that might be hopeful
- somehow pulling rod and still triggering mortal draw on the correct frame
- somehow pulling rod and spinner at the same time (wouldn't be useful for poe skip)
- `procCutFinishJumpUpInit` (something backslice? idk what this is, but might be useful)
- `checkCaughtEscapeCutTurn` (no clue)
- `procPickPut` (no clue)
- finding bottle dupe in SD
- finding quick transform in SD
 
### Status: Works
 
- `daAlink_c::setClimbStartNotGround` (re-grabbing something climbable mid-air, e.g. ladders, vines)
- `daAlink_c::checkNormalAction` --> `daAlink_c::procHorseRideInit` (getting on Epona or Boar)
- `daAlink_c::checkGroundSpecialMode` --> `daAlink_c::procCoMetamorphoseInit` (force transform, triggered when you are standing on special ground, e.g. black fog) (HD can trigger this at any point using quick transform)
- `daAlink_c::checkNormalAction` --> `daAlink_c::procBoardRideInit`  (pressing A to get on the ice board in Snowpeak)
- `daAlink_c::checkNormalAction` --> `daAlink_c::procGoatCatchInit` (catching an angry goat on the ranch with pressing A)
 
 
### Status: Works, but not accessible while pulling rod
 
- `daAlink_c::checkNormalAction` --> `daAlink_c::changeCutFast` (A to mortal draw, can't trigger it after pulling rod)
- `daAlink_c::checkGroundSpecialMode` --> `daAlink_c::procGoatMoveInit` (entering the goat wrangling minigame in Ordon Day 2)
- `daAlink_c::checkGroundSpecialMode` --> `daAlink_c::procSumouReadyInit` (entering sumu wrestling)
- `daAlink_c::checkGroundSpecialMode` --> `daAlink_c::procCanoeJumpRideInit` (entering the canoe after the little auto hop, only accessible using cheats)
- `daAlink_c::checkGroundSpecialMode` --> `daAlink_c::procBoardWaitInit` (idling while on the ice board)
- `daAlink_c::procFishingFoodInit` (putting worms/bee larva onto the rod, can't pull a rod and use a bottle at the same time atm)
- `daAlink_c::procBossBodyHangInit` (grabbing onto Morpheel/Agorok)
- `daAlink_c::procRoofHangStartInit` (hanging from a roof, which in this case means e.g. the vines in Lakebed on the ceiling where you can hang on)
- `daAlink_c::procSpinnerReadyInit` (riding the spinner, doesnt work as you cant equip the spinner while pulling rod)
- `daAlink_c::procHawkCatchInit` (if you could catch a hawk while pulling rod this would work)
 
### Status: Idk what these are
 
- `procCutFinishJumpUpInit` (seems related to backslice after a sideroll)
- `checkCaughtEscapeCutTurn` (no clue)
- `checkBoomerangCarry` (related to boomerang carrying items)
- `daAlink_c::procCopyRodReviveInit` (something with the rod, maybe the short ingame cutscene where it gets re-activated) 
- `daAlink_c::procPickPut` (no clue)
- `daAlink_c::setKandelaarMtx` (something with the lantern)
 
### Status: Too early in Link's event loop
 
- Pulling sword
- Grabbing a free standing item/object (like a cucco)
- `daAlink_c::setHeavyBoots` (force unequipping Iron Boots)
- `daAlink_c::checkDemoAction` (any cutscene that starts, e.g. opening doors, chests and so on)
- `daAlink_c::checkAutoJumpAction` (magnet stream with iron boots, diving into water, entering water, jumping, roll-jumping, falling)
- `daAlink_c::checkSwimAction` (swimming in water)
- `daAlink_c::checkBoomerangCatchAction` (catching stuff in the rang, as well as the rang itself)