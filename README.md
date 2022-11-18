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

+ [AFK](AFK.md) - How to deal with AFK players
+ [Commands](Commands.md) - List of all commands registered by the plugin
+ [Database](Database.md) - Database schema
+ [Economy](Economy.md) - Name of currency, items that can be bought, etc.
+ [GUI](GUI.md) - What should be shown to the player and when
+ [Game modes](Game modes.md) - Specification for team vs. team and all vs. all
+ [Inventory](Inventory.md) - Items carried by a player, *i.e.* bullets, arrows, tnt...
+ [Items](Items.md) - Items that can be collected on the map
+ [Lag compensation](Lag compensation.md) - What lag compensation does and how it works
+ [Maps](Maps.md) - How to design a map for an FPSMO game, spawning system, metadata, etc.
+ [Moderation](Moderation.md) - How moderation works, notably `/CmdReferee`
+ [Overall description](Overall description.md)
+ [Plugin](Plugin.md) - Plugin related specification, *i.e.* what happens when it's loaded/unloaded
+ [Recording games](Recording games.md) - How recording game works
+ [Texture pack](Texture pack.md) - How a texture pack should be designed for an FPSMO game
+ [Voting](Voting.md) - How voting for the next map works
+ [Weapons](Weapons.md) - List of weapons and their characteristics
+ [XP](XP.md) - Leveling system

## Useful links

+ [UnknownShadow200/MCGalaxy](https://github.com/UnknownShadow200/MCGalaxy)
+ [opapinguin/FPS-Plugin](https://github.com/opapinguin/FPS-Plugin)
+ [NotAwesome2/MCGalaxy-CustomModels](https://github.com/NotAwesome2/MCGalaxy-CustomModels)
+ [Classic Protocol Extension](https://c4k3.github.io/wiki.vg/Classic_Protocol_Extension.html)
