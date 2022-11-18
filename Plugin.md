# Plugin

**Requierement.** *Plugin.1.* When `/pload`ing the plugin, the game starts if and only if the `autostart` configuration variable is set to `true`.

**Requierement.** *Plugin.2.* When `/pload`ing the plugin for the first time (meaning that the configuration file does not exist), all side effects must be displayed to the user (database and file system operations). The user is prompted to either confirm or cancel loading the plugin.

**Requierement.** *Plugin.3.* When `/punload`ing the plugin, the game must be stopped when there's one running.
