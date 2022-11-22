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

# Afk
s_afk-notice = 100
s_afk = 120

# Voting system
# ============= 

# If history is 0, it is possible to play the same map twice (or more).
# If history is 1, the same map cannot be played twice.
# If history is 2, the same map cannot be played twice for three consecutive rounds
# If history is one but the number of maps in the pool (or larger), each map is played deterministically in the order they were added
history = 0
```
