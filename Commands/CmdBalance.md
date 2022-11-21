# CmdBalance

**Requirement.** **If** an user runs `/help balance` **or** `/help money`, **then** the following message should be printed to the user, **where** `[currency]` is the currency of the server:

```
&T/balance &H- Shows how much money you have.
&T/balance <player> &H- Shows how much money <player> has.
&T/balance <player> <amount> &H- Sets money for <player>
```

**Requirement.** **When** loading the plugin for the first time, the level permission for `/balance` should be `LevelPermission.Guest` **and** the level permission for setting balance of others should be `LevelPermission.Operator`.

**Requirement.** **If** an user runs `/balance`, **then** `/balance [player]` should be ran instead **where** `[player]` is the user's name.

**Requirement.** **If** an user runs `/balance <player>`, **then**:
+ **if** there is no player `<player>`, **then** `&WThere is no player <player>&W.` should be printed to the user.
+ **else** the following message should be printed to the user, **where** `[spent]`, `[amount]` and `[currency]` are respectively the money spent, the balance of `<player>`, and the currency of the server.

```nofmt
&SEconomy stats for <player>&S:
Current balance: &T[amount] [currency]&S.
Total spent: &T[spent] [currency]&S.
```

**Requirement.** **If** an user runs `/balance <player> <amount>`, **then**:
+ **if** there is no player `<player>`, **then** `&WThere is no player <player>&W.` should be printed to the user.
+ **else if** `<amount>` cannot be parsed into a positive integer, **then** `&T<amount> &Wis not a valid positive integer.` should be printed to the user.
+ **else** `<player>`'s balance should be set to `<amount>` **and** `&T<player>'s &Sbalance has been set to &T<amount>&S.` should be printed to the user.
