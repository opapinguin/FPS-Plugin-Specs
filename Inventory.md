# Inventory

**Definition.** An *inventory* is a given amount of arrows, health, rifle ammunitions, rockets, bazooka ammunitions, lasergun ammunitions and TNTs.

**Definition.** The *default inventory* is an inventory with the following amounts.

| **Item**             | **Amount** |
|----------------------|------------|
| Arrows               | 10/10      |
| Health               | 10/10      |
| Rifle ammunitions    | 0/10       |
| Rockets              | 0/10       |
| Bazooka ammunitions  | 0/10       |
| Lasergun ammunitions | 0/10       |
| TNTs                 | 0/10       |

**Requirement.** **If** a player is in-game, **then** they should have an inventory.

**Requirement.** **If** a player is **not** in-game, **then** they should **not** have an inventory.

**Requirement.** **When** a player joins the game **or** rejoins the game, their inventory should be the default inventory.

**Requirement.** **When** right-clicking on an `Ammunition arrow box` block, **if** the player has an inventory, **then**:
+ **if** the player is full of arrows, **then** `&WYou're already full of arrows.` should be printed to the user.
+ **else then** the arrow slot fould be filled **and** the corresponding block should be replaced with air for 20 seconds.

> The previous requirement applies to other weapons/health too.
