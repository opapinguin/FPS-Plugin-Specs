# Lag compensation
## How Lag Compensation Works
In lag compensation, we adjust the game model according to latency. Most games--including ClassiCube--are server-centered, meaning that all information from one client to another must be routed through the server.

For instance, this will always mean that players see each other where they were some time ago, not where they are now. What is seen is all dependent on the observer. However, to discuss lag compensation, we must agree on an absolute time, which we take to be the time t on the server clock.

If player A has a ping of T_{a}, then the time it takes for player A to receive (and verify, as we're using TCP) a packet from the server is T_{a}. This means that, at any time, player A sees the server data as it was at time t-T_{a}. A similar argument can be made for player B.

As all packets are routed through the server, at time t player A observes player B as he was at time t-T_{a}-T_{b}, and player B observes player A at time t as he was at time t-T_{a}-T_{b} as well.

### An example
As an example of lag compensation, we can compensate for lag so that when player A fires his weapon at player B and hits on his screen, it will be registered as a hit on the server.

First note that when player A fires a weapon at time t, he will see the projectile as it was at time t-2T_{a} (one T_{a} for the key press, one for the block changes). Meanwhile, he sees player B as he was at time t-T_{a}-T_{b}.

It is therefore the server's responsibility to check collision of our gun, rewound in time to t-2T_{a}, against player B, at a rewound time t-T_{a}-T_{b}.
