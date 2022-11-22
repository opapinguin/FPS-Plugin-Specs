# CmdReplay

+ **If** a user runs `/help replay` **or** `/replay`, **then** the following message should be printed to the user:

```
&T/replay list &H- Lists all replays
&T/replay latest &H- Lists the ten most recent replays
&T/replay load <replay_id> &H- Loads <replay_id>
&T/replay unload &H- Unloads currently loaded replay
&T/replay start &H- Starts the currently loaded replay
&T/replay stop &H- Stops the currently loaded replay
&T/replay set <time> &H- Jump to <time> in the replay
```

+ **If** a user runs `/replay list`, **then** the list of all replays should be printed to the user. **When** a replay is printed, it should take the following form:

```nofmt
&Tdd/MM/yyyy HH:mm <map> id:<id> duration:<duration>
```

For example:

```nofmt
20/11/2022 19:00 foobarmap id:28 duration:7min57s
```

+ **If** a user runs `/replay latest`, **then** the list of the ten latest replays should be printed to the user.

+ **If** a user runs `/replay load <replay_id>`, **then**:
    + **if** there is no replay with identifier `<replay_id>`, **then** `&WCould not load replay <replay_id>: there is no replay with such id.` should be printed to the user.
    + **else if** the replay's map does not exists, **then** `&WCould not load replay <replay_id>: its map [map] is missing.` should be printed to the user.
    + **else if** the replay's map is currently on the map pool, **then** `&WCannot load a replay if its map is on the map pool.` **and** `&WPlease remove the map from the map pool first.` should be printed to the user.
    + **else if** there is already a replay running on that map, **then** `&WCould not load replay <replay_id>: there's already a replay loaded there.` **and** `&WPlease &T/goto [map] &Wand &T/replay unload &Wfirst.` should be printed to the user.
    + **else if** the user does not have the pervisit for the replay's map, **then** `&WCould not load replay: you do not have the required pervisit for &T[map]&W.` should be printed to the user.
    + **else** the replay is loaded.

+ **When** a user loads a replay, they should be moved to the replay's map **and** the replay should be set to its first frame **and** the replay should be paused.

+ **If** a user runs `/replay unload`, **then**:
    + **if** there is no replay loaded on the current map, **then** `&WThere is no replay to unload.` should be printed to the user.
    + **else** the replay should be unloaded **and** `&SUnloaded replay.` should be printed to map chat.

+ **When** an user unloads a replay, the corresponding map should be set to its original state **and** replay-specific bots (if any) should be removed.

+ **If** an user runs `/replay start`, **then**:
    + **if** there is no replay loaded on the player's current map, **then** `&WThere's no replay loaded on &T[map].` should be printed to the user.
    + **else if** the replay is on its last frame **and** paused, **then** the replay should be set to its first frame and start.
    + **else if** the replay is **not** on its last frame **and** paused, **then** it should resume **and** `&SResumed replay.` should be printed to map chat.
    + **else** (the replay is already running), **then** `&WReplay is already running.` should be printed to the user.

+ **If** an user runs `/replay stop`, **then**:
    + **if** there is no replay loaded on the player's current map, **then** `&WThere's no replay loaded on &T[map].` should be printed to the user.
    + **else if** the replay is **not** running, **then** `&WReplay is already stopped.` should be printed to the user.
    + **else** (the replay is running), **then** the replay should be stopped.

+ **If** an user runs `/replay set <time>`, **then**:
    + **if** there is no replay loaded on the player's current map, **then** `&WThere's no replay loaded on &T[map].` should be printed to the user.
    + **else if** `<time>` is an invalid time format, **then** `&WValid time formats: &THH:mm:ss&W, &TH:mm:ss&W, &Tmm:ss &Wor &Tm:ss&W.` **and** `&WExample: &T4:05 &Wfor four minutes and five seconds.` should be printed to the user.
    + **else if** `<time>` is larger than the replay's duration, **then** the replay should be paused **and** set to its last frame **and** `&SReplay was set to frame &T[frame]&S.` should be printed to the map chat **where** `[frame]` is the corresponding frame.
    + **else** the replay should be paused **and** set to the corresponding frame **and** `&SReplay was set to frame &T[frame]&S.` should be printed to the map chat.

+ **If** an user leaves a map **and** there is a replay loaded on this map **and** no one is left on this map **then** the replay should be unloaded **and** `&SUnloaded replay.` should be printed to the user.
