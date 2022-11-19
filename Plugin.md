# Plugin

**Requirement.** When `/pload`ing the plugin, the game starts if and only if the `autostart` configuration variable is set to `true`.

**Requirement.** When `/pload`ing the plugin for the first time (meaning that the configuration file does not exist), all side effects must be displayed to the user (database and file system operations). The user is prompted to either confirm or cancel loading the plugin.

**Requirement.** Upon confirmation, database and file system operations are to be run. The configuration file must be generated with its default values.

**Requirement.** When `/punload`ing the plugin, the game must be stopped when there's one running.

**Requirement.** When `/pload`ing the plugin, no default MCGalaxy command should be unregistered.
