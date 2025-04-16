# Getting Started with Pyrite

Pyrite is a tool for creating large Minecraft Bedrock command files with ease.
First, [download Pyrite](htpps://solarflurry.github.io/pyrite/download) if you have not already.

The first thing to understand about Pyrite is the `select` function. The select function selects an entity for resulting commands. The following code utilises `select`.
```select(@a).say("Hello World!")```
The code above reference all players (`@a`) and runs the `say` function.

The `select` function can take 2 different kinds of arguments. In the example above, it received a selector argument. Pyrite selectors are the regular Bedrock selectors:
- `@a` - All players
- `@e` - All entities
- `@p` - Closest player
- `@r` - Random player
- `@s` - Current entity
> Note: The `@initiator` selector does not do anything as Pyrite generates function files, not NPCs