# Maps

## Designing maps for FPSMO

+ It is assumed that every *FPSMO map* uses a texture pack complying with the following constraints:
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
    + The font file `default.png` must be consistent with the default ClassiCube font, except for the following symbols:
        - 159: Bold uppercase A
        - 171: Bold uppercase B
        - 172: Bold uppercase C
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
        - 186-211: Bold lowercase a-z
        - 212: Empty heart
        - 213: Bow outline
        - 214: Hand gun outline
        - 215: Rocket outline
        - 216: Bazooka outline
        - 217: Laser gun outline
        - 218: Sword outline
        - 224-246: Bold uppercase D-Z
        - 247: Bold bang
        - 248: Bold question mark

+ It is assumed that every *FPSMO map* uses the following custom level blocks (raw blocks IDs are given here):
    + 256: Health box
    + 257: Ammunition box arrows
    + 258: Ammunition box rifle
    + 259: Ammunition box rocket
    + 260: Ammunition box bazooka
    + 261: Ammunition box lasergun
    + 262: TNTs box

+ It is assumed that on an *FPSMO map*, every blocks should be hidden from the `B` block menu.

+ Map designers (or moderators, on their demand) must be able to attach the following metadata to their maps:
    + `countdown: int` duration of the countdown, (it can be zero)
    + `duration: int` duration *in seconds* of the round (the countdown is excluded from this duration)
    + `authors: string` comma-separated list of the authors of the map

+ It is assumed that every *FPSMO map* has building/deleting blocks disabled.

+ It is assumed that every *FPSMO map* has `Guest` pervisit.

+ Maps designer must be able to specify spawn-points in their maps. Each spawn point can be labeled “Red”, “Blue” or “Mix”.
    + If labeled “Red”, only players from the red team can spawn on this point
    + If labeled “Blue”, only players from the blue team can spawn on this point
    + If labeled “Mix”, any player can spawn on this point
