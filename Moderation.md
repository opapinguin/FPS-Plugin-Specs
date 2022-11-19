# Moderation

**Requirement.** The `/FPSMO` command requires the `LevelPermission.Operator` permission.

**Requirement.** Just running `/FPSMO` prints the help message for the game.

**Requirement.** `/FPSMO start` starts the game. It doesn't work if there is no FPSMO game running yet *or* if the map pool is empty.

**Requirement.** `/FPSMO start [map]` starts the game on the given map. If no map is given *and* if the user is not a console *and* if the user is standing on a map that is in the map pool, then the game starts on this map. Otherwise, the first map is selected randomly in the map pool.

**Requirement.** `/FPSMO stop` stops the game if there is one running.

**Requirement.** `/FPSMO config` prints all configuration variables (and their content) to the user.

**Requirement.** `/FPSMO config <variable>` prints the content of the given configuration variable, if such a variable exists.

**Requirement.** `/FPSMO config <variable> <content>` edits the content of the given configuration variable, upon validation.
