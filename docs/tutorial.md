# Getting Started with Pyrite

Pyrite is a tool for creating large Minecraft Bedrock command files with ease.
First, [download Pyrite](htpps://solarflurry.github.io/pyrite/download) if you have not already.

Pyrite generates a function file, which you need to put in a Behavior Pack. To create a Behavior Pack, follow the tutorial on the [Bedrock Wiki](https://wiki.bedrock.dev/guide/project-setup).

After your Behavior Pack is complete and you have applied it to your world, move your function file to the `your_behavior_pack/functions/pyrite/` directory. To run your function in game, use the command `/function pyrite/your_function_name`.

> Note: You can use the `/reload` command to reload your function files.

## The Basics

The first thing to understand about Pyrite is the `select` function. The select function selects an entity for resulting commands. The following code utilises `select`.
```
select(@a).say("Hello World!")
```
The code above reference all players (`@a`) and runs the `say` command.

The `select` function can take 2 different kinds of arguments. In the example above, it received a selector argument. Pyrite selectors are the regular Bedrock selectors:
- `@a` - All players
- `@e` - All entities
- `@p` - Closest player
- `@r` - Random player
- `@s` - Current entity
> Note: The `@initiator` selector does not do anything as Pyrite generates function files, not NPCs

The other type of selector uses JSON. It's format looks like this:
```
{
    "selector": "@e"
    "type": "zombie",
    "hasitem": {
        "item": "netherite_sword",
        "location": "slot.weapon.mainhand"
    },
    "name": "Ultra Zombie"
}
```
Let's break that down.
- `selector` means the selector (as mentioned above)
- `type` means the type of the entity i. e. `"zombie"`
- `hasitem` means the itemdata that the entity needs to have (more info on the [Bedrock Wiki](https://wiki.bedrock.dev/commands/selectors))
- `name` means the name of the entity i. e "Ultra Zombie"

This basically translates to `@r[type=zombie,name="Ultra Zombie",hasitem={item=netherite_sword,location=slot.weapon.mainhand}]` in commands.

For example, lets say we want all entities called "Grumm" to say "I'm upside-down!". We would first `select` these entities then run the `say` command.
```
// select all entities named "Grumm"
select({
    "selector": "@e",
    "name": "Grumm"
})
// make them say "I'm upside-down!"
.say("I'm upside-down!")
```

## Understanding

Now you want to understand the commands system in Pyrite. In Pyrite, the term 'command' refers to what you would call functions in JavaScript or C++. Commands need an entity to run on, and uses the `.` operator. In the previous examples, the format `entity.say()` was used.

Another thing to understand, which is probably one of the most important things, is the root entity. In Pyrite, the root entity refers to the entity that ran the function command. If a command does not have an entity referenced in the code, then it automatically references the root entity.
```
say("from the root entity")
select(@e).say("from a referenced entity")
```
In fact, `select` is also a command. Select can be run on a referenced entity as well as on the root entity.