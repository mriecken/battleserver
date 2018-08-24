# BattleServer

The goal of the BattleServer project is to create a server that is capable of hosting and managing multiple networked battles where each contestant in the battle is represented by a unique, remote process.

Our initial intent is to make a distributed version of a game like RoboCode, where each "client" (each Robot team) is managed by the player's own machine.

The rules, physics, and general management of the game is governed by the BattleServer, while the individual actions of the participants is handled by the remote clients.

The remote clients can be written in any language that is capable of communicating over standard network protocols.

## Pluggable

The BattleServer will be able to host multiple game types.  Initially, each server will host a single game type, but this may change in the future.

## Scalable

Each battle server will be able to host multiple, simultaneous games.  When performance becomes an issue, the BattleServer will be capable of working in a cluster of BattleServers to share the load.

## Secure

No cheating!

## Open Source

So that you can make your own rules and host your own battles.

# Protocols

The game server will use specific language to communicate with clients to perform the following actions:

 1. Register a new player
 2. Login as an existing playter
 3. Get a list of game types
 4. Get a list of games waiting to start
 5. Get a list of games in progress
 6. Start a new game if allowed
 7. Join an existing game if allowed
 8. Observe an existing game if allowed
 9. Get basic server information (number of players, etc.)

Once a player joins a game,. communications will be handed off to the game module (which may be on another server in the future) which will be responsible for management of the game on a turn by turn basis.
