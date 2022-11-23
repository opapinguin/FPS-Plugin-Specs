# CmdBuy

+ **It is assumed that** the `/buy` command has permission `LevelPermission.Guest`.

+ **When** a player runs `/buy <item> [args]`:
    + **if** the player does not have enough XP do buy `item` **then** `&WRequired level for &T<item>&W: &T[level]&W.` should be printed to the player, **where** `[level]` is the required level.
    + **else if** the player does not have enough money do buy `item` **then** `&WCould not purchase <item>: you do not have enough &T[currency]&W.` where `[currency]` is the server currency.
    + **else then** an attempt to buy `<item>` is triggered.

+ **When** a player succeed to buy an `<item>`, `<amount>` money is taken from the player, **where** `<amount>` is the price of `<item>`.

+ **When** a player attempts to buy a lottery ticket:
    + **if** no game is running, **then** `&WCannot buy a lottery ticket when no game is running.` should be printed to the player.
    + **else if** the player is hidden, **then** `&WCannot buy a lottery ticket when hidden.` should be printed to the player.
    + **else then** the player enters the lottery [remark: it is not required for the player to be in-game].

+ **When** disconnecting, **if** a player is in the lottery, **then** the player is considered as leaving the lottery **and** is **not** refunded **and** the bet remains unchanged [remark: reconnecting before the end of the round doesn't count as rejoining the lottery, though it's possible to buy another ticket].

+ **When** the round enters voting stage, **if** a lottery was triggered **and** the lottery pool isn't empty, **then** a random player picked in the lottery gets the bet.

+ **When** the round enters coting stage, **if** a lottery was triggered **and** the lottery pool is empty, **then** the bet is destroyed.

+ **When** a player attempts to buy a nick:
    + **if** the nick contains color codes, **then** `&WYou cannot use color codes in nicks.` should be printed to the user **and** the purchase should fail.
    + **else if** the nick name is already used by another player as a true name **or** as a nick, **then** `&WThere is already a player named [nick].` **and** the purchase should fail.
    + **else then** player's nick should be changed **and** the purchase should succeed.

+ **When** a player attempts to buy a map queue:
    + **if** there is already a map queued for next round, **then** `&WThere is already a map queued for next round.` should be printed to the player **and** the purchase should fail.
    + **else if** there is already a map vote-queued, **then** `&WCannot buy a map queue: a map has been vote-queued already.` should be printed to the player **and** the purchase should fail.
    + **else if** the given map is not in the map pool, **then** `&WCould not find map &T[map] &Win the map pool.` should be printed to the player **and** the purchase should fail.
    + **else if** the map to be queued is in the history, **then** `&WCould not queue map: it has been played too recently.` should be printed to the user **and** the purchase should fail.
    + **else then** the map should be queued **and** the purchase should succeed.

+ **When** a player attempts to buy a map vote-queue:
    + **if** there is already a map queued for next round, **then** `&WThere is already a map queued for next round.` should be printed to the player **and** the purchase should fail.
    + **else if** there is already a map vote-queued, **then** `&WCannot buy a map vote-queue: a map has been vote-queued already.` should be printed to the player **and** the purchase should fail.
    + **else if** the given map is not in the map pool, **then** `&WCould not find map &T[map] &Win the map pool.` should be printed to the player **and** the purchase should fail.
    + **else if** the map to be vote-queued is in the history, **then** `&WCould not vote-queue map: it has been played too recently.` should be printed to the user **and** the purchase should fail.
    + **else then** the map should be vote-queued **and** the purchase should succeed.

+ **When** the game stops, **if** some player had bought a queue or vote-queue, **then** they should be refunded.

+ **When** a map is removed from the pool, **if** the game is running **and if** the corresponding map had been queued **or** vote-queued, **then** the corresponding player should be refunded.
