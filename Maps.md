# Maps

**Definition.** An *FPSMO map* is a map intended to be played in an FPSMO game.

## Designing maps for FPSMO

**Assumption.** Every *FPSMO map* uses a texture pack complying with the following constraints:

+ Terrain has 512 textures
+ Terrain must be consistent with ClassiCube default textures
+ It implements the following custom textures (384-388 are to be displayed in the inventory for weapon-selection)
    - 384: Bow (on transparent background)
    - 385: Rifle (on transparent background)
    - 386: Rocket (on transparent background)
    - 387: Bazooka (on transparent background)
    - 388: Lasergun (on transparent background)
    - 389: Health box top
    - 390: Health box side
    - 391: Health box bottom
    - 392: Ammunition box side
    - 393: Ammunition box bottom
    - 394: Ammunition box top arrows
    - 395: Ammunition box top rifle
    - 396: Ammunition box top rocket
    - 397: Ammunition box top bazooka
    - 398: Ammunition box top lasergun
    - 399-511 are reserved for potential future usage
+ The font file `default.png` must be consistent with the default ClassiCube font, except for the following symbols (they are often labeled “lines and boxes”):
    - 176: Half-heart
    - 177: Death-skull
    - 178: Bow
    - 179: Rifle
    - 180: Rocket
    - 181: Bazooka
    - 182: Lasergun
    - 183: Sword
    - 184: Full square
    - 185: Half square
    - 186-223 are reserved for potential future usage

**Assumption.** Every *FPSMO map* uses the following custom level blocks (raw blocks IDs are given here):

+ 256: Health box
+ 257: Ammunition box arrows
+ 258: Ammunition box rifle
+ 259: Ammunition box rocket
+ 260: Ammunition box bazooka
+ 261: Ammunition box lasergun

**Requirement.** Map designers (or moderators, on their demand) must be able to attach the following metadata to their maps:

+ `countdown: int` duration of the countdown, (it can be zero)
+ `duration: int` duration *in seconds* of the round (the countdown is excluded from this duration)
+ `authors: string` comma-separated list of the authors of the map

**Assumption.** Every *FPSMO map* has building/deleting blocks disabled.

**Assumption.** Every *FPSMO map* has `Guest` pervisit.

**Requirement.** When a player runs `/SetupFPS` on a map, an FPSMO-compatible texture pack substitute the current one and FPSMO level-blocks are added to the LBs. Preconditions:

+ The player has permission to change env settings on this map
+ The player has permission to edit level-blocks on this map
+ Running the level-blocks commands won't erase any already-existing level block

**Requirement.** Maps designer must be able to specify spawn-points in their maps. Each spawn point can be labeled “Red”, “Blue” or “Mix”.

+ If labeled “Red”, only players from the red team can spawn on this point
+ If labeled “Blue”, only players from the blue team can spawn on this point
+ If labeled “Mix”, any player can spawn on this point

## Map pool

**Requirement.** Running `/FPSMO MapPool Add <map_name>` adds a map to the map pool. *Preconditions:*

+ `<map_name>` must be an existing map
+ Moreover, it must not already be part of the map pool

Another remark, if `<map_name>` does not have meta data, default metadata is created and used.

**Requirement.** Running `/FPSMO MapPool Remove <map_name>` remove a map from the map pool. *Preconditions:*

+ `<map_name>` is in the map pool

If `<map_name>` is currently being played, the game does *not* end. The map just won't be showed in the votes anymore.

**Requirement.** If a map is deleted with `/deletelvl` *and* if this map is in the map pool, it should be removed from the map pool.

**Requirement.** Running `/FPSMO MapPool` displays the map pool.

**Requirement.** Running `/FPSMO MapPool Remove <map_name>` when the game is running on `<map_name>` *and* `<map_name>` is the *only* map in the pool will terminate the game when the round ends (unless a map is added in between).
