# CmdStore

+ **When** a user runs `/help store`, **then** the following message should be printed to the user, **where** `[items]` is a comma-separated list of purchasable items.

```
&T/store <item>
&HViews specific information about the specific item, such as its cost.
&T/store
&HViews information about all enabled items.
Available items: &T[items]&H.
```

+ **When** loading the plugin for the first time, the permission for `/store` should be `LevelPermission.Guest`.

+ **If** a user runs `/store`, **then** each available item should be printed on its own line to the user (formatted according to the requirement below) **and** `&SUse &T/store [item] &Sto see more information about that item.` should be printed to the user.

+ **When** printing an item using `/store`, **where** `[item]` is the name of the item, `[price]` is its price, `[level]` its required level and `[currency]` is the server's currency:
    + **if** the user has the required level, **then** `&T[item] &S- &a[price] [currency]` should be printed to the user.
    + **else** (the user does not have the required level, **then** `&T[item] &S- &a[price] [currency] &S- &cLevel [level] required`

+ **When** running `/store <item>`:
    + **if** `<item>` is not a valid item name, **then** `&WThere is no item &T<item> &Win the store.` should be printed to the user.
    + **else if** user does not have the required level for that item **then** the help message for that item **and** `&TPrice: &a[price] [currency]` **and** `&cLevel [level] required` should be printed to the user **where** `[price]`, `[currency]` and `[level]` are respectively the price of that item, the server's currency and the minimum required level.
    + **else then** the help message for that item **and** `&TPrice: &a[price] [currency]` should be printed to the user **where** `[price]` and `[currency]` are respectively the price of that item and the server's currency.
