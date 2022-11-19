# Voting

## The `vote.enabled` configuration variable

**Requirement.** When a round ends, a vote is triggered if and only if the map pool has at least 3 maps.

**Requirement.** If the map pool has 3 maps or less, it is not possible to buy a `VoteQueue`.

## Map selection

**Requirement.** If the map pool has only one map, then no vote is triggered. The next map to be played is just the only map in the pool.

**Requirement.** If the map pool has at least 2 maps, here is how the maps are selected for voting:

+ If the map pool has 4 maps or more *and* if some player bought a `VoteQueue`, 2 maps are random sampled from the maps pool (but the queued map). The vote-queued map and the two sampled maps are voted.
+ If the map pool has 3 maps or more, then 3 maps are randomly selected in the pool for voting.
+ If the map pool has only 2 maps, those two maps are selected for voting.
