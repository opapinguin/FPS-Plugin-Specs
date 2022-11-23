# All versus all

In all following requirements, it is assumed that a game is running **and** its game mode is all versus all.

+ **When** the rounds enter countdown mode, all scores should be 0.

+ **When** a player kills themselves, their score should decrease by 1.

+ **When** a player kills another player, their score should increase by 1.

+ **When** a player rejoins the round, their score should be 0.

+ **When** the rounds enter voting stage, the winning player is the one with the greatest score (even if the player left the game).
