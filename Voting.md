# Voting

+ **When** a round ends, **if** the map pool has at least 2 maps, **then** a vote is triggered.

+ **When** a round ends, **if** the map pool has only 1 map, **then** no vote is triggered and the next map is the only one in the pool.

+ **When** a vote is triggered, **then**:
    + **if** the map pool has 4 maps or more **and** some player bought a `VoteQueue`, **then** the maps selected for voting are the queued map and 2 distincts maps randomly sampled from the maps pool but the queued map.
    + **else if** the map pool has 3 maps or more, **then** the maps selected for voting are 3 distincts maps randomly sampled from the maps pool.
    + **else** (the map pool has exactly 2 maps), **then** those two maps are voted.

+ **If** a player sends a non-zero positive number to global chat **and** the game stage is voting **then**:
    + **if** the number is greater than the number of maps being voted, **then** it should be considered as a normal global chat message.
    + **else if** this player had already voted for a different map, **then** the votes count for the other map should be decreased by 1 **and** the votes count should be increased by 1 **and** `&SYou have changed your vote to &T[num]: [mapname]&S.` should be printed to the user.
    + **else if** this player had already voted for this map, **then** the votes for this map should be decreased by 1 **and** `&SYou have cancelled your vote for &T[num]: [mapname]&S.` should be printed to the user.
    + **else then** the votes count for the map should increase by 1 **and** `&SYour vote: &T[num]: [mapname]&S.` should be printed to the user.
