# Variables

## Basics

Variables in Pyrite are defined with the `let` keyword.
You can use variables to reference entities. These are known as __Reference Variables__, or simply references.

```js
let zombies = select({
    "selector": "@e",
    "type": "zombies"
})
zombies.replaceitem("netherites_sword", "slot.weapon.mainhand")
```

One important concept to understand is that reference variables *can* reference multiple entities, like the example above.

Another type of variables are __Constant Variables__. These variables can be assigned an `Integer`, `String`, `Boolean` or `Vector3`. The are defined like this:

```js
let int = 3
let string = "hello world"
let bool = true
let vec = Vec3(1, 3, 0)
```

## Operations

You can also do operations with variables. Below gives an example:

```js
let int = 6 + 7 * 2 // 20
let string = "hello" + "world" // "helloworld"
let bool = true | false & true // true
let vec = Vec3(0, 1, 6) + Vec3(2, 9, -3) // Vec3( 2, 10, 3 )
```
