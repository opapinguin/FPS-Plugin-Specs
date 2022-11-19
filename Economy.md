# Economy

## Store

**Requirement.** The following items can be bought in the economy.

| **Item**       | **Price** | **Description**                       | **Required level** |
|----------------|-----------|---------------------------------------|--------------------|
| LotteryTicket  | 10$       | Get the bet at the end of the round   | 1                  |
| Nick           | 600$      | Custom nickname                       | 30                 |
| Queue          | 80$       | Queue a map                           | 25                 |
| VoteQueue      | 60$       | Given map will be voted en round ends | 25                 |
| Title          | 250$      | Title in square brackets prefix       | 15                 |
| LoginMessage   | 180$      | Message displaying when logging in    | 20                 |
| LogoutMessage  | 180$      | Message displaying when logging out   | 20                 |
| KickAll        | 2500$     | Kick everyone with 1% chance          | 35                 |

**Requirement.** Buying a lottery ticket and leaving the game before the end of the round does not refund.

**Requirement.** Buying a lottery ticket, leaving the game and joining back before the end of the round keeps the ticket active (you may still gain the bet).

**Requirement.** It is not possible to add colors to nick names [the reason being that your name's color depends on your team, it's either all-red or all-blue].

**Requirement.** It is not possible to buy a nickname if this nickname is the true name of another player.

**Requirement.** It is not possible to Queue a map if it's the one actually being played.

**Requirement.** It *is* possible to VoteQueue a map even if it's the one actually being played.

**Requirement.** If a player buys a VoteQueue/Queue and if the game is stopped, the player is refunded.

**Requirement.** It is not possible to VoteQueue/Queue if the corresponding map is not in the map pool.

**Requirement.** If a player buy a VoteQueue/Queue and if the corresponding map is removed from the map pool, the queue is cancelled and the player is refunded. A message informing this is sent to in-game players and referees.

## Enabling/disabling

**Requirement.** If the XP system is *enabled*, each Item requires a minimum-level for the transaction to happen. If a player does not have enough XP, a message should be displayed informing them they cannot buy the item when they try to do so.

**Requirement.** If the XP system is *disabled*, any player with enough money can buy any item. All other requirement of this document assumes that economy is enabled.

## Commands

**Requirement.** `/store` lists all information displayed in the table of this document.

**Requirement.** `/buy <item> [args]` is used to buy items. It fails if either:

+ The player does not have enough XP (assuming XP is enabled)
+ *or* they do not have enough money
+ *or* if some preconditions regarding the items and the arguments aren't met (buying a non-existent map for queue, for example)

When failing, no money is taken from the player running the command.

**Requirement.** `/balance <player>` (or its shortcut `/money <player>`) shows how much moneys the given player has.

**Requirement.** `/store <item>` show information about that item.
