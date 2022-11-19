# Voting

## The `vote.enabled` configuration variable

**Requirement.** When a round ends, a vote is triggered if and only if the `vote.enabled` configuration variable is set to `true` *and* the map pool has at least 3 maps.

**Requirement.** If economy is enabled *and* if `vote.enabled` is set to `false`, it is not possible to buy a *VoteQueue*. 

**Requirement.** If ecnonmy is enabled *and* if `vote.enabled` is set to `true` *and* if the map pool has exactly 1, 2, 3 or 4 maps, then it is not possible to buy a *VoteQueue*.

## Changing the configuration variable

**Requirement.** If the `vote.enabled` configuration variable is set to `false` when a game is currently in the voting stage, the vote is *not* cancelled and the voting system will only be disabled for next round.

**Requirement.** If the `vote.enabled` configuration variable is set to `false` when a round hasn't reached the voting stage, *and* if a player had bought a VoteQueue, then the voting stage is cancelled anyway, and the player is refunded.

## Map selection

**Requirement.** If `vote.enabled` is set to false, here is how the next map is chosen:

+ If some player bought a *Queue*, then the queued map is selected
+ Else if there is only one map in the pool, this only map is selected
+ Otherwise, the next map is picked randomly among all maps from the pool but the one currently being played

**Requirement.** If `vote.enabled` is set to true *and* the map pool has at least 3 maps, here is how the maps are selected for voting:

+ If the map pool has *exactly* 3 maps, then those three maps are selected for voting.
+ If the map pool has 5 maps or more *and* if some player bought a *VoteQueue*, 2 maps are randomly sampled from the map pool but the map currently being played and the vote-queued map.
+ Otherwise, 3 maps are randomly sampled from the map pool but the map currently being played.

**Requirement.** If `vote.enabled` is set to true *and* the map pool has 1 or 2 maps, then everything must happen as if `vote.enabled` was set to false.
