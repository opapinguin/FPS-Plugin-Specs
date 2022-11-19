# Experience

## Maths

**Requirement.** When a player joins the game for the first time, they have 0 experience points and their level is 0 (*not* 1).

**Requirement.** Reaching level `n` from level `n-1` requires `Floor(10 * (n ^ 1.2))` experience points. That would give:

```nofmt
0 → 1 requires 10 XP
1 → 2 requires 22 XP
2 → 3 requires 37 XP
...
99 → 100 requires 2511 XP
```

**Requirement.** Killing a player gives 1 XP, except if it's yourself (in all vs. all) or if it's someone of your team (in team vs. team).

**Requirement.** It is not possible to lose XP.

**Requirement.** Not dying during a complete round gives 2XP. Exception: it doesn't apply when there are no opponents during some part of the round.

**Requirement.** Completing an achievement gives 8XP.

## Relation with economy

**Requirement.** Some items in the store can only be purchased if one has a high enough level. See [Economy](Economy.md).

**Requirement.** The previous requirement doesn't apply if the XP system is disabled. See next section.

## Enabling/disabling

> The following requirement is meant for servers who already have their own XP system, or who just want to implement FPSMO as a “Mini-game”.

**Requirement.** Operators must have the ability to disable the FPSMO XP system by running `/FPSMO Config XP Disable`. XP gaining, level up messages, and `<LVL>` prefix in public chat would then be disabled immediately.

**Requirement.** Operators must have the ability to enable the FPSMO XP system by running `/FPSMO Config XP Enable`. XP gaining, level up messages, and `<LVL>` prefix in public chat would then be enabled immediately.

## GUI

**Requirement.** In-game players chatting should be prefixed by `<LVL>`.

**Requirement.** Non in-game players chatting should *not* be prefixed by `<LVL>`. This applies to referees too.
