# CmdFPS

**Requirement.** *If* Guest+ runs `/help fps` *or* `/fps`, *then* the following message should be printed to the user:

```
&T/fps start [map] &H- Starts First-person shooter
&T/fps stop &H- Stops First-person shooter
&T/fps end &H- Ends current round of First-person shooter
&T/fps add [map] &H- Adds map to the map pool
&T/fps remove [map] &H- Removes map from the map pool
```

**Requirement.** *When* loading the plugin for the first time, the permission for `/fps` should be `LevelPermission.Operator`.

**Requirement.** *If* an Operator+ runs `/fps start`, *then*:
+ *if* there is already a game running, *then* prints `&WFPS is already running.` to the user.
+ *else if* the map pool is empty, *then* prints `&WCould not start FPS: the map pool is empty.` *and* `&WAdd some maps with &T/fps add [map] &Wfirst.` to the user.
+ *else* starts a first-person shooter game on a random map in the map pool.

**Requirement.** *If* an Operator+ run `/fps start <map>`, *then*:
+ *if* there is already a game running, *then* prints `&WFPS is already running.` to the user.
+ *else if* there is no map called `<map>` in the map pool, *then* prints `&WCould not start FPS: there is no map &T<map> &W in the map pool.`.
+ *else* starts a first-person shooter game on the given map.

**Requirement.** *If* an Operator+ runs `/fps stop`, *then*:
+ *if* there is no FPS game running, prints `&WThere is no FPS game running.` to the user.
+ *else* stops the FPS game.

**Requirement.** *If* an Operator+ runs `/fps end`, *then*:
+ *if* there is no FPS game running, prints `&WThere is no FPS game running.` to the user.
+ *else if* there is an FPS game running *and* the current stage is `Voting`, *then* prints `&WCould not end round.` *and* `&WCurrent round is at the voting stage.`
+ *else* the round should be ended.

**Requirement.** *If* an Operator+ runs `/fps add`, *then*:
+ *if* user is a console, *then* `&WPlease provide a map to add to the pool.` should be printed to the user.
+ *else if* the contextual map is `Server.Config.MainLevel`, *then* `&WCannot add MainLevel to the map pool.` should be printed to the user.
+ *else if* the contextual map has a replay loaded, *then* `&WCannot add &T[map] &Wto map pool because it's hosting a replay.` should be printed to the user.
+ *else if* the contextual map is already in the map pool, *then* `&T[map] &Wis already in the map pool.` should be printed to the user.
+ *else* the contextual map should be added to the map pool.

**Requirement.** *If* an Operator+ runs `/fps add <map>`, *then*:
+ *if* `<map>` is `Server.Config.MainLevel`, *then* `&WCannot add MainLevel to the map pool.` should be printed to the user.
+ *else if* `<map>` is already in the map pool, *then* `&T<map> &Wis already in the map pool.` should be printed to the user.
+ *else* `<map>` should be added to the map pool.

**Requirement.** *If* an Operator+ runs `/fps remove`, *then*:
+ *if* user is a console, *then* `&WPlease provide a map to remove from the pool.` should be printed to the user.
+ *else if* `[map]` is not in the map pool, *then* `&T[map] &Wis not in the map pool.` should be printed to the user.
+ *else if* there is a game running on `[map]`, *then* `&WCould not remove &T[map] &Wfrom pool: it's being played.` should be printed to the user.
+ *else if* `[map]` appears in an ongoing vote, *then* `&WCould not remove &T[map] &Wfrom pool.` *and* `&WIt's currently being voted.` should be printed to the user.
+ *else* `[map]` should be removed from the map pool.

**Requirement.** *If* an Operator+ runs `/fps remove <map>`, *then*:
+ *if* `<map>` is not in the map pool, *then* `&T<map> &Wis not in the map pool.` should be printed to the user.
+ *else if* there is a game running on `<map>`, *then* `&WCould not remove &T<map> &Wfrom pool: it's being played.` should be printed to the user.
+ *else if* `<map>` appears in an ongoing vote, *then* `&WCould not remove &T<map> &Wfrom pool.` *and* `&WIt's currently being voted.` should be printed to the user.
+ *else* `<map>` should be removed from the map pool.
