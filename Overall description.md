# Overall description

The main focus in this section is to explain the main factors in the development of the new gamemode.

## Product perspective

The FPSMO gamemode is targeted at ClassiCube players who want a new challenge.

### System interfaces

The FPSMO gamemode will execute on all platforms compatible with ClassiCube.

### User interfaces

The user interface of this gamemode is that of ClassiCube, changed to our needs by sending UI changes via the classic protocol extension using the MCGalaxy networking API.

### Hardware interfaces

N/A

### Software Interfaces

The required products are ClassiCube and the MCGalaxy server software for ClassiCube.

## Product functions

Client functions:

+ Choose a variety of weapons
+ Shoot these weapons
+ Being able to continuously monitor one’s own stamina, health points and reload time
+ Continuously monitor the performance of his/her team
+ Interact with his/her team via a per-round team chat
+ Ability to change state e.g., sprint, crawl
+ Buy goodies using money earned
+ Choose hotkey settings

Server requierements:

+ The end user must be able to configure whether to start the game on server startup
+ Continuously record rounds for later replay and hack detection
+ Continuously update statistics related to the leaderboards
+ Send hotkeys to connecting players
+ Save hotkey settings for players
+ Compensate for lag—if a player sees a hit in the client, that translates to a hit on the
server

## Assumptions and dependencies

We are assuming that clients connecting to the main server are able to use the up-to-date [classic protocol extension](https://c4k3.github.io/wiki.vg/Classic_Protocol_Extension.html). We also assume that some players will connect with hacked clients with malicious intents that can compromise the gameplay.
