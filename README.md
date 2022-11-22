# `FPSMOPlugin` specification

This repository contains the specification for the *First Person Shooter Multiplayer Online* plugin designed for [MCGalaxy](https://github.com/UnknownShadow200/MCGalaxy). The source code for the plugin is also on Github: <https://github.com/opapinguin/FPS-Plugin>.

## Introduction

### Purpose

The FPSMO (First-Person Shooter Multiplayer Online) gamemode will be a completely new first-person shooter gamemode brought to the game ClassiCube, implemented made as a MCGalaxy plugin. Though open source, its software will be developed and catered specifically to the World of ClassiCube server network.

### Scope

The FPSMO gamemode allows players to buy and shoot weapons, and gain money and XP in return. Money can be used to buy more weapons in return, and is automatically replenished over time.

Its main inspiration will be the TNT Wars gamemode found in the MCGalaxy server software.

The application includes features for:

+ Recording and replaying matches e.g., for hack detection
+ Both *team vs. team* and *all vs. all* game modes
+ Leaderboards
+ Various player states, such as crawling and running
+ Lag compensation

## Index

Read this first: [Overall description](Overall%20description.md) and [Plugin](Plugin.md).

+ [AFK](AFK.md) - How to deal with AFK players
+ [All versus all](All%20versus%20all.md) - Specification for team vs. team
+ [Configuration](Configuration.md)
+ [Economy](Economy.md) - Name of currency, items that can be bought, etc.
+ [Team versus team](Team%20versus%20team.md) - Specification for team vs. team
+ [Inventory](Inventory.md) - Items carried by a player, *i.e.* bullets, arrows, tnt...
+ [Lag compensation](Lag%20compensation.md) - What lag compensation does and how it works
+ [Maps](Maps.md) - How to design a map for an FPSMO game, spawning system, metadata, etc.
+ [Recording games](Recording%20games.md) - How recording game works
+ [Voting](Voting.md) - How voting for the next map works
+ [Weapons](Weapons.md) - List of weapons and their characteristics
+ [XP](XP.md) - Leveling system

# Commands registered by *FPSMOPlugin*

+ [CmdFPS](Commands/CmdFPS.md)
+ [CmdPlay](Commands/CmdPlay.md)
+ [CmdReplay](Commands/CmdReplay.md)
+ [CmdStore](Commands/CmdStore.md)
+ [CmdXP](Commands/CmdXP.md)

## Useful links

+ [UnknownShadow200/MCGalaxy](https://github.com/UnknownShadow200/MCGalaxy)
+ [opapinguin/FPS-Plugin](https://github.com/opapinguin/FPS-Plugin)
+ [NotAwesome2/MCGalaxy-CustomModels](https://github.com/NotAwesome2/MCGalaxy-CustomModels)
+ [Classic Protocol Extension](https://c4k3.github.io/wiki.vg/Classic_Protocol_Extension.html)
