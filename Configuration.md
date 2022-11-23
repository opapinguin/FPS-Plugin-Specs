# Configuration

+ **When** `/pload`ing the plugin for the first time, the following configuration file `fpsmo/game.properties` should be created:

```nofmt
# Edit the settings below to fit your needs
# Those settings will be updated when reloading the plugin/restarting the server.
b_auto_start = true
ms_round_tick = 50
s_votetime = 10
max_move_distance = 1.5625
b_set_main_level = true
default_roundtime_s = 60
gravity = 9.81

ms_update_round_status = 50
ms_update_weapon_animations = 50

# Guns

gun_block = 41
min_gun_velocity = 50
max_gun_velocity = 300
ms_gun_reload = 200
gun_damage = 1
gun_frame_length = 1

# Rockets

rocket_block = 42
min_rocket_velocity = 10
max_rocket_velocity = 60
ms_rocket_reload = 2000
rocket_damage = 1
rocket_frame_length = 4

s_afk_notice = 100
s_afk = 120

# How many previous played maps are saved. Used for voting.
history = 0

# Can be either team_vs_team or all_vs_all
gamemode = team_vs_team
```
