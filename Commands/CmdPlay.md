# CmdPlay

**Requirement.** *If* a Guest+ runs `/help play`, *then* the following message should be printed to the user:

```
&T/play &H- Joins the FPS game
```

**Requirement.** *If* a Guest+ runs `/play`, *then*:
+ *if* no game is running, *then* `&WNo game is running.` should be printed to the user.
+ *else if* they are in-game, *then* `&WYou are already playing.` should be printed to the user.
+ *else if* they are hidden, *then* `&WYou cannot play while hidden. Please unhide first.` should be printed to the user.
+ *else* the user should be teleported on the map being played and considered as in-game.
