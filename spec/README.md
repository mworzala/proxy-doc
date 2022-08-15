# Proxy Scaling
The core idea is to have a proxy with much more advanced packet observability and manipulation capabilities than the current proxies which exist.

## How and Why?
The obvious question here is how moving computation to the proxy may improve overall performance. The answer is horizontal scaling. It is possible to run many proxies in front of one (or more) backing servers (e.g. spigot). This means that if we slow down a proxy, it does not matter since we can add another one and distribute the players between them.

## Applications
There are many ways to benefit from a more complex proxy, with varying benefits and complexity. Some examples are listed below:
* Anticheat
  * Grim uses a lightweight recreation of the game world per player, constructed by watching packets.
* Custom protocol
  * Batching packets for a specific player
  * Multi entity position packet
  * Multipart entity handling: backing server can treat the entities like any other entity type, and the proxy can translate that into a typical multipart entity.
* Bedrock compatibility
  * Abstract GUIs, converted to inventories on JE and fancy BE GUIs on BE. Obviously limited by what can be done in a JE inventory.
  * Multipart entity handling on proxy also helps here, since it could use the bedrock data pack entity system.

## General Scalability Benefit
This idea proposes using proxies for scaling, but it does not require that multiple proxies must be used. The user could run a single proxy, but since all “plugins” must pretend there might be many proxies, it would be very easy for the user to add more if they run into performance issues.

## Q/A
Q: insert question
A: insert answer
