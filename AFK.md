# AFK

**Requirement.** If a player is in-game and do not interact with the game for `config.afk-notice-time-in-seconds`, a message is sent to them informing them that they are about to enter AFK mode.

**Requirement.** If a player is in-game and do not interact with the game for `config.afk-time-in-seconds`, they enter AFK-mode.

**Requirement.** When entering AFK-mode, a player is moved to `config.afk-map`. Hence, they are considered as leaving the game. If such a map does not exist, *or* if such map is in the map pool, then the player is sent to `Server.Config.MainLevel`. If such a map is also in the map pool, then the player is kicked from the server.
