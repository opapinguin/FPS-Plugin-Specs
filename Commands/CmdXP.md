# CmdExperience

+ **If** an user runs `/help experience` **or** `/help xp`, **then** the following message should be printed to the user:

```
&T/experience &H- Shows how much XP you have.
&T/experience <player> &H- Shows how much XP <player> has.
&T/experience <player> <amount> &H- Sets XP for <player>
```

+ **When** loading the plugin for the first time, the level permission for `/experience` should be `LevelPermission.Guest` **and** the level permission for setting XP of others should be `LevelPermission.Operator`.

+ **If** an user runs `/experience`, **then** `/experience [player]` should be ran instead **where** `[player]` is the user's name.

+ **If** an user runs `/experience <player>`, **then**:
    + **if** there is no player `<player>`, **then** `&WThere is no player <player>&W.` should be printed to the user.
    + **else** the following message should be printed to the user, **where** `[level]`, `[xp]` and `[needed]` are respectively the player's level, its XP and how much XP is left before next level.

```nofmt
&S<player> &Thas &T[xp] XP&S (&Tlevel [level]&S).
&SNeeds &T[remaining] XP &Sto reach &TLevel [level+1]&S.
```

+ **If** an user runs `/experience <player> <amount>`, **then**:
    + **if** there is no player `<player>`, **then** `&WThere is no player <player>&W.` should be printed to the user.
    + **else if** `<amount>` cannot be parsed into a positive integer, **then** `&T<amount> &Wis not a valid positive integer.` should be printed to the user.
    + **else** `<player>`'s XP should be set to `<amount>` **and** `&T<player>'s &SXP has been set to &T<amount>&S.` should be printed to the user.
