# Team versus team game mode

In all following requirements, it is assumed that a game is running **and** its game mode is team versus team.

**Definition.** *Unbalanced.* Teams are said to be **unbalanced** if their count differ by two or more. They are *balanced* otherwise.

**Definition.** *Unequal.* Teams are said to be **unequal** if they do not have the same count.

**Requirement.** **If** a player joins the game for the first time in the round **and** the round is **not** at voting stage **then**:
+ **if** teams are unequal **then** the player is assigned to the least populated team.
+ **else if** teams have different scores **then** the player is assigned to the team with the lowest score
+ **else then** the player is assigned a random team.

**Requirement.** **If** a player rejoins a round **and** the round is **not** at voting stage **then**:
+ **if** doing so wouldn't unbalance the game, **then** the player is assigned to their previous team. 
+ **else then** they are assigned to the least populated team.

**Requirement.** **When** the round enters *countdown* stage, all in-game players are assigned to a random team such that teams are balanced.

**Requirement.** **When** the round enters *countdown* stage, each team's score is 0.

**Requirement.** **When** a player kills another player in their own team, their team score decreases by one.

**Requirement.** **When** a player commits suicide, their team score decreases by one.

**Requirement.** **When** a player kills another player in their opponent team, their team score increases by one.

**Requirement.** **When** the round ends, the team with highest score wins.

**Requirement.** **If** a player chats **and** is in a team, **then** their nick should be colored according to their team.

**Requirement.** **When** the round enters *voting* stage, players are not considered to be part of a team anymore.
