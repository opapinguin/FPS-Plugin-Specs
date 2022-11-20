# AFK

**Requirement.** **If** a player is in-game **and** do not interact with the game for `FPS.Config.AFK-Notice` (in seconds), **then** `&WYou're about to enter AFK-mode. Please interact with the game to keep playing.` should be printed to the player.

**Requirement.** **If** a player is in-game **and** do not interact with the game for `FPS.Config.AFK-Mode` (in seconds), **then** they should enter AFK-mode **and** `&S[player] &Sis AFK-auto: not moved for [FPS.Config.AFK-Mode]` should be sent to global chat.

**Requirement.** **If** a player runs `/afk`, **then** they enter AFK-mode **and** `&S[player] &Sis AFK` should be sent to global chat.

**Requirement.** **If** a player runs `/afk <reason>`, **then** they enter AFK-mode **and** `&S[player &Sis AFK: <reason>` should be sent to global chat.

**Requirement.** **If** a player enters AFK-mode, **then** they should be moved to `Server.Config.MainLevel`. 

**Requirement.** **If** a player is in AFK-mode **and** interact with the game, **then** they exit AFK-mode.

**Requirement.** **If** a player exists AFK-mode, **then** `&S[player] &Sis not longer AFK` should be sent to global chat **and** `&SRun &T/play &Sto join FPS!`.
