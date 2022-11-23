# Navigation

This document deals with `/goto`, `/tp`, `/ref` and all problems related with moving players across maps.

+ **It is assumed that** the level permission for running `/goto` is set to `LevelPermission.Operator`.

+ **It is assumed that** the level permission for running `/tp` is set to `LevelPermission.Operator`.

+ **If** a player runs `/goto <destination>` **where** an FPS game is being played on `<destination>` **and if** the player is **not** a referee **then**:
    + **if** the player is hidden, then the player is marked as referee **and** is moved to `<destination>` **and** is **not** considered as joining the game.
    + **else then** the player joins the game.

+ **If** a player runs `/goto <destination>` **where** an FPS game is being played on `<destination>` **and if** the player **is** a referee **then** the player is moved to `<destination>` **and** is **not** considered as joining the game.

+ **If** a player runs `/ref` while being in-game, **then** they are considered as leaving the game.

+ **If** a player stands on a map in the map pool that is **not** being played **and if** this map is selected as the next map for FPS, **then**:
    + **if** the player is a referee, **then** they are **not** considered as joining the game.
    + **else if** the player is hidden, **then** the player is marked as referee **and** is **not** considered as joining the game.
    + **else then** the player joins the game.

+ **If** a player runs `/tp <someone>`, **then assuming** `<someone>` is an online player **and** is visible to the player:
    + **if** `<someone>` is **not** in-game, **then** the player should be moved to `<someone>`'s location.
    + **else if** `<someone>` **is** in-game:
        + **if** the player is **not** a referee, **then** `&WCannot teleport to an in-game player unless you're referee.` **and** `&WPlease run &T/referee &Wfirst.` should be printed to the player.
        + **else then** the player should be moved to `<someone>`'s location.
