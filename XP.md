# Experience

## Maths

**Requirement.XP.1.** When a player joins the game for the first time, they have 0 experience points and their level is 0 (*not* 1).

**Requirement.XP.2.** Reaching level `n` from level `n-1` requires `Floor(10 * (n ^ 1.2))` experience points. That would give:

```nofmt
0 → 1 requires 10 XP
1 → 2 requires 22 XP
2 → 3 requires 37 XP
...
99 → 100 requires 2511 XP
```

**Requirement.XP.3.** Killing a player gives 1 XP, except if it's yourself (in all vs. all) or if it's someone of your team (in team vs. team).

**Requirement.XP.4.** It is not possible to lose XP.

**Requirement.XP.5.** Not dying during a complete round gives 2XP. Exception: it doesn't apply when there are no opponents during some part of the round.

**Requirement.XP.6.** Completing an achievement gives 8XP.

## Relation with economy

**Requirement.XP.7.** Some items in the store can only be purchased if one has a high enough level. See [Economy](Economy.md).

**Requirement.XP.8.** The **Requirement.XP.7** doesn't apply if the XP system is disabled. See next section.

## Enabling/disabling

> The following requirement is meant for servers who already have their own XP system, or who just want to implement FPSMO as a “Mini-game”.

**Requirement.XP.9.** Operators must have the ability to disable the FPSMO XP system by running `/fpsmo config xp disable`. XP gaining, level up messages, and `<lvl>` prefix in public chat would then be disabled immediately.

**Requirement.XP.10.** Operators must have the ability to enable the FPSMO XP system by running `/fpsmo config xp enable`. XP gaining, level up messages, and `<lvl>` prefix in public chat would then be enabled immediately.

## GUI

**Requirement.XP.11.** In-game players chatting should be prefixed by `<lvl>`.

**Requirement.XP.12.** Non in-game players chatting should *not* be prefixed by `<lvl>`. This applies to referees too.
