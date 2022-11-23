# Experience

+ **When** a player joins the game for the first time, their experience is 0 and their level is 0.

+ Reaching level $n$ from level $n-1$ requires $\lfloor 10\times n^{1.2}\rfloor$ experience points. That would give:

```nofmt
0 → 1 requires 10 XP
1 → 2 requires 22 XP
2 → 3 requires 37 XP
...
99 → 100 requires 2511 XP
```

## Gaining experience

+ Killing a player gives 1 XP, **except if** the victim is yourself **or** if it's someone of your team [latter case is only applicable in team vs. team].

+ **If** a player survived a whole round without disconnecting **and** there was opponents during the whole round **then** the player gains 2XP + 1XP per opponents still connected.

+ **When** a player completes an achievement, they gain 8XP.

## GUI

+ **When** chatting to global chat, players should be prefixed by their level under angle brackets.

+ **When** unlocking a level, `[player] has reached level [level]!`  should be printed to global chat.
