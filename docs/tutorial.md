# Getting Started with Pyrite

Pyrite is a tool for creating large Minecraft Bedrock command files with ease.
First, [download Pyrite](htpps://solarflurry.github.io/pyrite/download) if you have not already.

Pyrite generates a function file, which you need to put in a Behavior Pack. To create a Behavior Pack, follow the tutorial on the [Bedrock Wiki](https://wiki.bedrock.dev/guide/project-setup).

After your Behavior Pack is complete and you have applied it to your world, move your function file to the `your_behavior_pack/functions/pyrite/` directory. To run your function in game, use the command `/function pyrite/your_function_name`.

> Note: You can use the `/reload` command to reload your function files.

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