# Plugin

+ When `/pload`ing the plugin, the game starts if and only if the `autostart` configuration variable is set to `true`.

+ When `/pload`ing the plugin for the first time (meaning that the configuration file does not exist), all side effects must be displayed to the user (database and file system operations). The user is prompted to either confirm or cancel loading the plugin.

+ Upon confirmation, database and file system operations are to be run. The configuration file must be generated with its default values.

+ When `/punload`ing the plugin, the game must be stopped when there's one running.

+ If the plugin is loaded *and* if no game is running *and* a player joins the server, they join on `Server.Config.MainLevel`.

+ *If* the plugin is loaded *and* a game is running *and* a player joins the server, they join on the map currently being played.

+ When `/pload`ing the plugin, *if* `Server.Config.MainLevel` is in the map pool, then it is removed and a message is displayed to the user indicating it.

+ *If* a player runs either `/Main`, `/Home`, `/Lobby` or `/AFK`, they are teleported to the main level `Server.Config.MainLevel`. In the latter case, they're also marked as AFK. They are considered, in all cases, as leaving the game.
