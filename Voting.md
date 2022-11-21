# Voting

**Requirement.** **When** a round ends, **if** the map pool has at least 2 maps, **then** a vote is triggered.

**Requirement.** **When** a round ends, **if** the map pool only has 1 map, **then** no vote is triggered and the next map is the only one in the pool.

**Requirement.** **When** a vote is triggered, **then**:

+ **if** the map pool has 4 maps or more **and** some player bought a `VoteQueue`, **then** the maps selected for voting are the queued map and 2 distincts maps randomly sampled from the maps pool but the queued map.
+ **else if** the map pool has 3 maps or more, **then** the maps selected for voting are 3 distincts maps randomly sampled from the maps pool.
+ **else** (the map pool has exactly 2 maps), **then** those two maps are voted.
