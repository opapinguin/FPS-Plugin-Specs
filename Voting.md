# Voting

In all following requirements, `history` denotes the configuration variable (see [Configuration](Configuration.md)), `pool_size` is the number of maps in the map pool, and `maps_hat` is all maps in the map pool **but** the maps in the history.

+ **When** a round ends
    + **if** `history` is larger than or equal to `pool_size - 1`, **then** the map indexed `(i + 1) % pool_size` is selected as the next map, **where** `i` is the index of the current map in the map pool.
    + **else if** a map has been queued, **then** the corresponding map is selected as the next one.
    + **else if** `maps_hat` has only 2 maps, **then** those two maps are selected for voting.
    + **else then**:
        + **if** some map has been vote queued, **then** it appears in the vote and 2 other maps are chosen randomly from the hat.
        + **else then** 3 maps are chosen randomly in the hat.

+ **If** a player sends a non-zero positive number to global chat **and** the game stage is voting **then**:
    + **if** the number is greater than the number of maps being voted, **then** it should be considered as a normal global chat message.
    + **else if** this player had already voted for a different map, **then** the votes count for the other map should be decreased by 1 **and** the votes count should be increased by 1 **and** `&SYou have changed your vote to &T[num]: [mapname]&S.` should be printed to the user.
    + **else if** this player had already voted for this map, **then** the votes for this map should be decreased by 1 **and** `&SYou have cancelled your vote for &T[num]: [mapname]&S.` should be printed to the user.
    + **else then** the votes count for the map should increase by 1 **and** `&SYour vote: &T[num]: [mapname]&S.` should be printed to the user.
