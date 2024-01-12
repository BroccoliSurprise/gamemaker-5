# Game maker - Energy car

## Welcome to Game maker! 
Today we are making a sort of racing game. Follow the steps in this tutorial to get started.
When you're finished with the tutorial, you can generate a QR code you can scan with your phone to play and share the game with family and friends.


## Test the game
We've prepared some code for you. Click the game-screen to test the game.

## Random placement
A little randomness makes the game more exciting.
Let's have the car (``||Variables:mySprite||``) start in a random spot.

Grab a ``||scene:place mySprite on top of random||``-block from the ``||scene:Scene||``-menu, and place it at the bottom of the program.

Then click the gray square to choose which type of map-tile you want to start on.
	
*Reminder: You can press the light bulb at any time to see a solution.*


```blocks
namespace SpriteKind {
    export const Fuel = SpriteKind.create()
    export const Goal = SpriteKind.create()
}

scene.setBackgroundColor(9)
let mySprite = sprites.create(img`
    . . . . . . . . . . . . . . . . 
    . . . . 1 1 1 1 1 1 1 1 . . . . 
    . . . 1 b 1 1 1 1 1 1 6 1 . . . 
    . . 1 6 b 1 1 1 1 1 1 6 6 1 . . 
    . 1 6 6 b b b b b b 1 6 6 9 1 . 
    . 1 6 1 d d d d d d d b 6 9 1 1 
    . 1 1 b 6 6 d 6 6 6 d d 9 9 1 1 
    . 1 d 6 6 6 d 6 6 6 6 d 1 1 1 1 
    . d d 9 9 9 d 9 9 9 9 9 d 1 1 1 
    . d d d d d d c d d d c d 1 5 5 
    . d d d d d d c d d c d d d 1 5 
    . d d d d d d c c c d d d d d d 
    . d f f f f d d d d f f f d d d 
    . . f f f f f d d f f f f f d . 
    . . . f f f . . . . f f f f . . 
    . . . . . . . . . . . . . . . . 
    `, SpriteKind.Player)
controller.moveSprite(mySprite)
tiles.setCurrentTilemap(tilemap`approximation of western Norway`)

scene.cameraFollowSprite(mySprite)
let home = sprites.create(img`
    ....................e2e22e2e....................
    .................222eee22e2e222.................
    ..............222e22e2e22eee22e222..............
    ...........e22e22eeee2e22e2eeee22e22e...........
    ........eeee22e22e22e2e22e2e22e22e22eeee........
    .....222e22e22eeee22e2e22e2e22eeee22e22e222.....
    ...22eeee22e22e22e22eee22eee22e22e22e22eeee22...
    4cc22e22e22eeee22e22e2e22e2e22e22eeee22e22e22cc4
    6c6eee22e22e22e22e22e2e22e2e22e22e22e22e22eee6c6
    46622e22eeee22e22eeee2e22e2eeee22e22eeee22e22664
    46622e22e22e22eeee22e2e22e2e22eeee22e22e22e22664
    4cc22eeee22e22e22e22eee22eee22e22e22e22eeee22cc4
    6c622e22e22eeee22e22e2e22e2e22e22eeee22e22e226c6
    466eee22e22e22e22e22e2e22e2e22e22e22e22e22eee664
    46622e22eeee22e22e22e2e22e2e22e22e22eeee22e22664
    4cc22e22e22e22e22eeee2e22e2eeee22e22e22e22e22cc4
    6c622eeee22e22eeee22eee22eee22eeee22e22eeee226c6
    46622e22e22eeee22e22e2e22e2e22e22eeee22e22e22664
    466eee22e22e22e22e22e2e22e2e22e22e22e22e22eee664
    4cc22e22eeee22e22e22e2e22e2e22e22e22eeee22e22cc4
    6c622e22e22e22e22e22eee22eee22e22e22e22e22e226c6
    46622eeee22e22e22eeecc6666cceee22e22e22eeee22664
    46622e22e22e22eeecc6666666666cceee22e22e22e22664
    4cceee22e22eeecc66666cccccc66666cceee22e22eeecc4
    6c622e22eeecc66666cc64444446cc66666cceee22e226c6
    46622e22cc66666cc64444444444446cc66666cc22e22664
    46622cc6666ccc64444444444444444446ccc6666cc22664
    4ccc6666ccc6444bcc666666666666ccb4446ccc6666ccc4
    cccccccc6666666cb44444444444444bc6666666cccccccc
    64444444444446c444444444444444444c64444444444446
    66cb444444444cb411111111111111114bc444444444bc66
    666cccccccccccd166666666666666661dccccccccccc666
    6666444444444c116eeeeeeeeeeeeee611c4444444446666
    666e2222222e4c16e4e44e44e44e44ee61c4e2222222e666
    666eeeeeeeee4c16e4e44e44e44e44ee61c4eeeeeeeee666
    666eddddddde4c66f4e4effffffe44ee66c4eddddddde666
    666edffdffde4c66f4effffffffff4ee66c4edffdffde666
    666edccdccde4c66f4effffffffffeee66c4edccdccde666
    666eddddddde4c66f4eeeeeeeeeeeeee66c4eddddddde666
    c66edffdffde4c66e4e44e44e44e44ee66c4edffdffde66c
    c66edccdccde4c66e4e44e44e44e44ee66c4edccdccde66c
    cc66666666664c66e4e44e44e44feeee66c46666666666cc
    .c66444444444c66e4e44e44e44ffffe66c44444444466c.
    ..c64eee4eee4c66f4e44e44e44f44fe66c4eee4eee46c..
    ...c4eee4eee4c66f4e44e44e44effee66c4eee4eee4c...
    ....644444444c66f4e44e44e44e44ee66c444444446....
    .....64eee444c66f4e44e44e44e44ee66c444eee46.....
    ......6ccc666c66e4e44e44e44e44ee66c666ccc6......
    `, SpriteKind.Goal)

tiles.placeOnRandomTile(mySprite, sprites.castle.tileGrass1)


```



## Explore the map (tilemap)
The house **("home")** will be the spot you need to reach to win the game.

If you click the square in the ``||scene:tilemap||``-block and move the mouse around, the coordinates you are pointing at is shown at the bottom of the screen. 

Pick out the spot on the map where you want to place the house, and memorize the coordinates (i.e. "31, 27")



## Place the house
Grab a ``||scene:place mySprite on top of tilemap col 0 row 0||``, and place it at the bottom of the program.
Click on ``||variables:mySprite||`` in this new block, and change it to ``||variables:home||``.

Click on the numbers and replace them with the coordinates you memorized in the previous step. 


```blocks
namespace SpriteKind {
    export const Fuel = SpriteKind.create()
    export const Goal = SpriteKind.create()
}

scene.setBackgroundColor(9)
let mySprite = sprites.create(img`
    . . . . . . . . . . . . . . . . 
    . . . . 1 1 1 1 1 1 1 1 . . . . 
    . . . 1 b 1 1 1 1 1 1 6 1 . . . 
    . . 1 6 b 1 1 1 1 1 1 6 6 1 . . 
    . 1 6 6 b b b b b b 1 6 6 9 1 . 
    . 1 6 1 d d d d d d d b 6 9 1 1 
    . 1 1 b 6 6 d 6 6 6 d d 9 9 1 1 
    . 1 d 6 6 6 d 6 6 6 6 d 1 1 1 1 
    . d d 9 9 9 d 9 9 9 9 9 d 1 1 1 
    . d d d d d d c d d d c d 1 5 5 
    . d d d d d d c d d c d d d 1 5 
    . d d d d d d c c c d d d d d d 
    . d f f f f d d d d f f f d d d 
    . . f f f f f d d f f f f f d . 
    . . . f f f . . . . f f f f . . 
    . . . . . . . . . . . . . . . . 
    `, SpriteKind.Player)
controller.moveSprite(mySprite)
tiles.setCurrentTilemap(tilemap`approximation of western Norway`)

scene.cameraFollowSprite(mySprite)
let home = sprites.create(img`
    ....................e2e22e2e....................
    .................222eee22e2e222.................
    ..............222e22e2e22eee22e222..............
    ...........e22e22eeee2e22e2eeee22e22e...........
    ........eeee22e22e22e2e22e2e22e22e22eeee........
    .....222e22e22eeee22e2e22e2e22eeee22e22e222.....
    ...22eeee22e22e22e22eee22eee22e22e22e22eeee22...
    4cc22e22e22eeee22e22e2e22e2e22e22eeee22e22e22cc4
    6c6eee22e22e22e22e22e2e22e2e22e22e22e22e22eee6c6
    46622e22eeee22e22eeee2e22e2eeee22e22eeee22e22664
    46622e22e22e22eeee22e2e22e2e22eeee22e22e22e22664
    4cc22eeee22e22e22e22eee22eee22e22e22e22eeee22cc4
    6c622e22e22eeee22e22e2e22e2e22e22eeee22e22e226c6
    466eee22e22e22e22e22e2e22e2e22e22e22e22e22eee664
    46622e22eeee22e22e22e2e22e2e22e22e22eeee22e22664
    4cc22e22e22e22e22eeee2e22e2eeee22e22e22e22e22cc4
    6c622eeee22e22eeee22eee22eee22eeee22e22eeee226c6
    46622e22e22eeee22e22e2e22e2e22e22eeee22e22e22664
    466eee22e22e22e22e22e2e22e2e22e22e22e22e22eee664
    4cc22e22eeee22e22e22e2e22e2e22e22e22eeee22e22cc4
    6c622e22e22e22e22e22eee22eee22e22e22e22e22e226c6
    46622eeee22e22e22eeecc6666cceee22e22e22eeee22664
    46622e22e22e22eeecc6666666666cceee22e22e22e22664
    4cceee22e22eeecc66666cccccc66666cceee22e22eeecc4
    6c622e22eeecc66666cc64444446cc66666cceee22e226c6
    46622e22cc66666cc64444444444446cc66666cc22e22664
    46622cc6666ccc64444444444444444446ccc6666cc22664
    4ccc6666ccc6444bcc666666666666ccb4446ccc6666ccc4
    cccccccc6666666cb44444444444444bc6666666cccccccc
    64444444444446c444444444444444444c64444444444446
    66cb444444444cb411111111111111114bc444444444bc66
    666cccccccccccd166666666666666661dccccccccccc666
    6666444444444c116eeeeeeeeeeeeee611c4444444446666
    666e2222222e4c16e4e44e44e44e44ee61c4e2222222e666
    666eeeeeeeee4c16e4e44e44e44e44ee61c4eeeeeeeee666
    666eddddddde4c66f4e4effffffe44ee66c4eddddddde666
    666edffdffde4c66f4effffffffff4ee66c4edffdffde666
    666edccdccde4c66f4effffffffffeee66c4edccdccde666
    666eddddddde4c66f4eeeeeeeeeeeeee66c4eddddddde666
    c66edffdffde4c66e4e44e44e44e44ee66c4edffdffde66c
    c66edccdccde4c66e4e44e44e44e44ee66c4edccdccde66c
    cc66666666664c66e4e44e44e44feeee66c46666666666cc
    .c66444444444c66e4e44e44e44ffffe66c44444444466c.
    ..c64eee4eee4c66f4e44e44e44f44fe66c4eee4eee46c..
    ...c4eee4eee4c66f4e44e44e44effee66c4eee4eee4c...
    ....644444444c66f4e44e44e44e44ee66c444444446....
    .....64eee444c66f4e44e44e44e44ee66c444eee46.....
    ......6ccc666c66e4e44e44e44e44ee66c666ccc6......
    `, SpriteKind.Goal)

tiles.placeOnRandomTile(mySprite, sprites.castle.tileGrass1)

tiles.placeOnTile(home, tiles.getTileLocation(31, 27))

```


## Make new sprites
Our world is pretty barren, now it's time to fill it with stuff.

We'll start by adding a new kind of **Sprite** that later will award us points for picking up. 

Grab a ``||sprites:set mySprite2 to sprite of kind Player||``-block from the ``||sprites:Sprite||``-menu and add it to the program.

You can press the gray square to draw what you want, or pick a finished drawing from the **Gallery**.



```blocks
namespace SpriteKind {
    export const Fuel = SpriteKind.create()
    export const Goal = SpriteKind.create()
}

scene.setBackgroundColor(9)
let mySprite = sprites.create(img`
    . . . . . . . . . . . . . . . . 
    . . . . 1 1 1 1 1 1 1 1 . . . . 
    . . . 1 b 1 1 1 1 1 1 6 1 . . . 
    . . 1 6 b 1 1 1 1 1 1 6 6 1 . . 
    . 1 6 6 b b b b b b 1 6 6 9 1 . 
    . 1 6 1 d d d d d d d b 6 9 1 1 
    . 1 1 b 6 6 d 6 6 6 d d 9 9 1 1 
    . 1 d 6 6 6 d 6 6 6 6 d 1 1 1 1 
    . d d 9 9 9 d 9 9 9 9 9 d 1 1 1 
    . d d d d d d c d d d c d 1 5 5 
    . d d d d d d c d d c d d d 1 5 
    . d d d d d d c c c d d d d d d 
    . d f f f f d d d d f f f d d d 
    . . f f f f f d d f f f f f d . 
    . . . f f f . . . . f f f f . . 
    . . . . . . . . . . . . . . . . 
    `, SpriteKind.Player)
controller.moveSprite(mySprite)
tiles.setCurrentTilemap(tilemap`approximation of western Norway`)

scene.cameraFollowSprite(mySprite)
let home = sprites.create(img`
    ....................e2e22e2e....................
    .................222eee22e2e222.................
    ..............222e22e2e22eee22e222..............
    ...........e22e22eeee2e22e2eeee22e22e...........
    ........eeee22e22e22e2e22e2e22e22e22eeee........
    .....222e22e22eeee22e2e22e2e22eeee22e22e222.....
    ...22eeee22e22e22e22eee22eee22e22e22e22eeee22...
    4cc22e22e22eeee22e22e2e22e2e22e22eeee22e22e22cc4
    6c6eee22e22e22e22e22e2e22e2e22e22e22e22e22eee6c6
    46622e22eeee22e22eeee2e22e2eeee22e22eeee22e22664
    46622e22e22e22eeee22e2e22e2e22eeee22e22e22e22664
    4cc22eeee22e22e22e22eee22eee22e22e22e22eeee22cc4
    6c622e22e22eeee22e22e2e22e2e22e22eeee22e22e226c6
    466eee22e22e22e22e22e2e22e2e22e22e22e22e22eee664
    46622e22eeee22e22e22e2e22e2e22e22e22eeee22e22664
    4cc22e22e22e22e22eeee2e22e2eeee22e22e22e22e22cc4
    6c622eeee22e22eeee22eee22eee22eeee22e22eeee226c6
    46622e22e22eeee22e22e2e22e2e22e22eeee22e22e22664
    466eee22e22e22e22e22e2e22e2e22e22e22e22e22eee664
    4cc22e22eeee22e22e22e2e22e2e22e22e22eeee22e22cc4
    6c622e22e22e22e22e22eee22eee22e22e22e22e22e226c6
    46622eeee22e22e22eeecc6666cceee22e22e22eeee22664
    46622e22e22e22eeecc6666666666cceee22e22e22e22664
    4cceee22e22eeecc66666cccccc66666cceee22e22eeecc4
    6c622e22eeecc66666cc64444446cc66666cceee22e226c6
    46622e22cc66666cc64444444444446cc66666cc22e22664
    46622cc6666ccc64444444444444444446ccc6666cc22664
    4ccc6666ccc6444bcc666666666666ccb4446ccc6666ccc4
    cccccccc6666666cb44444444444444bc6666666cccccccc
    64444444444446c444444444444444444c64444444444446
    66cb444444444cb411111111111111114bc444444444bc66
    666cccccccccccd166666666666666661dccccccccccc666
    6666444444444c116eeeeeeeeeeeeee611c4444444446666
    666e2222222e4c16e4e44e44e44e44ee61c4e2222222e666
    666eeeeeeeee4c16e4e44e44e44e44ee61c4eeeeeeeee666
    666eddddddde4c66f4e4effffffe44ee66c4eddddddde666
    666edffdffde4c66f4effffffffff4ee66c4edffdffde666
    666edccdccde4c66f4effffffffffeee66c4edccdccde666
    666eddddddde4c66f4eeeeeeeeeeeeee66c4eddddddde666
    c66edffdffde4c66e4e44e44e44e44ee66c4edffdffde66c
    c66edccdccde4c66e4e44e44e44e44ee66c4edccdccde66c
    cc66666666664c66e4e44e44e44feeee66c46666666666cc
    .c66444444444c66e4e44e44e44ffffe66c44444444466c.
    ..c64eee4eee4c66f4e44e44e44f44fe66c4eee4eee46c..
    ...c4eee4eee4c66f4e44e44e44effee66c4eee4eee4c...
    ....644444444c66f4e44e44e44e44ee66c444444446....
    .....64eee444c66f4e44e44e44e44ee66c444eee46.....
    ......6ccc666c66e4e44e44e44e44ee66c666ccc6......
    `, SpriteKind.Goal)

tiles.placeOnRandomTile(mySprite, sprites.castle.tileGrass1)

tiles.placeOnTile(home, tiles.getTileLocation(40, 43))

mySprite2 = sprites.create(img`
        ....................
        ....................
        ....................
        ....................
        ....................
        ....................
        .......22...22......
        ......2322.2222.....
        ......232222222.....
        ......222222222.....
        .......22222b2......
        ........222b2.......
        .........222........
        ..........2.........
        ....................
        ....................
        ....................
        ....................
        ....................
        ....................
        `, SpriteKind.Player)

```




## Make a good name
Give the new Sprite a better name than ``||variables:mySprite2||``, i.e. ``||variables:power||``, or something that matches the drawing. 
Press the white arrow that says ``||sprites:Player||`` and swap to the ``||sprites:Fuel||``-type.


```blocks
namespace SpriteKind {
    export const Fuel = SpriteKind.create()
    export const Goal = SpriteKind.create()
}

scene.setBackgroundColor(9)
let mySprite = sprites.create(img`
    . . . . . . . . . . . . . . . . 
    . . . . 1 1 1 1 1 1 1 1 . . . . 
    . . . 1 b 1 1 1 1 1 1 6 1 . . . 
    . . 1 6 b 1 1 1 1 1 1 6 6 1 . . 
    . 1 6 6 b b b b b b 1 6 6 9 1 . 
    . 1 6 1 d d d d d d d b 6 9 1 1 
    . 1 1 b 6 6 d 6 6 6 d d 9 9 1 1 
    . 1 d 6 6 6 d 6 6 6 6 d 1 1 1 1 
    . d d 9 9 9 d 9 9 9 9 9 d 1 1 1 
    . d d d d d d c d d d c d 1 5 5 
    . d d d d d d c d d c d d d 1 5 
    . d d d d d d c c c d d d d d d 
    . d f f f f d d d d f f f d d d 
    . . f f f f f d d f f f f f d . 
    . . . f f f . . . . f f f f . . 
    . . . . . . . . . . . . . . . . 
    `, SpriteKind.Player)
controller.moveSprite(mySprite)
tiles.setCurrentTilemap(tilemap`approximation of western Norway`)

scene.cameraFollowSprite(mySprite)
let home = sprites.create(img`
    ....................e2e22e2e....................
    .................222eee22e2e222.................
    ..............222e22e2e22eee22e222..............
    ...........e22e22eeee2e22e2eeee22e22e...........
    ........eeee22e22e22e2e22e2e22e22e22eeee........
    .....222e22e22eeee22e2e22e2e22eeee22e22e222.....
    ...22eeee22e22e22e22eee22eee22e22e22e22eeee22...
    4cc22e22e22eeee22e22e2e22e2e22e22eeee22e22e22cc4
    6c6eee22e22e22e22e22e2e22e2e22e22e22e22e22eee6c6
    46622e22eeee22e22eeee2e22e2eeee22e22eeee22e22664
    46622e22e22e22eeee22e2e22e2e22eeee22e22e22e22664
    4cc22eeee22e22e22e22eee22eee22e22e22e22eeee22cc4
    6c622e22e22eeee22e22e2e22e2e22e22eeee22e22e226c6
    466eee22e22e22e22e22e2e22e2e22e22e22e22e22eee664
    46622e22eeee22e22e22e2e22e2e22e22e22eeee22e22664
    4cc22e22e22e22e22eeee2e22e2eeee22e22e22e22e22cc4
    6c622eeee22e22eeee22eee22eee22eeee22e22eeee226c6
    46622e22e22eeee22e22e2e22e2e22e22eeee22e22e22664
    466eee22e22e22e22e22e2e22e2e22e22e22e22e22eee664
    4cc22e22eeee22e22e22e2e22e2e22e22e22eeee22e22cc4
    6c622e22e22e22e22e22eee22eee22e22e22e22e22e226c6
    46622eeee22e22e22eeecc6666cceee22e22e22eeee22664
    46622e22e22e22eeecc6666666666cceee22e22e22e22664
    4cceee22e22eeecc66666cccccc66666cceee22e22eeecc4
    6c622e22eeecc66666cc64444446cc66666cceee22e226c6
    46622e22cc66666cc64444444444446cc66666cc22e22664
    46622cc6666ccc64444444444444444446ccc6666cc22664
    4ccc6666ccc6444bcc666666666666ccb4446ccc6666ccc4
    cccccccc6666666cb44444444444444bc6666666cccccccc
    64444444444446c444444444444444444c64444444444446
    66cb444444444cb411111111111111114bc444444444bc66
    666cccccccccccd166666666666666661dccccccccccc666
    6666444444444c116eeeeeeeeeeeeee611c4444444446666
    666e2222222e4c16e4e44e44e44e44ee61c4e2222222e666
    666eeeeeeeee4c16e4e44e44e44e44ee61c4eeeeeeeee666
    666eddddddde4c66f4e4effffffe44ee66c4eddddddde666
    666edffdffde4c66f4effffffffff4ee66c4edffdffde666
    666edccdccde4c66f4effffffffffeee66c4edccdccde666
    666eddddddde4c66f4eeeeeeeeeeeeee66c4eddddddde666
    c66edffdffde4c66e4e44e44e44e44ee66c4edffdffde66c
    c66edccdccde4c66e4e44e44e44e44ee66c4edccdccde66c
    cc66666666664c66e4e44e44e44feeee66c46666666666cc
    .c66444444444c66e4e44e44e44ffffe66c44444444466c.
    ..c64eee4eee4c66f4e44e44e44f44fe66c4eee4eee46c..
    ...c4eee4eee4c66f4e44e44e44effee66c4eee4eee4c...
    ....644444444c66f4e44e44e44e44ee66c444444446....
    .....64eee444c66f4e44e44e44e44ee66c444eee46.....
    ......6ccc666c66e4e44e44e44e44ee66c666ccc6......
    `, SpriteKind.Goal)

tiles.placeOnRandomTile(mySprite, sprites.castle.tileGrass1)

tiles.placeOnTile(home, tiles.getTileLocation(40, 43))

power = sprites.create(img`
        ....................
        ....................
        ....................
        ....................
        ....................
        ....................
        .......22...22......
        ......2322.2222.....
        ......232222222.....
        ......222222222.....
        .......22222b2......
        ........222b2.......
        .........222........
        ..........2.........
        ....................
        ....................
        ....................
        ....................
        ....................
        ....................
        `, SpriteKind.Fuel)

```



## The repeat-block

Find a ``||loops:repeat||``-block in the ``||loops:loop||``-menu, and place it in the program so that it envelops the **Fuel**-sprite.

Set it to repeat 100 times.

```blocks
namespace SpriteKind {
    export const Fuel = SpriteKind.create()
    export const Goal = SpriteKind.create()
}

scene.setBackgroundColor(9)
let mySprite = sprites.create(img`
    . . . . . . . . . . . . . . . . 
    . . . . 1 1 1 1 1 1 1 1 . . . . 
    . . . 1 b 1 1 1 1 1 1 6 1 . . . 
    . . 1 6 b 1 1 1 1 1 1 6 6 1 . . 
    . 1 6 6 b b b b b b 1 6 6 9 1 . 
    . 1 6 1 d d d d d d d b 6 9 1 1 
    . 1 1 b 6 6 d 6 6 6 d d 9 9 1 1 
    . 1 d 6 6 6 d 6 6 6 6 d 1 1 1 1 
    . d d 9 9 9 d 9 9 9 9 9 d 1 1 1 
    . d d d d d d c d d d c d 1 5 5 
    . d d d d d d c d d c d d d 1 5 
    . d d d d d d c c c d d d d d d 
    . d f f f f d d d d f f f d d d 
    . . f f f f f d d f f f f f d . 
    . . . f f f . . . . f f f f . . 
    . . . . . . . . . . . . . . . . 
    `, SpriteKind.Player)
controller.moveSprite(mySprite)
tiles.setCurrentTilemap(tilemap`approximation of western Norway`)

scene.cameraFollowSprite(mySprite)
let home = sprites.create(img`
    ....................e2e22e2e....................
    .................222eee22e2e222.................
    ..............222e22e2e22eee22e222..............
    ...........e22e22eeee2e22e2eeee22e22e...........
    ........eeee22e22e22e2e22e2e22e22e22eeee........
    .....222e22e22eeee22e2e22e2e22eeee22e22e222.....
    ...22eeee22e22e22e22eee22eee22e22e22e22eeee22...
    4cc22e22e22eeee22e22e2e22e2e22e22eeee22e22e22cc4
    6c6eee22e22e22e22e22e2e22e2e22e22e22e22e22eee6c6
    46622e22eeee22e22eeee2e22e2eeee22e22eeee22e22664
    46622e22e22e22eeee22e2e22e2e22eeee22e22e22e22664
    4cc22eeee22e22e22e22eee22eee22e22e22e22eeee22cc4
    6c622e22e22eeee22e22e2e22e2e22e22eeee22e22e226c6
    466eee22e22e22e22e22e2e22e2e22e22e22e22e22eee664
    46622e22eeee22e22e22e2e22e2e22e22e22eeee22e22664
    4cc22e22e22e22e22eeee2e22e2eeee22e22e22e22e22cc4
    6c622eeee22e22eeee22eee22eee22eeee22e22eeee226c6
    46622e22e22eeee22e22e2e22e2e22e22eeee22e22e22664
    466eee22e22e22e22e22e2e22e2e22e22e22e22e22eee664
    4cc22e22eeee22e22e22e2e22e2e22e22e22eeee22e22cc4
    6c622e22e22e22e22e22eee22eee22e22e22e22e22e226c6
    46622eeee22e22e22eeecc6666cceee22e22e22eeee22664
    46622e22e22e22eeecc6666666666cceee22e22e22e22664
    4cceee22e22eeecc66666cccccc66666cceee22e22eeecc4
    6c622e22eeecc66666cc64444446cc66666cceee22e226c6
    46622e22cc66666cc64444444444446cc66666cc22e22664
    46622cc6666ccc64444444444444444446ccc6666cc22664
    4ccc6666ccc6444bcc666666666666ccb4446ccc6666ccc4
    cccccccc6666666cb44444444444444bc6666666cccccccc
    64444444444446c444444444444444444c64444444444446
    66cb444444444cb411111111111111114bc444444444bc66
    666cccccccccccd166666666666666661dccccccccccc666
    6666444444444c116eeeeeeeeeeeeee611c4444444446666
    666e2222222e4c16e4e44e44e44e44ee61c4e2222222e666
    666eeeeeeeee4c16e4e44e44e44e44ee61c4eeeeeeeee666
    666eddddddde4c66f4e4effffffe44ee66c4eddddddde666
    666edffdffde4c66f4effffffffff4ee66c4edffdffde666
    666edccdccde4c66f4effffffffffeee66c4edccdccde666
    666eddddddde4c66f4eeeeeeeeeeeeee66c4eddddddde666
    c66edffdffde4c66e4e44e44e44e44ee66c4edffdffde66c
    c66edccdccde4c66e4e44e44e44e44ee66c4edccdccde66c
    cc66666666664c66e4e44e44e44feeee66c46666666666cc
    .c66444444444c66e4e44e44e44ffffe66c44444444466c.
    ..c64eee4eee4c66f4e44e44e44f44fe66c4eee4eee46c..
    ...c4eee4eee4c66f4e44e44e44effee66c4eee4eee4c...
    ....644444444c66f4e44e44e44e44ee66c444444446....
    .....64eee444c66f4e44e44e44e44ee66c444eee46.....
    ......6ccc666c66e4e44e44e44e44ee66c666ccc6......
    `, SpriteKind.Goal)

tiles.placeOnRandomTile(mySprite, sprites.castle.tileGrass1)

tiles.placeOnTile(home, tiles.getTileLocation(40, 43))
for (let index = 0; index < 100; index++) {
power = sprites.create(img`
        ....................
        ....................
        ....................
        ....................
        ....................
        ....................
        .......22...22......
        ......2322.2222.....
        ......232222222.....
        ......222222222.....
        .......22222b2......
        ........222b2.......
        .........222........
        ..........2.........
        ....................
        ....................
        ....................
        ....................
        ....................
        ....................
        `, SpriteKind.Fuel)
}
```



## Place sprites all over
Now we have 100 Fuel-sprites, but they're all in the same spot.

Put a ``||scene:place mySprite on top of random||``-block inside the ``||loops:repeat||``-block, and switch from ``||variables:mySprite||`` to what you named the Fuel-sprite.

Press the gray square to choose where to place the Fuel-sprites.


```blocks
namespace SpriteKind {
    export const Fuel = SpriteKind.create()
    export const Goal = SpriteKind.create()
}

scene.setBackgroundColor(9)
let mySprite = sprites.create(img`
    . . . . . . . . . . . . . . . . 
    . . . . 1 1 1 1 1 1 1 1 . . . . 
    . . . 1 b 1 1 1 1 1 1 6 1 . . . 
    . . 1 6 b 1 1 1 1 1 1 6 6 1 . . 
    . 1 6 6 b b b b b b 1 6 6 9 1 . 
    . 1 6 1 d d d d d d d b 6 9 1 1 
    . 1 1 b 6 6 d 6 6 6 d d 9 9 1 1 
    . 1 d 6 6 6 d 6 6 6 6 d 1 1 1 1 
    . d d 9 9 9 d 9 9 9 9 9 d 1 1 1 
    . d d d d d d c d d d c d 1 5 5 
    . d d d d d d c d d c d d d 1 5 
    . d d d d d d c c c d d d d d d 
    . d f f f f d d d d f f f d d d 
    . . f f f f f d d f f f f f d . 
    . . . f f f . . . . f f f f . . 
    . . . . . . . . . . . . . . . . 
    `, SpriteKind.Player)
controller.moveSprite(mySprite)
tiles.setCurrentTilemap(tilemap`approximation of western Norway`)

scene.cameraFollowSprite(mySprite)
let home = sprites.create(img`
    ....................e2e22e2e....................
    .................222eee22e2e222.................
    ..............222e22e2e22eee22e222..............
    ...........e22e22eeee2e22e2eeee22e22e...........
    ........eeee22e22e22e2e22e2e22e22e22eeee........
    .....222e22e22eeee22e2e22e2e22eeee22e22e222.....
    ...22eeee22e22e22e22eee22eee22e22e22e22eeee22...
    4cc22e22e22eeee22e22e2e22e2e22e22eeee22e22e22cc4
    6c6eee22e22e22e22e22e2e22e2e22e22e22e22e22eee6c6
    46622e22eeee22e22eeee2e22e2eeee22e22eeee22e22664
    46622e22e22e22eeee22e2e22e2e22eeee22e22e22e22664
    4cc22eeee22e22e22e22eee22eee22e22e22e22eeee22cc4
    6c622e22e22eeee22e22e2e22e2e22e22eeee22e22e226c6
    466eee22e22e22e22e22e2e22e2e22e22e22e22e22eee664
    46622e22eeee22e22e22e2e22e2e22e22e22eeee22e22664
    4cc22e22e22e22e22eeee2e22e2eeee22e22e22e22e22cc4
    6c622eeee22e22eeee22eee22eee22eeee22e22eeee226c6
    46622e22e22eeee22e22e2e22e2e22e22eeee22e22e22664
    466eee22e22e22e22e22e2e22e2e22e22e22e22e22eee664
    4cc22e22eeee22e22e22e2e22e2e22e22e22eeee22e22cc4
    6c622e22e22e22e22e22eee22eee22e22e22e22e22e226c6
    46622eeee22e22e22eeecc6666cceee22e22e22eeee22664
    46622e22e22e22eeecc6666666666cceee22e22e22e22664
    4cceee22e22eeecc66666cccccc66666cceee22e22eeecc4
    6c622e22eeecc66666cc64444446cc66666cceee22e226c6
    46622e22cc66666cc64444444444446cc66666cc22e22664
    46622cc6666ccc64444444444444444446ccc6666cc22664
    4ccc6666ccc6444bcc666666666666ccb4446ccc6666ccc4
    cccccccc6666666cb44444444444444bc6666666cccccccc
    64444444444446c444444444444444444c64444444444446
    66cb444444444cb411111111111111114bc444444444bc66
    666cccccccccccd166666666666666661dccccccccccc666
    6666444444444c116eeeeeeeeeeeeee611c4444444446666
    666e2222222e4c16e4e44e44e44e44ee61c4e2222222e666
    666eeeeeeeee4c16e4e44e44e44e44ee61c4eeeeeeeee666
    666eddddddde4c66f4e4effffffe44ee66c4eddddddde666
    666edffdffde4c66f4effffffffff4ee66c4edffdffde666
    666edccdccde4c66f4effffffffffeee66c4edccdccde666
    666eddddddde4c66f4eeeeeeeeeeeeee66c4eddddddde666
    c66edffdffde4c66e4e44e44e44e44ee66c4edffdffde66c
    c66edccdccde4c66e4e44e44e44e44ee66c4edccdccde66c
    cc66666666664c66e4e44e44e44feeee66c46666666666cc
    .c66444444444c66e4e44e44e44ffffe66c44444444466c.
    ..c64eee4eee4c66f4e44e44e44f44fe66c4eee4eee46c..
    ...c4eee4eee4c66f4e44e44e44effee66c4eee4eee4c...
    ....644444444c66f4e44e44e44e44ee66c444444446....
    .....64eee444c66f4e44e44e44e44ee66c444eee46.....
    ......6ccc666c66e4e44e44e44e44ee66c666ccc6......
    `, SpriteKind.Goal)

tiles.placeOnRandomTile(mySprite, sprites.castle.tileGrass1)

tiles.placeOnTile(home, tiles.getTileLocation(40, 43))
for (let index = 0; index < 100; index++) {
    power = sprites.create(img`
            ....................
            ....................
            ....................
            ....................
            ....................
            ....................
            .......22...22......
            ......2322.2222.....
            ......232222222.....
            ......222222222.....
            .......22222b2......
            ........222b2.......
            .........222........
            ..........2.........
            ....................
            ....................
            ....................
            ....................
            ....................
            ....................
            `, SpriteKind.Fuel)
	tiles.placeOnRandomTile(power, sprites.castle.tileGrass1)
}
```

## Sprites interacts
Now we're going to program it so that something happens when you drive into a Fuel-sprite.

Grab a ``||sprites:on sprite of kind player overlaps...||``-block in the ``||sprites:Sprites||``-menu, and put it somewhere in your program outside of the ``||loops:on start||``-block. (Over, under, to the side or anywhere.)


```blocks
namespace SpriteKind {
    export const Fuel = SpriteKind.create()
    export const Goal = SpriteKind.create()
}

scene.setBackgroundColor(9)
let mySprite = sprites.create(img`
    . . . . . . . . . . . . . . . . 
    . . . . 1 1 1 1 1 1 1 1 . . . . 
    . . . 1 b 1 1 1 1 1 1 6 1 . . . 
    . . 1 6 b 1 1 1 1 1 1 6 6 1 . . 
    . 1 6 6 b b b b b b 1 6 6 9 1 . 
    . 1 6 1 d d d d d d d b 6 9 1 1 
    . 1 1 b 6 6 d 6 6 6 d d 9 9 1 1 
    . 1 d 6 6 6 d 6 6 6 6 d 1 1 1 1 
    . d d 9 9 9 d 9 9 9 9 9 d 1 1 1 
    . d d d d d d c d d d c d 1 5 5 
    . d d d d d d c d d c d d d 1 5 
    . d d d d d d c c c d d d d d d 
    . d f f f f d d d d f f f d d d 
    . . f f f f f d d f f f f f d . 
    . . . f f f . . . . f f f f . . 
    . . . . . . . . . . . . . . . . 
    `, SpriteKind.Player)
controller.moveSprite(mySprite)
tiles.setCurrentTilemap(tilemap`approximation of western Norway`)

scene.cameraFollowSprite(mySprite)
let home = sprites.create(img`
    ....................e2e22e2e....................
    .................222eee22e2e222.................
    ..............222e22e2e22eee22e222..............
    ...........e22e22eeee2e22e2eeee22e22e...........
    ........eeee22e22e22e2e22e2e22e22e22eeee........
    .....222e22e22eeee22e2e22e2e22eeee22e22e222.....
    ...22eeee22e22e22e22eee22eee22e22e22e22eeee22...
    4cc22e22e22eeee22e22e2e22e2e22e22eeee22e22e22cc4
    6c6eee22e22e22e22e22e2e22e2e22e22e22e22e22eee6c6
    46622e22eeee22e22eeee2e22e2eeee22e22eeee22e22664
    46622e22e22e22eeee22e2e22e2e22eeee22e22e22e22664
    4cc22eeee22e22e22e22eee22eee22e22e22e22eeee22cc4
    6c622e22e22eeee22e22e2e22e2e22e22eeee22e22e226c6
    466eee22e22e22e22e22e2e22e2e22e22e22e22e22eee664
    46622e22eeee22e22e22e2e22e2e22e22e22eeee22e22664
    4cc22e22e22e22e22eeee2e22e2eeee22e22e22e22e22cc4
    6c622eeee22e22eeee22eee22eee22eeee22e22eeee226c6
    46622e22e22eeee22e22e2e22e2e22e22eeee22e22e22664
    466eee22e22e22e22e22e2e22e2e22e22e22e22e22eee664
    4cc22e22eeee22e22e22e2e22e2e22e22e22eeee22e22cc4
    6c622e22e22e22e22e22eee22eee22e22e22e22e22e226c6
    46622eeee22e22e22eeecc6666cceee22e22e22eeee22664
    46622e22e22e22eeecc6666666666cceee22e22e22e22664
    4cceee22e22eeecc66666cccccc66666cceee22e22eeecc4
    6c622e22eeecc66666cc64444446cc66666cceee22e226c6
    46622e22cc66666cc64444444444446cc66666cc22e22664
    46622cc6666ccc64444444444444444446ccc6666cc22664
    4ccc6666ccc6444bcc666666666666ccb4446ccc6666ccc4
    cccccccc6666666cb44444444444444bc6666666cccccccc
    64444444444446c444444444444444444c64444444444446
    66cb444444444cb411111111111111114bc444444444bc66
    666cccccccccccd166666666666666661dccccccccccc666
    6666444444444c116eeeeeeeeeeeeee611c4444444446666
    666e2222222e4c16e4e44e44e44e44ee61c4e2222222e666
    666eeeeeeeee4c16e4e44e44e44e44ee61c4eeeeeeeee666
    666eddddddde4c66f4e4effffffe44ee66c4eddddddde666
    666edffdffde4c66f4effffffffff4ee66c4edffdffde666
    666edccdccde4c66f4effffffffffeee66c4edccdccde666
    666eddddddde4c66f4eeeeeeeeeeeeee66c4eddddddde666
    c66edffdffde4c66e4e44e44e44e44ee66c4edffdffde66c
    c66edccdccde4c66e4e44e44e44e44ee66c4edccdccde66c
    cc66666666664c66e4e44e44e44feeee66c46666666666cc
    .c66444444444c66e4e44e44e44ffffe66c44444444466c.
    ..c64eee4eee4c66f4e44e44e44f44fe66c4eee4eee46c..
    ...c4eee4eee4c66f4e44e44e44effee66c4eee4eee4c...
    ....644444444c66f4e44e44e44e44ee66c444444446....
    .....64eee444c66f4e44e44e44e44ee66c444eee46.....
    ......6ccc666c66e4e44e44e44e44ee66c666ccc6......
    `, SpriteKind.Goal)

tiles.placeOnRandomTile(mySprite, sprites.castle.tileGrass1)

tiles.placeOnTile(home, tiles.getTileLocation(40, 43))
for (let index = 0; index < 100; index++) {
    power = sprites.create(img`
            ....................
            ....................
            ....................
            ....................
            ....................
            ....................
            .......22...22......
            ......2322.2222.....
            ......232222222.....
            ......222222222.....
            .......22222b2......
            ........222b2.......
            .........222........
            ..........2.........
            ....................
            ....................
            ....................
            ....................
            ....................
            ....................
            `, SpriteKind.Fuel)
	tiles.placeOnRandomTile(power, sprites.castle.tileGrass1)
}

sprites.onOverlap(SpriteKind.Player, SpriteKind.Player, function (sprite, otherSprite) {

})

```


## Choose the correct Sprite type

In the ``||sprites:...Player overlaps otherSprite...||``-block you just made, you need to set it to check if a **Player**-sprite touches a **Fuel**-sprite. 

Click the white arrow in the oval to the right to swap.



```blocks
namespace SpriteKind {
    export const Fuel = SpriteKind.create()
    export const Goal = SpriteKind.create()
}

scene.setBackgroundColor(9)
let mySprite = sprites.create(img`
    . . . . . . . . . . . . . . . . 
    . . . . 1 1 1 1 1 1 1 1 . . . . 
    . . . 1 b 1 1 1 1 1 1 6 1 . . . 
    . . 1 6 b 1 1 1 1 1 1 6 6 1 . . 
    . 1 6 6 b b b b b b 1 6 6 9 1 . 
    . 1 6 1 d d d d d d d b 6 9 1 1 
    . 1 1 b 6 6 d 6 6 6 d d 9 9 1 1 
    . 1 d 6 6 6 d 6 6 6 6 d 1 1 1 1 
    . d d 9 9 9 d 9 9 9 9 9 d 1 1 1 
    . d d d d d d c d d d c d 1 5 5 
    . d d d d d d c d d c d d d 1 5 
    . d d d d d d c c c d d d d d d 
    . d f f f f d d d d f f f d d d 
    . . f f f f f d d f f f f f d . 
    . . . f f f . . . . f f f f . . 
    . . . . . . . . . . . . . . . . 
    `, SpriteKind.Player)
controller.moveSprite(mySprite)
tiles.setCurrentTilemap(tilemap`approximation of western Norway`)

scene.cameraFollowSprite(mySprite)
let home = sprites.create(img`
    ....................e2e22e2e....................
    .................222eee22e2e222.................
    ..............222e22e2e22eee22e222..............
    ...........e22e22eeee2e22e2eeee22e22e...........
    ........eeee22e22e22e2e22e2e22e22e22eeee........
    .....222e22e22eeee22e2e22e2e22eeee22e22e222.....
    ...22eeee22e22e22e22eee22eee22e22e22e22eeee22...
    4cc22e22e22eeee22e22e2e22e2e22e22eeee22e22e22cc4
    6c6eee22e22e22e22e22e2e22e2e22e22e22e22e22eee6c6
    46622e22eeee22e22eeee2e22e2eeee22e22eeee22e22664
    46622e22e22e22eeee22e2e22e2e22eeee22e22e22e22664
    4cc22eeee22e22e22e22eee22eee22e22e22e22eeee22cc4
    6c622e22e22eeee22e22e2e22e2e22e22eeee22e22e226c6
    466eee22e22e22e22e22e2e22e2e22e22e22e22e22eee664
    46622e22eeee22e22e22e2e22e2e22e22e22eeee22e22664
    4cc22e22e22e22e22eeee2e22e2eeee22e22e22e22e22cc4
    6c622eeee22e22eeee22eee22eee22eeee22e22eeee226c6
    46622e22e22eeee22e22e2e22e2e22e22eeee22e22e22664
    466eee22e22e22e22e22e2e22e2e22e22e22e22e22eee664
    4cc22e22eeee22e22e22e2e22e2e22e22e22eeee22e22cc4
    6c622e22e22e22e22e22eee22eee22e22e22e22e22e226c6
    46622eeee22e22e22eeecc6666cceee22e22e22eeee22664
    46622e22e22e22eeecc6666666666cceee22e22e22e22664
    4cceee22e22eeecc66666cccccc66666cceee22e22eeecc4
    6c622e22eeecc66666cc64444446cc66666cceee22e226c6
    46622e22cc66666cc64444444444446cc66666cc22e22664
    46622cc6666ccc64444444444444444446ccc6666cc22664
    4ccc6666ccc6444bcc666666666666ccb4446ccc6666ccc4
    cccccccc6666666cb44444444444444bc6666666cccccccc
    64444444444446c444444444444444444c64444444444446
    66cb444444444cb411111111111111114bc444444444bc66
    666cccccccccccd166666666666666661dccccccccccc666
    6666444444444c116eeeeeeeeeeeeee611c4444444446666
    666e2222222e4c16e4e44e44e44e44ee61c4e2222222e666
    666eeeeeeeee4c16e4e44e44e44e44ee61c4eeeeeeeee666
    666eddddddde4c66f4e4effffffe44ee66c4eddddddde666
    666edffdffde4c66f4effffffffff4ee66c4edffdffde666
    666edccdccde4c66f4effffffffffeee66c4edccdccde666
    666eddddddde4c66f4eeeeeeeeeeeeee66c4eddddddde666
    c66edffdffde4c66e4e44e44e44e44ee66c4edffdffde66c
    c66edccdccde4c66e4e44e44e44e44ee66c4edccdccde66c
    cc66666666664c66e4e44e44e44feeee66c46666666666cc
    .c66444444444c66e4e44e44e44ffffe66c44444444466c.
    ..c64eee4eee4c66f4e44e44e44f44fe66c4eee4eee46c..
    ...c4eee4eee4c66f4e44e44e44effee66c4eee4eee4c...
    ....644444444c66f4e44e44e44e44ee66c444444446....
    .....64eee444c66f4e44e44e44e44ee66c444eee46.....
    ......6ccc666c66e4e44e44e44e44ee66c666ccc6......
    `, SpriteKind.Goal)

tiles.placeOnRandomTile(mySprite, sprites.castle.tileGrass1)

tiles.placeOnTile(home, tiles.getTileLocation(40, 43))
for (let index = 0; index < 100; index++) {
    power = sprites.create(img`
            ....................
            ....................
            ....................
            ....................
            ....................
            ....................
            .......22...22......
            ......2322.2222.....
            ......232222222.....
            ......222222222.....
            .......22222b2......
            ........222b2.......
            .........222........
            ..........2.........
            ....................
            ....................
            ....................
            ....................
            ....................
            ....................
            `, SpriteKind.Fuel)
	tiles.placeOnRandomTile(power, sprites.castle.tileGrass1)
}

sprites.onOverlap(SpriteKind.Player, SpriteKind.Fuel, function (sprite, otherSprite) {

})

```


## Points 

We want points when we touch a Fuel-sprite. Grab a ``||info:change score by 1||``-block from the ``||info:Info||``-menu.


```blocks
namespace SpriteKind {
    export const Fuel = SpriteKind.create()
    export const Goal = SpriteKind.create()
}

scene.setBackgroundColor(9)
let mySprite = sprites.create(img`
    . . . . . . . . . . . . . . . . 
    . . . . 1 1 1 1 1 1 1 1 . . . . 
    . . . 1 b 1 1 1 1 1 1 6 1 . . . 
    . . 1 6 b 1 1 1 1 1 1 6 6 1 . . 
    . 1 6 6 b b b b b b 1 6 6 9 1 . 
    . 1 6 1 d d d d d d d b 6 9 1 1 
    . 1 1 b 6 6 d 6 6 6 d d 9 9 1 1 
    . 1 d 6 6 6 d 6 6 6 6 d 1 1 1 1 
    . d d 9 9 9 d 9 9 9 9 9 d 1 1 1 
    . d d d d d d c d d d c d 1 5 5 
    . d d d d d d c d d c d d d 1 5 
    . d d d d d d c c c d d d d d d 
    . d f f f f d d d d f f f d d d 
    . . f f f f f d d f f f f f d . 
    . . . f f f . . . . f f f f . . 
    . . . . . . . . . . . . . . . . 
    `, SpriteKind.Player)
controller.moveSprite(mySprite)
tiles.setCurrentTilemap(tilemap`approximation of western Norway`)

scene.cameraFollowSprite(mySprite)
let home = sprites.create(img`
    ....................e2e22e2e....................
    .................222eee22e2e222.................
    ..............222e22e2e22eee22e222..............
    ...........e22e22eeee2e22e2eeee22e22e...........
    ........eeee22e22e22e2e22e2e22e22e22eeee........
    .....222e22e22eeee22e2e22e2e22eeee22e22e222.....
    ...22eeee22e22e22e22eee22eee22e22e22e22eeee22...
    4cc22e22e22eeee22e22e2e22e2e22e22eeee22e22e22cc4
    6c6eee22e22e22e22e22e2e22e2e22e22e22e22e22eee6c6
    46622e22eeee22e22eeee2e22e2eeee22e22eeee22e22664
    46622e22e22e22eeee22e2e22e2e22eeee22e22e22e22664
    4cc22eeee22e22e22e22eee22eee22e22e22e22eeee22cc4
    6c622e22e22eeee22e22e2e22e2e22e22eeee22e22e226c6
    466eee22e22e22e22e22e2e22e2e22e22e22e22e22eee664
    46622e22eeee22e22e22e2e22e2e22e22e22eeee22e22664
    4cc22e22e22e22e22eeee2e22e2eeee22e22e22e22e22cc4
    6c622eeee22e22eeee22eee22eee22eeee22e22eeee226c6
    46622e22e22eeee22e22e2e22e2e22e22eeee22e22e22664
    466eee22e22e22e22e22e2e22e2e22e22e22e22e22eee664
    4cc22e22eeee22e22e22e2e22e2e22e22e22eeee22e22cc4
    6c622e22e22e22e22e22eee22eee22e22e22e22e22e226c6
    46622eeee22e22e22eeecc6666cceee22e22e22eeee22664
    46622e22e22e22eeecc6666666666cceee22e22e22e22664
    4cceee22e22eeecc66666cccccc66666cceee22e22eeecc4
    6c622e22eeecc66666cc64444446cc66666cceee22e226c6
    46622e22cc66666cc64444444444446cc66666cc22e22664
    46622cc6666ccc64444444444444444446ccc6666cc22664
    4ccc6666ccc6444bcc666666666666ccb4446ccc6666ccc4
    cccccccc6666666cb44444444444444bc6666666cccccccc
    64444444444446c444444444444444444c64444444444446
    66cb444444444cb411111111111111114bc444444444bc66
    666cccccccccccd166666666666666661dccccccccccc666
    6666444444444c116eeeeeeeeeeeeee611c4444444446666
    666e2222222e4c16e4e44e44e44e44ee61c4e2222222e666
    666eeeeeeeee4c16e4e44e44e44e44ee61c4eeeeeeeee666
    666eddddddde4c66f4e4effffffe44ee66c4eddddddde666
    666edffdffde4c66f4effffffffff4ee66c4edffdffde666
    666edccdccde4c66f4effffffffffeee66c4edccdccde666
    666eddddddde4c66f4eeeeeeeeeeeeee66c4eddddddde666
    c66edffdffde4c66e4e44e44e44e44ee66c4edffdffde66c
    c66edccdccde4c66e4e44e44e44e44ee66c4edccdccde66c
    cc66666666664c66e4e44e44e44feeee66c46666666666cc
    .c66444444444c66e4e44e44e44ffffe66c44444444466c.
    ..c64eee4eee4c66f4e44e44e44f44fe66c4eee4eee46c..
    ...c4eee4eee4c66f4e44e44e44effee66c4eee4eee4c...
    ....644444444c66f4e44e44e44e44ee66c444444446....
    .....64eee444c66f4e44e44e44e44ee66c444eee46.....
    ......6ccc666c66e4e44e44e44e44ee66c666ccc6......
    `, SpriteKind.Goal)

tiles.placeOnRandomTile(mySprite, sprites.castle.tileGrass1)

tiles.placeOnTile(home, tiles.getTileLocation(40, 43))
for (let index = 0; index < 100; index++) {
    power = sprites.create(img`
            ....................
            ....................
            ....................
            ....................
            ....................
            ....................
            .......22...22......
            ......2322.2222.....
            ......232222222.....
            ......222222222.....
            .......22222b2......
            ........222b2.......
            .........222........
            ..........2.........
            ....................
            ....................
            ....................
            ....................
            ....................
            ....................
            `, SpriteKind.Fuel)
	tiles.placeOnRandomTile(power, sprites.castle.tileGrass1)
}

sprites.onOverlap(SpriteKind.Player, SpriteKind.Fuel, function (sprite, otherSprite) {
info.changeScoreBy(1)
})

```




## Removing sprites
We also need to remove the Fuel-sprite when we get points. To ensure we only remove the one we're touchhing, we need to do two things.

First, find a ``||sprites:destroy mySprite||``-block and put it under the ``||info:change score||``-block.
Then you need to **click and drag** the red ``||variables:otherSprite||``-oval out of the border in the ``||sprites:overlap||``-block, and put it in instead of ``||variables:mySprite||`` in the ``||sprites:Destroy||``-block.

(*This step is a little tricky, ask the friendly guide in the green shirt if you need help.*)




```blocks
namespace SpriteKind {
    export const Fuel = SpriteKind.create()
    export const Goal = SpriteKind.create()
}

scene.setBackgroundColor(9)
let mySprite = sprites.create(img`
    . . . . . . . . . . . . . . . . 
    . . . . 1 1 1 1 1 1 1 1 . . . . 
    . . . 1 b 1 1 1 1 1 1 6 1 . . . 
    . . 1 6 b 1 1 1 1 1 1 6 6 1 . . 
    . 1 6 6 b b b b b b 1 6 6 9 1 . 
    . 1 6 1 d d d d d d d b 6 9 1 1 
    . 1 1 b 6 6 d 6 6 6 d d 9 9 1 1 
    . 1 d 6 6 6 d 6 6 6 6 d 1 1 1 1 
    . d d 9 9 9 d 9 9 9 9 9 d 1 1 1 
    . d d d d d d c d d d c d 1 5 5 
    . d d d d d d c d d c d d d 1 5 
    . d d d d d d c c c d d d d d d 
    . d f f f f d d d d f f f d d d 
    . . f f f f f d d f f f f f d . 
    . . . f f f . . . . f f f f . . 
    . . . . . . . . . . . . . . . . 
    `, SpriteKind.Player)
controller.moveSprite(mySprite)
tiles.setCurrentTilemap(tilemap`approximation of western Norway`)

scene.cameraFollowSprite(mySprite)
let home = sprites.create(img`
    ....................e2e22e2e....................
    .................222eee22e2e222.................
    ..............222e22e2e22eee22e222..............
    ...........e22e22eeee2e22e2eeee22e22e...........
    ........eeee22e22e22e2e22e2e22e22e22eeee........
    .....222e22e22eeee22e2e22e2e22eeee22e22e222.....
    ...22eeee22e22e22e22eee22eee22e22e22e22eeee22...
    4cc22e22e22eeee22e22e2e22e2e22e22eeee22e22e22cc4
    6c6eee22e22e22e22e22e2e22e2e22e22e22e22e22eee6c6
    46622e22eeee22e22eeee2e22e2eeee22e22eeee22e22664
    46622e22e22e22eeee22e2e22e2e22eeee22e22e22e22664
    4cc22eeee22e22e22e22eee22eee22e22e22e22eeee22cc4
    6c622e22e22eeee22e22e2e22e2e22e22eeee22e22e226c6
    466eee22e22e22e22e22e2e22e2e22e22e22e22e22eee664
    46622e22eeee22e22e22e2e22e2e22e22e22eeee22e22664
    4cc22e22e22e22e22eeee2e22e2eeee22e22e22e22e22cc4
    6c622eeee22e22eeee22eee22eee22eeee22e22eeee226c6
    46622e22e22eeee22e22e2e22e2e22e22eeee22e22e22664
    466eee22e22e22e22e22e2e22e2e22e22e22e22e22eee664
    4cc22e22eeee22e22e22e2e22e2e22e22e22eeee22e22cc4
    6c622e22e22e22e22e22eee22eee22e22e22e22e22e226c6
    46622eeee22e22e22eeecc6666cceee22e22e22eeee22664
    46622e22e22e22eeecc6666666666cceee22e22e22e22664
    4cceee22e22eeecc66666cccccc66666cceee22e22eeecc4
    6c622e22eeecc66666cc64444446cc66666cceee22e226c6
    46622e22cc66666cc64444444444446cc66666cc22e22664
    46622cc6666ccc64444444444444444446ccc6666cc22664
    4ccc6666ccc6444bcc666666666666ccb4446ccc6666ccc4
    cccccccc6666666cb44444444444444bc6666666cccccccc
    64444444444446c444444444444444444c64444444444446
    66cb444444444cb411111111111111114bc444444444bc66
    666cccccccccccd166666666666666661dccccccccccc666
    6666444444444c116eeeeeeeeeeeeee611c4444444446666
    666e2222222e4c16e4e44e44e44e44ee61c4e2222222e666
    666eeeeeeeee4c16e4e44e44e44e44ee61c4eeeeeeeee666
    666eddddddde4c66f4e4effffffe44ee66c4eddddddde666
    666edffdffde4c66f4effffffffff4ee66c4edffdffde666
    666edccdccde4c66f4effffffffffeee66c4edccdccde666
    666eddddddde4c66f4eeeeeeeeeeeeee66c4eddddddde666
    c66edffdffde4c66e4e44e44e44e44ee66c4edffdffde66c
    c66edccdccde4c66e4e44e44e44e44ee66c4edccdccde66c
    cc66666666664c66e4e44e44e44feeee66c46666666666cc
    .c66444444444c66e4e44e44e44ffffe66c44444444466c.
    ..c64eee4eee4c66f4e44e44e44f44fe66c4eee4eee46c..
    ...c4eee4eee4c66f4e44e44e44effee66c4eee4eee4c...
    ....644444444c66f4e44e44e44e44ee66c444444446....
    .....64eee444c66f4e44e44e44e44ee66c444eee46.....
    ......6ccc666c66e4e44e44e44e44ee66c666ccc6......
    `, SpriteKind.Goal)

tiles.placeOnRandomTile(mySprite, sprites.castle.tileGrass1)

tiles.placeOnTile(home, tiles.getTileLocation(40, 43))
for (let index = 0; index < 100; index++) {
    power = sprites.create(img`
            ....................
            ....................
            ....................
            ....................
            ....................
            ....................
            .......22...22......
            ......2322.2222.....
            ......232222222.....
            ......222222222.....
            .......22222b2......
            ........222b2.......
            .........222........
            ..........2.........
            ....................
            ....................
            ....................
            ....................
            ....................
            ....................
            `, SpriteKind.Fuel)
	tiles.placeOnRandomTile(power, sprites.castle.tileGrass1)
}

sprites.onOverlap(SpriteKind.Player, SpriteKind.Fuel, function (sprite, otherSprite) {
info.changeScoreBy(1)
sprites.destroy(otherSprite)
})

```


## A way to win the game 
Now we'll add a rule that lets you win the game when you get home.

Make a new ``||sprites:overlap||``-block, and set it to trigger when you touch a **Goal**-sprite.

Inside this block, add a ``||game:game over: WIN||``-block.


```blocks
namespace SpriteKind {
    export const Fuel = SpriteKind.create()
    export const Goal = SpriteKind.create()
}

scene.setBackgroundColor(9)
let mySprite = sprites.create(img`
    . . . . . . . . . . . . . . . . 
    . . . . 1 1 1 1 1 1 1 1 . . . . 
    . . . 1 b 1 1 1 1 1 1 6 1 . . . 
    . . 1 6 b 1 1 1 1 1 1 6 6 1 . . 
    . 1 6 6 b b b b b b 1 6 6 9 1 . 
    . 1 6 1 d d d d d d d b 6 9 1 1 
    . 1 1 b 6 6 d 6 6 6 d d 9 9 1 1 
    . 1 d 6 6 6 d 6 6 6 6 d 1 1 1 1 
    . d d 9 9 9 d 9 9 9 9 9 d 1 1 1 
    . d d d d d d c d d d c d 1 5 5 
    . d d d d d d c d d c d d d 1 5 
    . d d d d d d c c c d d d d d d 
    . d f f f f d d d d f f f d d d 
    . . f f f f f d d f f f f f d . 
    . . . f f f . . . . f f f f . . 
    . . . . . . . . . . . . . . . . 
    `, SpriteKind.Player)
controller.moveSprite(mySprite)
tiles.setCurrentTilemap(tilemap`approximation of western Norway`)

scene.cameraFollowSprite(mySprite)
let home = sprites.create(img`
    ....................e2e22e2e....................
    .................222eee22e2e222.................
    ..............222e22e2e22eee22e222..............
    ...........e22e22eeee2e22e2eeee22e22e...........
    ........eeee22e22e22e2e22e2e22e22e22eeee........
    .....222e22e22eeee22e2e22e2e22eeee22e22e222.....
    ...22eeee22e22e22e22eee22eee22e22e22e22eeee22...
    4cc22e22e22eeee22e22e2e22e2e22e22eeee22e22e22cc4
    6c6eee22e22e22e22e22e2e22e2e22e22e22e22e22eee6c6
    46622e22eeee22e22eeee2e22e2eeee22e22eeee22e22664
    46622e22e22e22eeee22e2e22e2e22eeee22e22e22e22664
    4cc22eeee22e22e22e22eee22eee22e22e22e22eeee22cc4
    6c622e22e22eeee22e22e2e22e2e22e22eeee22e22e226c6
    466eee22e22e22e22e22e2e22e2e22e22e22e22e22eee664
    46622e22eeee22e22e22e2e22e2e22e22e22eeee22e22664
    4cc22e22e22e22e22eeee2e22e2eeee22e22e22e22e22cc4
    6c622eeee22e22eeee22eee22eee22eeee22e22eeee226c6
    46622e22e22eeee22e22e2e22e2e22e22eeee22e22e22664
    466eee22e22e22e22e22e2e22e2e22e22e22e22e22eee664
    4cc22e22eeee22e22e22e2e22e2e22e22e22eeee22e22cc4
    6c622e22e22e22e22e22eee22eee22e22e22e22e22e226c6
    46622eeee22e22e22eeecc6666cceee22e22e22eeee22664
    46622e22e22e22eeecc6666666666cceee22e22e22e22664
    4cceee22e22eeecc66666cccccc66666cceee22e22eeecc4
    6c622e22eeecc66666cc64444446cc66666cceee22e226c6
    46622e22cc66666cc64444444444446cc66666cc22e22664
    46622cc6666ccc64444444444444444446ccc6666cc22664
    4ccc6666ccc6444bcc666666666666ccb4446ccc6666ccc4
    cccccccc6666666cb44444444444444bc6666666cccccccc
    64444444444446c444444444444444444c64444444444446
    66cb444444444cb411111111111111114bc444444444bc66
    666cccccccccccd166666666666666661dccccccccccc666
    6666444444444c116eeeeeeeeeeeeee611c4444444446666
    666e2222222e4c16e4e44e44e44e44ee61c4e2222222e666
    666eeeeeeeee4c16e4e44e44e44e44ee61c4eeeeeeeee666
    666eddddddde4c66f4e4effffffe44ee66c4eddddddde666
    666edffdffde4c66f4effffffffff4ee66c4edffdffde666
    666edccdccde4c66f4effffffffffeee66c4edccdccde666
    666eddddddde4c66f4eeeeeeeeeeeeee66c4eddddddde666
    c66edffdffde4c66e4e44e44e44e44ee66c4edffdffde66c
    c66edccdccde4c66e4e44e44e44e44ee66c4edccdccde66c
    cc66666666664c66e4e44e44e44feeee66c46666666666cc
    .c66444444444c66e4e44e44e44ffffe66c44444444466c.
    ..c64eee4eee4c66f4e44e44e44f44fe66c4eee4eee46c..
    ...c4eee4eee4c66f4e44e44e44effee66c4eee4eee4c...
    ....644444444c66f4e44e44e44e44ee66c444444446....
    .....64eee444c66f4e44e44e44e44ee66c444eee46.....
    ......6ccc666c66e4e44e44e44e44ee66c666ccc6......
    `, SpriteKind.Goal)

tiles.placeOnRandomTile(mySprite, sprites.castle.tileGrass1)

tiles.placeOnTile(home, tiles.getTileLocation(40, 43))
for (let index = 0; index < 100; index++) {
    power = sprites.create(img`
            ....................
            ....................
            ....................
            ....................
            ....................
            ....................
            .......22...22......
            ......2322.2222.....
            ......232222222.....
            ......222222222.....
            .......22222b2......
            ........222b2.......
            .........222........
            ..........2.........
            ....................
            ....................
            ....................
            ....................
            ....................
            ....................
            `, SpriteKind.Fuel)
	tiles.placeOnRandomTile(power, sprites.castle.tileGrass1)
}

sprites.onOverlap(SpriteKind.Player, SpriteKind.Fuel, function (sprite, otherSprite) {
info.changeScoreBy(1)
sprites.destroy(otherSprite)
})

sprites.onOverlap(SpriteKind.Player, SpriteKind.Goal, function (sprite, otherSprite) {
    game.gameOver(true)
})




```





## A way to lose - part 1
The game will be very boring if there's no way to *lose*.

Add a ``||info:set life to 3||`` block in ``||loops:on start||``, and set it to start with 100 lives.

The 100 lives symbolizes the fuel tank. In the next step, we'll make it so that the tank gradually runs out.


```blocks
namespace SpriteKind {
    export const Fuel = SpriteKind.create()
    export const Goal = SpriteKind.create()
}

scene.setBackgroundColor(9)
let mySprite = sprites.create(img`
    . . . . . . . . . . . . . . . . 
    . . . . 1 1 1 1 1 1 1 1 . . . . 
    . . . 1 b 1 1 1 1 1 1 6 1 . . . 
    . . 1 6 b 1 1 1 1 1 1 6 6 1 . . 
    . 1 6 6 b b b b b b 1 6 6 9 1 . 
    . 1 6 1 d d d d d d d b 6 9 1 1 
    . 1 1 b 6 6 d 6 6 6 d d 9 9 1 1 
    . 1 d 6 6 6 d 6 6 6 6 d 1 1 1 1 
    . d d 9 9 9 d 9 9 9 9 9 d 1 1 1 
    . d d d d d d c d d d c d 1 5 5 
    . d d d d d d c d d c d d d 1 5 
    . d d d d d d c c c d d d d d d 
    . d f f f f d d d d f f f d d d 
    . . f f f f f d d f f f f f d . 
    . . . f f f . . . . f f f f . . 
    . . . . . . . . . . . . . . . . 
    `, SpriteKind.Player)
controller.moveSprite(mySprite)
tiles.setCurrentTilemap(tilemap`approximation of western Norway`)

scene.cameraFollowSprite(mySprite)
let home = sprites.create(img`
    ....................e2e22e2e....................
    .................222eee22e2e222.................
    ..............222e22e2e22eee22e222..............
    ...........e22e22eeee2e22e2eeee22e22e...........
    ........eeee22e22e22e2e22e2e22e22e22eeee........
    .....222e22e22eeee22e2e22e2e22eeee22e22e222.....
    ...22eeee22e22e22e22eee22eee22e22e22e22eeee22...
    4cc22e22e22eeee22e22e2e22e2e22e22eeee22e22e22cc4
    6c6eee22e22e22e22e22e2e22e2e22e22e22e22e22eee6c6
    46622e22eeee22e22eeee2e22e2eeee22e22eeee22e22664
    46622e22e22e22eeee22e2e22e2e22eeee22e22e22e22664
    4cc22eeee22e22e22e22eee22eee22e22e22e22eeee22cc4
    6c622e22e22eeee22e22e2e22e2e22e22eeee22e22e226c6
    466eee22e22e22e22e22e2e22e2e22e22e22e22e22eee664
    46622e22eeee22e22e22e2e22e2e22e22e22eeee22e22664
    4cc22e22e22e22e22eeee2e22e2eeee22e22e22e22e22cc4
    6c622eeee22e22eeee22eee22eee22eeee22e22eeee226c6
    46622e22e22eeee22e22e2e22e2e22e22eeee22e22e22664
    466eee22e22e22e22e22e2e22e2e22e22e22e22e22eee664
    4cc22e22eeee22e22e22e2e22e2e22e22e22eeee22e22cc4
    6c622e22e22e22e22e22eee22eee22e22e22e22e22e226c6
    46622eeee22e22e22eeecc6666cceee22e22e22eeee22664
    46622e22e22e22eeecc6666666666cceee22e22e22e22664
    4cceee22e22eeecc66666cccccc66666cceee22e22eeecc4
    6c622e22eeecc66666cc64444446cc66666cceee22e226c6
    46622e22cc66666cc64444444444446cc66666cc22e22664
    46622cc6666ccc64444444444444444446ccc6666cc22664
    4ccc6666ccc6444bcc666666666666ccb4446ccc6666ccc4
    cccccccc6666666cb44444444444444bc6666666cccccccc
    64444444444446c444444444444444444c64444444444446
    66cb444444444cb411111111111111114bc444444444bc66
    666cccccccccccd166666666666666661dccccccccccc666
    6666444444444c116eeeeeeeeeeeeee611c4444444446666
    666e2222222e4c16e4e44e44e44e44ee61c4e2222222e666
    666eeeeeeeee4c16e4e44e44e44e44ee61c4eeeeeeeee666
    666eddddddde4c66f4e4effffffe44ee66c4eddddddde666
    666edffdffde4c66f4effffffffff4ee66c4edffdffde666
    666edccdccde4c66f4effffffffffeee66c4edccdccde666
    666eddddddde4c66f4eeeeeeeeeeeeee66c4eddddddde666
    c66edffdffde4c66e4e44e44e44e44ee66c4edffdffde66c
    c66edccdccde4c66e4e44e44e44e44ee66c4edccdccde66c
    cc66666666664c66e4e44e44e44feeee66c46666666666cc
    .c66444444444c66e4e44e44e44ffffe66c44444444466c.
    ..c64eee4eee4c66f4e44e44e44f44fe66c4eee4eee46c..
    ...c4eee4eee4c66f4e44e44e44effee66c4eee4eee4c...
    ....644444444c66f4e44e44e44e44ee66c444444446....
    .....64eee444c66f4e44e44e44e44ee66c444eee46.....
    ......6ccc666c66e4e44e44e44e44ee66c666ccc6......
    `, SpriteKind.Goal)

tiles.placeOnRandomTile(mySprite, sprites.castle.tileGrass1)

tiles.placeOnTile(home, tiles.getTileLocation(40, 43))
for (let index = 0; index < 100; index++) {
    power = sprites.create(img`
            ....................
            ....................
            ....................
            ....................
            ....................
            ....................
            .......22...22......
            ......2322.2222.....
            ......232222222.....
            ......222222222.....
            .......22222b2......
            ........222b2.......
            .........222........
            ..........2.........
            ....................
            ....................
            ....................
            ....................
            ....................
            ....................
            `, SpriteKind.Fuel)
	tiles.placeOnRandomTile(power, sprites.castle.tileGrass1)
}

info.setLife(100)


```





## A way to lose - part 2
Grab a ``||game:on game update every 500ms||``-block and put it wherever you like. Click on 500 and choose a bigger number, i.e 1 or 5 seconds(*1000 or 5000 milliseconds*)

Put a ``||info:change life by -1||``-block inside this block, and the game will gradually count down from full tank to 0.

Test out different numbers in the update-block if it's too hard or too easy to get home before the tank runs out.


```blocks
namespace SpriteKind {
    export const Fuel = SpriteKind.create()
    export const Goal = SpriteKind.create()
}

scene.setBackgroundColor(9)
let mySprite = sprites.create(img`
    . . . . . . . . . . . . . . . . 
    . . . . 1 1 1 1 1 1 1 1 . . . . 
    . . . 1 b 1 1 1 1 1 1 6 1 . . . 
    . . 1 6 b 1 1 1 1 1 1 6 6 1 . . 
    . 1 6 6 b b b b b b 1 6 6 9 1 . 
    . 1 6 1 d d d d d d d b 6 9 1 1 
    . 1 1 b 6 6 d 6 6 6 d d 9 9 1 1 
    . 1 d 6 6 6 d 6 6 6 6 d 1 1 1 1 
    . d d 9 9 9 d 9 9 9 9 9 d 1 1 1 
    . d d d d d d c d d d c d 1 5 5 
    . d d d d d d c d d c d d d 1 5 
    . d d d d d d c c c d d d d d d 
    . d f f f f d d d d f f f d d d 
    . . f f f f f d d f f f f f d . 
    . . . f f f . . . . f f f f . . 
    . . . . . . . . . . . . . . . . 
    `, SpriteKind.Player)
controller.moveSprite(mySprite)
tiles.setCurrentTilemap(tilemap`approximation of western Norway`)

scene.cameraFollowSprite(mySprite)
let home = sprites.create(img`
    ....................e2e22e2e....................
    .................222eee22e2e222.................
    ..............222e22e2e22eee22e222..............
    ...........e22e22eeee2e22e2eeee22e22e...........
    ........eeee22e22e22e2e22e2e22e22e22eeee........
    .....222e22e22eeee22e2e22e2e22eeee22e22e222.....
    ...22eeee22e22e22e22eee22eee22e22e22e22eeee22...
    4cc22e22e22eeee22e22e2e22e2e22e22eeee22e22e22cc4
    6c6eee22e22e22e22e22e2e22e2e22e22e22e22e22eee6c6
    46622e22eeee22e22eeee2e22e2eeee22e22eeee22e22664
    46622e22e22e22eeee22e2e22e2e22eeee22e22e22e22664
    4cc22eeee22e22e22e22eee22eee22e22e22e22eeee22cc4
    6c622e22e22eeee22e22e2e22e2e22e22eeee22e22e226c6
    466eee22e22e22e22e22e2e22e2e22e22e22e22e22eee664
    46622e22eeee22e22e22e2e22e2e22e22e22eeee22e22664
    4cc22e22e22e22e22eeee2e22e2eeee22e22e22e22e22cc4
    6c622eeee22e22eeee22eee22eee22eeee22e22eeee226c6
    46622e22e22eeee22e22e2e22e2e22e22eeee22e22e22664
    466eee22e22e22e22e22e2e22e2e22e22e22e22e22eee664
    4cc22e22eeee22e22e22e2e22e2e22e22e22eeee22e22cc4
    6c622e22e22e22e22e22eee22eee22e22e22e22e22e226c6
    46622eeee22e22e22eeecc6666cceee22e22e22eeee22664
    46622e22e22e22eeecc6666666666cceee22e22e22e22664
    4cceee22e22eeecc66666cccccc66666cceee22e22eeecc4
    6c622e22eeecc66666cc64444446cc66666cceee22e226c6
    46622e22cc66666cc64444444444446cc66666cc22e22664
    46622cc6666ccc64444444444444444446ccc6666cc22664
    4ccc6666ccc6444bcc666666666666ccb4446ccc6666ccc4
    cccccccc6666666cb44444444444444bc6666666cccccccc
    64444444444446c444444444444444444c64444444444446
    66cb444444444cb411111111111111114bc444444444bc66
    666cccccccccccd166666666666666661dccccccccccc666
    6666444444444c116eeeeeeeeeeeeee611c4444444446666
    666e2222222e4c16e4e44e44e44e44ee61c4e2222222e666
    666eeeeeeeee4c16e4e44e44e44e44ee61c4eeeeeeeee666
    666eddddddde4c66f4e4effffffe44ee66c4eddddddde666
    666edffdffde4c66f4effffffffff4ee66c4edffdffde666
    666edccdccde4c66f4effffffffffeee66c4edccdccde666
    666eddddddde4c66f4eeeeeeeeeeeeee66c4eddddddde666
    c66edffdffde4c66e4e44e44e44e44ee66c4edffdffde66c
    c66edccdccde4c66e4e44e44e44e44ee66c4edccdccde66c
    cc66666666664c66e4e44e44e44feeee66c46666666666cc
    .c66444444444c66e4e44e44e44ffffe66c44444444466c.
    ..c64eee4eee4c66f4e44e44e44f44fe66c4eee4eee46c..
    ...c4eee4eee4c66f4e44e44e44effee66c4eee4eee4c...
    ....644444444c66f4e44e44e44e44ee66c444444446....
    .....64eee444c66f4e44e44e44e44ee66c444eee46.....
    ......6ccc666c66e4e44e44e44e44ee66c666ccc6......
    `, SpriteKind.Goal)

tiles.placeOnRandomTile(mySprite, sprites.castle.tileGrass1)

tiles.placeOnTile(home, tiles.getTileLocation(40, 43))
for (let index = 0; index < 100; index++) {
    power = sprites.create(img`
            ....................
            ....................
            ....................
            ....................
            ....................
            ....................
            .......22...22......
            ......2322.2222.....
            ......232222222.....
            ......222222222.....
            .......22222b2......
            ........222b2.......
            .........222........
            ..........2.........
            ....................
            ....................
            ....................
            ....................
            ....................
            ....................
            `, SpriteKind.Fuel)
	tiles.placeOnRandomTile(power, sprites.castle.tileGrass1)
}

info.setLife(100)

game.onUpdateInterval(5000, function () {
    info.changeLifeBy(-1)
})



```































































```template

namespace SpriteKind {
    export const Fuel = SpriteKind.create()
    export const Goal = SpriteKind.create()
}

scene.setBackgroundColor(9)
let mySprite = sprites.create(img`
    . . . . . . . . . . . . . . . . 
    . . . . 1 1 1 1 1 1 1 1 . . . . 
    . . . 1 b 1 1 1 1 1 1 6 1 . . . 
    . . 1 6 b 1 1 1 1 1 1 6 6 1 . . 
    . 1 6 6 b b b b b b 1 6 6 9 1 . 
    . 1 6 1 d d d d d d d b 6 9 1 1 
    . 1 1 b 6 6 d 6 6 6 d d 9 9 1 1 
    . 1 d 6 6 6 d 6 6 6 6 d 1 1 1 1 
    . d d 9 9 9 d 9 9 9 9 9 d 1 1 1 
    . d d d d d d c d d d c d 1 5 5 
    . d d d d d d c d d c d d d 1 5 
    . d d d d d d c c c d d d d d d 
    . d f f f f d d d d f f f d d d 
    . . f f f f f d d f f f f f d . 
    . . . f f f . . . . f f f f . . 
    . . . . . . . . . . . . . . . . 
    `, SpriteKind.Player)
controller.moveSprite(mySprite)
tiles.setCurrentTilemap(tilemap`approximation of western Norway`)

scene.cameraFollowSprite(mySprite)
let home = sprites.create(img`
    ....................e2e22e2e....................
    .................222eee22e2e222.................
    ..............222e22e2e22eee22e222..............
    ...........e22e22eeee2e22e2eeee22e22e...........
    ........eeee22e22e22e2e22e2e22e22e22eeee........
    .....222e22e22eeee22e2e22e2e22eeee22e22e222.....
    ...22eeee22e22e22e22eee22eee22e22e22e22eeee22...
    4cc22e22e22eeee22e22e2e22e2e22e22eeee22e22e22cc4
    6c6eee22e22e22e22e22e2e22e2e22e22e22e22e22eee6c6
    46622e22eeee22e22eeee2e22e2eeee22e22eeee22e22664
    46622e22e22e22eeee22e2e22e2e22eeee22e22e22e22664
    4cc22eeee22e22e22e22eee22eee22e22e22e22eeee22cc4
    6c622e22e22eeee22e22e2e22e2e22e22eeee22e22e226c6
    466eee22e22e22e22e22e2e22e2e22e22e22e22e22eee664
    46622e22eeee22e22e22e2e22e2e22e22e22eeee22e22664
    4cc22e22e22e22e22eeee2e22e2eeee22e22e22e22e22cc4
    6c622eeee22e22eeee22eee22eee22eeee22e22eeee226c6
    46622e22e22eeee22e22e2e22e2e22e22eeee22e22e22664
    466eee22e22e22e22e22e2e22e2e22e22e22e22e22eee664
    4cc22e22eeee22e22e22e2e22e2e22e22e22eeee22e22cc4
    6c622e22e22e22e22e22eee22eee22e22e22e22e22e226c6
    46622eeee22e22e22eeecc6666cceee22e22e22eeee22664
    46622e22e22e22eeecc6666666666cceee22e22e22e22664
    4cceee22e22eeecc66666cccccc66666cceee22e22eeecc4
    6c622e22eeecc66666cc64444446cc66666cceee22e226c6
    46622e22cc66666cc64444444444446cc66666cc22e22664
    46622cc6666ccc64444444444444444446ccc6666cc22664
    4ccc6666ccc6444bcc666666666666ccb4446ccc6666ccc4
    cccccccc6666666cb44444444444444bc6666666cccccccc
    64444444444446c444444444444444444c64444444444446
    66cb444444444cb411111111111111114bc444444444bc66
    666cccccccccccd166666666666666661dccccccccccc666
    6666444444444c116eeeeeeeeeeeeee611c4444444446666
    666e2222222e4c16e4e44e44e44e44ee61c4e2222222e666
    666eeeeeeeee4c16e4e44e44e44e44ee61c4eeeeeeeee666
    666eddddddde4c66f4e4effffffe44ee66c4eddddddde666
    666edffdffde4c66f4effffffffff4ee66c4edffdffde666
    666edccdccde4c66f4effffffffffeee66c4edccdccde666
    666eddddddde4c66f4eeeeeeeeeeeeee66c4eddddddde666
    c66edffdffde4c66e4e44e44e44e44ee66c4edffdffde66c
    c66edccdccde4c66e4e44e44e44e44ee66c4edccdccde66c
    cc66666666664c66e4e44e44e44feeee66c46666666666cc
    .c66444444444c66e4e44e44e44ffffe66c44444444466c.
    ..c64eee4eee4c66f4e44e44e44f44fe66c4eee4eee46c..
    ...c4eee4eee4c66f4e44e44e44effee66c4eee4eee4c...
    ....644444444c66f4e44e44e44e44ee66c444444446....
    .....64eee444c66f4e44e44e44e44ee66c444eee46.....
    ......6ccc666c66e4e44e44e44e44ee66c666ccc6......
    `, SpriteKind.Goal)








```

## Finished!
Good job! When you click the Done-button underneath here, you can generate a QR-code you can scan with your phone, so that you can keep playing and programming on your game after you leave.

If you want, you're free to keep building the game and adding more functions and rules. Take a look a the demo on our home page for some ideas.







```assetjson

{
  "README.md": " ",
  "assets.json": "",
  "main.blocks": "<xml xmlns=\"https://developers.google.com/blockly/xml\"><variables><variable type=\"KIND_SpriteKind\" id=\"6h6yRO9gGTE!/.Wt-O^c\">Player</variable><variable type=\"KIND_SpriteKind\" id=\",?--7df-hyngkFSBpHcg\">Projectile</variable><variable type=\"KIND_SpriteKind\" id=\"(e}E{XvO-%OE-eqO@.]s\">Food</variable><variable type=\"KIND_SpriteKind\" id=\"P{$)o6O_CgX/jyE?5Za[\">Enemy</variable><variable type=\"KIND_SpriteKind\" id=\",wY)^i(x|q1)`t]R5I6O\">Fuel</variable><variable type=\"KIND_SpriteKind\" id=\"uVS(ferxo|FJ}(:H|aU(\">Goal</variable><variable id=\"wcyJn*eeJmM+SEL|CmMD\">power</variable><variable id=\"du?,~:Ix%pITsV4BlPH+\">home</variable><variable id=\"TelHPe9{DfLa[knNvE01\">mySprite</variable></variables><block type=\"pxt-on-start\" x=\"0\" y=\"0\"><statement name=\"HANDLER\"><block type=\"gamesetbackgroundcolor\"><value name=\"color\"><shadow type=\"colorindexpicker\"><field name=\"index\">9</field></shadow></value><next><block type=\"set_current_tilemap\"><value name=\"tilemap\"><shadow type=\"tiles_tilemap_editor\"><field name=\"tilemap\">tilemap`approximation of western Norway`</field><data>{\"commentRefs\":[],\"fieldData\":{\"tilemap\":\"level1\"}}</data></shadow></value><next><block type=\"variables_set\"><field name=\"VAR\" id=\"TelHPe9{DfLa[knNvE01\">mySprite</field><value name=\"VALUE\"><shadow xmlns=\"http://www.w3.org/1999/xhtml\" type=\"math_number\"><field name=\"NUM\">0</field></shadow><block type=\"spritescreate\"><value name=\"img\"><shadow type=\"screen_image_picker\"><field name=\"img\">img`\n. . . . . . . . . . . . . . . . \n. . . . 1 1 1 1 1 1 1 1 . . . . \n. . . 1 b 1 1 1 1 1 1 6 1 . . . \n. . 1 6 b 1 1 1 1 1 1 6 6 1 . . \n. 1 6 6 b b b b b b 1 6 6 9 1 . \n. 1 6 1 d d d d d d d b 6 9 1 1 \n. 1 1 b 6 6 d 6 6 6 d d 9 9 1 1 \n. 1 d 6 6 6 d 6 6 6 6 d 1 1 1 1 \n. d d 9 9 9 d 9 9 9 9 9 d 1 1 1 \n. d d d d d d c d d d c d 1 5 5 \n. d d d d d d c d d c d d d 1 5 \n. d d d d d d c c c d d d d d d \n. d f f f f d d d d f f f d d d \n. . f f f f f d d f f f f f d . \n. . . f f f . . . . f f f f . . \n. . . . . . . . . . . . . . . . \n`</field><data>{\"commentRefs\":[],\"fieldData\":{\"img\":null}}</data></shadow></value><value name=\"kind\"><shadow type=\"spritekind\"><field name=\"MEMBER\">Player</field></shadow></value></block></value><next><block type=\"game_control_sprite\"><mutation xmlns=\"http://www.w3.org/1999/xhtml\" _expanded=\"0\" _input_init=\"true\"></mutation><value name=\"sprite\"><block type=\"variables_get\"><field name=\"VAR\" id=\"TelHPe9{DfLa[knNvE01\">mySprite</field></block></value><value name=\"vx\"><shadow type=\"spriteSpeedPicker\"><field name=\"speed\">100</field></shadow></value><value name=\"vy\"><shadow type=\"spriteSpeedPicker\"><field name=\"speed\">100</field></shadow></value><next><block type=\"camerafollow\"><value name=\"sprite\"><block type=\"variables_get\"><field name=\"VAR\" id=\"TelHPe9{DfLa[knNvE01\">mySprite</field></block></value><next><block type=\"variables_set\"><field name=\"VAR\" id=\"wcyJn*eeJmM+SEL|CmMD\">power</field><value name=\"VALUE\"><shadow xmlns=\"http://www.w3.org/1999/xhtml\" type=\"math_number\"><field name=\"NUM\">0</field></shadow><block type=\"spritescreate\"><value name=\"img\"><shadow type=\"screen_image_picker\"><field name=\"img\">img`\n....................\n....................\n....................\n....................\n....................\n....................\n.......22...22......\n......2322.2222.....\n......232222222.....\n......222222222.....\n.......22222b2......\n........222b2.......\n.........222........\n..........2.........\n....................\n....................\n....................\n....................\n....................\n....................\n`</field><data>{\"commentRefs\":[],\"fieldData\":{\"img\":null}}</data></shadow></value><value name=\"kind\"><shadow type=\"spritekind\"><field name=\"MEMBER\">Fuel</field></shadow></value></block></value><next><block type=\"variables_set\"><field name=\"VAR\" id=\"du?,~:Ix%pITsV4BlPH+\">home</field><value name=\"VALUE\"><shadow xmlns=\"http://www.w3.org/1999/xhtml\" type=\"math_number\"><field name=\"NUM\">0</field></shadow><block type=\"spritescreate\"><value name=\"img\"><shadow type=\"screen_image_picker\"><field name=\"img\">img`\n....................e2e22e2e....................\n.................222eee22e2e222.................\n..............222e22e2e22eee22e222..............\n...........e22e22eeee2e22e2eeee22e22e...........\n........eeee22e22e22e2e22e2e22e22e22eeee........\n.....222e22e22eeee22e2e22e2e22eeee22e22e222.....\n...22eeee22e22e22e22eee22eee22e22e22e22eeee22...\n4cc22e22e22eeee22e22e2e22e2e22e22eeee22e22e22cc4\n6c6eee22e22e22e22e22e2e22e2e22e22e22e22e22eee6c6\n46622e22eeee22e22eeee2e22e2eeee22e22eeee22e22664\n46622e22e22e22eeee22e2e22e2e22eeee22e22e22e22664\n4cc22eeee22e22e22e22eee22eee22e22e22e22eeee22cc4\n6c622e22e22eeee22e22e2e22e2e22e22eeee22e22e226c6\n466eee22e22e22e22e22e2e22e2e22e22e22e22e22eee664\n46622e22eeee22e22e22e2e22e2e22e22e22eeee22e22664\n4cc22e22e22e22e22eeee2e22e2eeee22e22e22e22e22cc4\n6c622eeee22e22eeee22eee22eee22eeee22e22eeee226c6\n46622e22e22eeee22e22e2e22e2e22e22eeee22e22e22664\n466eee22e22e22e22e22e2e22e2e22e22e22e22e22eee664\n4cc22e22eeee22e22e22e2e22e2e22e22e22eeee22e22cc4\n6c622e22e22e22e22e22eee22eee22e22e22e22e22e226c6\n46622eeee22e22e22eeecc6666cceee22e22e22eeee22664\n46622e22e22e22eeecc6666666666cceee22e22e22e22664\n4cceee22e22eeecc66666cccccc66666cceee22e22eeecc4\n6c622e22eeecc66666cc64444446cc66666cceee22e226c6\n46622e22cc66666cc64444444444446cc66666cc22e22664\n46622cc6666ccc64444444444444444446ccc6666cc22664\n4ccc6666ccc6444bcc666666666666ccb4446ccc6666ccc4\ncccccccc6666666cb44444444444444bc6666666cccccccc\n64444444444446c444444444444444444c64444444444446\n66cb444444444cb411111111111111114bc444444444bc66\n666cccccccccccd166666666666666661dccccccccccc666\n6666444444444c116eeeeeeeeeeeeee611c4444444446666\n666e2222222e4c16e4e44e44e44e44ee61c4e2222222e666\n666eeeeeeeee4c16e4e44e44e44e44ee61c4eeeeeeeee666\n666eddddddde4c66f4e4effffffe44ee66c4eddddddde666\n666edffdffde4c66f4effffffffff4ee66c4edffdffde666\n666edccdccde4c66f4effffffffffeee66c4edccdccde666\n666eddddddde4c66f4eeeeeeeeeeeeee66c4eddddddde666\nc66edffdffde4c66e4e44e44e44e44ee66c4edffdffde66c\nc66edccdccde4c66e4e44e44e44e44ee66c4edccdccde66c\ncc66666666664c66e4e44e44e44feeee66c46666666666cc\n.c66444444444c66e4e44e44e44ffffe66c44444444466c.\n..c64eee4eee4c66f4e44e44e44f44fe66c4eee4eee46c..\n...c4eee4eee4c66f4e44e44e44effee66c4eee4eee4c...\n....644444444c66f4e44e44e44e44ee66c444444446....\n.....64eee444c66f4e44e44e44e44ee66c444eee46.....\n......6ccc666c66e4e44e44e44e44ee66c666ccc6......\n`</field><data>{\"commentRefs\":[],\"fieldData\":{\"img\":null}}</data></shadow></value><value name=\"kind\"><shadow type=\"spritekind\"><field name=\"MEMBER\">Goal</field></shadow></value></block></value></block></next></block></next></block></next></block></next></block></next></block></next></block></statement></block></xml>",
  "main.ts": "namespace SpriteKind {\n    export const Fuel = SpriteKind.create()\n    export const Goal = SpriteKind.create()\n}\nscene.setBackgroundColor(9)\ntiles.setCurrentTilemap(tilemap`approximation of western Norway`)\nlet mySprite = sprites.create(img`\n    . . . . . . . . . . . . . . . . \n    . . . . 1 1 1 1 1 1 1 1 . . . . \n    . . . 1 b 1 1 1 1 1 1 6 1 . . . \n    . . 1 6 b 1 1 1 1 1 1 6 6 1 . . \n    . 1 6 6 b b b b b b 1 6 6 9 1 . \n    . 1 6 1 d d d d d d d b 6 9 1 1 \n    . 1 1 b 6 6 d 6 6 6 d d 9 9 1 1 \n    . 1 d 6 6 6 d 6 6 6 6 d 1 1 1 1 \n    . d d 9 9 9 d 9 9 9 9 9 d 1 1 1 \n    . d d d d d d c d d d c d 1 5 5 \n    . d d d d d d c d d c d d d 1 5 \n    . d d d d d d c c c d d d d d d \n    . d f f f f d d d d f f f d d d \n    . . f f f f f d d f f f f f d . \n    . . . f f f . . . . f f f f . . \n    . . . . . . . . . . . . . . . . \n    `, SpriteKind.Player)\ncontroller.moveSprite(mySprite)\nscene.cameraFollowSprite(mySprite)\nlet power = sprites.create(img`\n    ....................\n    ....................\n    ....................\n    ....................\n    ....................\n    ....................\n    .......22...22......\n    ......2322.2222.....\n    ......232222222.....\n    ......222222222.....\n    .......22222b2......\n    ........222b2.......\n    .........222........\n    ..........2.........\n    ....................\n    ....................\n    ....................\n    ....................\n    ....................\n    ....................\n    `, SpriteKind.Fuel)\nlet home = sprites.create(img`\n    ....................e2e22e2e....................\n    .................222eee22e2e222.................\n    ..............222e22e2e22eee22e222..............\n    ...........e22e22eeee2e22e2eeee22e22e...........\n    ........eeee22e22e22e2e22e2e22e22e22eeee........\n    .....222e22e22eeee22e2e22e2e22eeee22e22e222.....\n    ...22eeee22e22e22e22eee22eee22e22e22e22eeee22...\n    4cc22e22e22eeee22e22e2e22e2e22e22eeee22e22e22cc4\n    6c6eee22e22e22e22e22e2e22e2e22e22e22e22e22eee6c6\n    46622e22eeee22e22eeee2e22e2eeee22e22eeee22e22664\n    46622e22e22e22eeee22e2e22e2e22eeee22e22e22e22664\n    4cc22eeee22e22e22e22eee22eee22e22e22e22eeee22cc4\n    6c622e22e22eeee22e22e2e22e2e22e22eeee22e22e226c6\n    466eee22e22e22e22e22e2e22e2e22e22e22e22e22eee664\n    46622e22eeee22e22e22e2e22e2e22e22e22eeee22e22664\n    4cc22e22e22e22e22eeee2e22e2eeee22e22e22e22e22cc4\n    6c622eeee22e22eeee22eee22eee22eeee22e22eeee226c6\n    46622e22e22eeee22e22e2e22e2e22e22eeee22e22e22664\n    466eee22e22e22e22e22e2e22e2e22e22e22e22e22eee664\n    4cc22e22eeee22e22e22e2e22e2e22e22e22eeee22e22cc4\n    6c622e22e22e22e22e22eee22eee22e22e22e22e22e226c6\n    46622eeee22e22e22eeecc6666cceee22e22e22eeee22664\n    46622e22e22e22eeecc6666666666cceee22e22e22e22664\n    4cceee22e22eeecc66666cccccc66666cceee22e22eeecc4\n    6c622e22eeecc66666cc64444446cc66666cceee22e226c6\n    46622e22cc66666cc64444444444446cc66666cc22e22664\n    46622cc6666ccc64444444444444444446ccc6666cc22664\n    4ccc6666ccc6444bcc666666666666ccb4446ccc6666ccc4\n    cccccccc6666666cb44444444444444bc6666666cccccccc\n    64444444444446c444444444444444444c64444444444446\n    66cb444444444cb411111111111111114bc444444444bc66\n    666cccccccccccd166666666666666661dccccccccccc666\n    6666444444444c116eeeeeeeeeeeeee611c4444444446666\n    666e2222222e4c16e4e44e44e44e44ee61c4e2222222e666\n    666eeeeeeeee4c16e4e44e44e44e44ee61c4eeeeeeeee666\n    666eddddddde4c66f4e4effffffe44ee66c4eddddddde666\n    666edffdffde4c66f4effffffffff4ee66c4edffdffde666\n    666edccdccde4c66f4effffffffffeee66c4edccdccde666\n    666eddddddde4c66f4eeeeeeeeeeeeee66c4eddddddde666\n    c66edffdffde4c66e4e44e44e44e44ee66c4edffdffde66c\n    c66edccdccde4c66e4e44e44e44e44ee66c4edccdccde66c\n    cc66666666664c66e4e44e44e44feeee66c46666666666cc\n    .c66444444444c66e4e44e44e44ffffe66c44444444466c.\n    ..c64eee4eee4c66f4e44e44e44f44fe66c4eee4eee46c..\n    ...c4eee4eee4c66f4e44e44e44effee66c4eee4eee4c...\n    ....644444444c66f4e44e44e44e44ee66c444444446....\n    .....64eee444c66f4e44e44e44e44ee66c444eee46.....\n    ......6ccc666c66e4e44e44e44e44ee66c666ccc6......\n    `, SpriteKind.Goal)\n",
  "pxt.json": "{\n    \"name\": \"Energy car assets\",\n    \"description\": \"\",\n    \"dependencies\": {\n        \"device\": \"*\"\n    },\n    \"files\": [\n        \"main.blocks\",\n        \"main.ts\",\n        \"README.md\",\n        \"assets.json\",\n        \"tilemap.g.jres\",\n        \"tilemap.g.ts\"\n    ],\n    \"targetVersions\": {\n        \"branch\": \"v1.13.55\",\n        \"tag\": \"v1.13.55\",\n        \"commits\": \"https://github.com/microsoft/pxt-arcade/commits/1b3fc64620f77c6224e58f0d2efa9ce1db21f906\",\n        \"target\": \"1.13.55\",\n        \"pxt\": \"9.3.10\"\n    },\n    \"preferredEditor\": \"blocksprj\"\n}\n",
  "tilemap.g.jres": "{\n    \"transparency16\": {\n        \"data\": \"hwQQABAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA==\",\n        \"mimeType\": \"image/x-mkcd-f4\",\n        \"tilemapTile\": true\n    },\n    \"level1\": {\n        \"id\": \"level1\",\n        \"mimeType\": \"application/mkcd-tilemap\",\n        \"data\": \"MTA0MDAwNDAwMDAwMDAwMTAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAwMDAwMDAwMDAwMDAwMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDAwMDAxMDEwMTAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAxMDAwMDAxMDEwMTAxMDEwMTAzMDMwMzAxMDEwMTAxMDAwMDAwMDAwMDAwMDAwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMDAwMDEwMTAxMDAwMDAwMDAwMDAwMDAwMDAwMDEwMTAxMDEwMTAwMDAwMDAxMDEwMTAxMDEwMTAxMDEwMTAxMDAwMDAwMDAwMDAwMDAwMDAwMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAwMDEwMTAxMDEwMDAwMDAwMDAwMDAwMDAwMDAwMTAxMDEwMTAxMDEwMDAwMDAwMDAwMDEwMTAxMDEwMTAxMDAwMDAwMDAwMTAxMDAwMDAwMDAwMDAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDAwMDAxMDEwMDAwMDAwMDAwMDAwMDAwMDAwMDAxMDEwMTAxMDEwMTAxMDAwMDAwMDAwMDAwMDEwMTAxMDAwMDAwMDAwMTAxMDEwMTAwMDAwMDAwMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAzMDMwMTAzMDEwMTAxMDEwMDAwMDEwMTAwMDAwMDAwMDAwMDAwMDAwMDAxMDEwMTAxMDEwMTAxMDEwMTAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMTAxMDEwMTAxMDEwMDAwMDAwMDAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDMwMTAxMDEwMTAwMDAwMTAxMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDEwMTAxMDEwMTAxMDEwMDAwMDAwMDAwMDAwMDAwMDAwMTAxMDEwMTAxMDEwMTAxMDAwMDAwMDAwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMzAxMDEwMTAxMDAwMDAxMDEwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAxMDEwMTAxMDEwMTAxMDAwMDAwMDAwMDAwMDAwMTAxMDEwMTAxMDEwMTAxMDEwMDAwMDAwMDAwMDEwMTAxMDEwMTAxMDMwMTAxMDEwMTAxMDEwMTAxMDMwMTAxMDEwMDAwMDEwMTAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMTAzMDEwMTAxMDEwMTAxMDAwMDAwMDAwMDAxMDEwMTAxMDEwMTAxMDEwMTAxMDAwMDAwMDAwMTAxMDEwMTAxMDEwMTAzMDEwMTAxMDEwMTAxMDEwMzAxMDEwMTAwMDAwMTAxMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAxMDEwMTAxMDEwMTAxMDEwMTAwMDAwMDAxMDEwMTAzMDMwMTAxMDEwMTAxMDEwMTAwMDAwMDAwMDEwMTAxMDEwMTAxMDEwMzAxMDEwMTAxMDEwMTAxMDEwMTAxMDAwMDAxMDEwMTAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDAwMDAwMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDAwMDAwMDAwMTAxMDEwMTAxMDEwMTAxMDMwMTAxMDEwMTAxMDEwMTAxMDEwMDAwMDAwMTAxMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMDAwMDAwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAwMDAwMDAwMDEwMTAxMDEwMTAxMDEwMTAzMDMwMTAxMDEwMTAxMDEwMTAwMDAwMDAxMDEwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMTAxMDEwMzAzMDEwMTAxMDEwMTAwMDAwMDAxMDEwMTAxMDEwMjAxMDEwMTAxMDEwMTAxMDEwMDAwMDAwMTAxMDEwMTAxMDEwMTAxMDEwMzAzMDEwMTAxMDEwMTAxMDAwMDAwMDEwMTAwMDAwMDAwMDAwMDAwMDAwMDAwMDEwMTAxMDEwMTAzMDEwMTAxMDEwMTAxMDAwMDAwMDEwMTAzMDMwMTAxMDEwMTAxMDEwMTAxMDEwMTAwMDAwMDAwMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMDAwMDAwMTAxMDAwMDAwMDAwMDAwMDAwMDAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMDAwMDAwMDAxMDEwMTAzMDEwMTAxMDEwMTAxMDEwMTAxMDEwMDAwMDAwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMzAxMDEwMTAwMDAwMDAxMDEwMDAwMDAwMDAwMDAwMDAwMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMDAwMDAwMDAwMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDAwMDAwMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDMwMTAxMDAwMDAwMDEwMTAxMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDEwMTAxMDEwMTAwMDAwMDAwMDEwMDAwMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAwMDAwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMDAwMDAwMDAxMDEwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMTAxMDEwMTAxMDAwMDAwMDAwMTAxMDEwMDAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAwMDAwMDAwMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAwMDAwMDAwMDEwMTAxMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDEwMTAxMDEwMDAwMDAwMDAxMDEwMTAxMDAwMTAxMDEwMzAxMDEwMTAxMDEwMTAxMDAwMTAwMDAwMDAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDAwMDAwMDAwMTAxMDEwMTAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMTAxMDEwMTAwMDAwMDAwMDEwMTAxMDEwMTAxMDEwMTAzMDEwMTAxMDEwMTAxMDAwMDAxMDAwMDAwMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMDAwMDAwMDAxMDEwMTAxMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDEwMTAxMDEwMTAxMDAwMDAwMDAwMTAxMDEwMTAxMDEwMTAxMDMwMTAxMDEwMTAxMDEwMDAwMDEwMDAwMDAwMDAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMDAwMDAwMDAxMDEwMTAxMDEwMTAwMDEwMDAwMDAwMDAwMDAwMDAwMDEwMTAxMDEwMTAxMDEwMTAwMDAwMDAxMDEwMTAxMDEwMTAxMDEwMzAxMDEwMTAxMDEwMTAwMDAwMTAxMDAwMDAwMDAwMDAxMDEwMTAxMDEwMTAwMDAwMDAwMDAwMDAwMDEwMTAxMDMwMTAxMDAwMTAwMDAwMDAwMDAwMDAwMDAwMDAxMDEwMTAxMDEwMTAwMDAwMDAwMDEwMTAxMDEwMTAxMDEwMTAzMDEwMTAxMDEwMTAxMDIwMDAxMDEwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDEwMDAwMDAwMTAxMDEwMzAxMDEwMDAxMDAwMDAwMDAwMDAwMDAwMDAwMDEwMTAxMDEwMTAwMDAwMDAwMDAwMDAxMDEwMTAxMDEwMTAxMDMwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAxMDEwMTAwMDAwMDAxMDEwMTAzMDEwMTAwMDAwMDAxMDEwMDAwMDAwMDAwMDAwMTAxMDEwMDAwMDAwMDAwMDAwMDAwMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDAwMDAxMDEwMTAzMDEwMTAxMDAwMDAwMDEwMTAxMDAwMDAwMDAwMDAxMDAwMDAwMDAwMDAwMDAwMDAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMDAwMDEwMTAxMDEwMTAxMDEwMDAwMDAwMTAxMDEwMTAwMDAwMDAwMDAwMDAwMDAwMDAxMDEwMTAwMDAwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAwMDAwMTAxMDEwMTAxMDEwMTAwMDAwMDAwMDEwMTAxMDEwMDAwMDAwMDAwMDAwMTAxMDEwMTAxMDEwMDAwMDIwMDAwMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDAwMDAxMDEwMTAxMDEwMTAxMDAwMDAwMDAwMTAxMDEwMTAwMDAwMDAwMDEwMTAxMDEwMTAxMDEwMTAxMDAwMDAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMDAwMDEwMTAxMDEwMTAxMDEwMTAwMDAwMDAwMDEwMTAxMDAwMDAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAzMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAwMDAwMTAxMDEwMTAxMDEwMTAxMDEwMDAwMDAwMTAxMDEwMTAwMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDIwMTAxMDMwMzAzMDMwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDMwMTAzMDMwMTAxMDEwMTAxMDEwMTAxMDAwMDAxMDEwMTAxMDEwMTAxMDEwMTAxMDAwMDAxMDEwMTAxMDAwMTAxMDEwMzAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMzAzMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDMwMTAxMDMwMTAxMDEwMTAxMDEwMTAxMDEwMDAwMDEwMTAxMDEwMTAxMDEwMTAxMDEwMDAwMDEwMTAxMDAwMDAxMDEwMTAzMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMzAxMDEwMTAxMDMwMTAxMDEwMTAxMDEwMzAxMDMwMzAxMDEwMzAxMDEwMTAxMDEwMTAwMDAwMDAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMDAwMDEwMTAxMDMwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAzMDEwMTAxMDMwMTAxMDEwMTAxMDEwMTAzMDEwMzAxMDEwMTAzMDEwMTAxMDEwMTAxMDAwMDAwMDEwMTAxMDMwMTAxMDEwMTAxMDEwMTAxMDEwMTAwMDAwMDAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDMwMzAzMDMwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDMwMTAxMDEwMTAxMDEwMDAwMDAwMTAxMDEwMzAxMDEwMTAxMDEwMTAxMDEwMTAxMDAwMDAwMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDMwMzAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMzAxMDEwMTAxMDEwMTAwMDAwMDAxMDEwMTAxMDMwMTAxMDEwMTAxMDEwMTAxMDEwMDAwMDAwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMzAzMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMzAzMDEwMTAxMDEwMDAwMDAwMDAwMDEwMTAxMDEwMzAxMDEwMTAxMDEwMDAxMDEwMDAwMDAwMDAwMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDMwMTAxMDEwMTAxMDEwMzAzMDEwMTAxMDEwMTAwMDAwMDAwMDAwMDAxMDEwMTAxMDMwMTAxMDEwMTAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDMwMzAxMDMwMTAxMDEwMTAxMDAwMTAwMDAwMDAwMDEwMTAxMDEwMTAxMDEwMTAxMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDEwMTAxMDAwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDMwMTAxMDEwMzAxMDEwMTAxMDEwMDAxMDAwMDAwMDAwMTAxMDEwMTAxMDEwMTAxMDEwMDAwMDAwMDAwMDEwMDAwMDEwMTAxMDEwMTAwMDAwMDAwMDAwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDMwMTAxMDEwMTAzMDEwMTAxMDEwMTAwMDAwMDAwMDAwMDAwMDEwMTAxMDEwMTAxMDEwMTAwMDAwMDAwMDEwMTAwMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAzMDMwMTAxMDEwMTAxMDEwMzAxMDEwMTAxMDAwMDAwMDAwMDAwMDAwMTAxMDEwMTAxMDEwMTAxMDAwMDAwMDEwMTAwMDAwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAzMDEwMTAxMDEwMDAwMDAwMDAwMDAwMTAxMDEwMTAxMDEwMTAxMDEwMDAwMDAwMTAwMDAwMDAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDMwMTAxMDEwMTAwMDAwMDAwMDAwMDAxMDEwMTAxMDEwMTAxMDEwMTAwMDAwMDAwMDAwMDAwMDEwMTAzMDMwMzAzMDMwMzAzMDMwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAwMDAwMTAwMDAwMDAxMDEwMTAxMDEwMTAxMDEwMTAxMDAwMDAwMDAwMDAwMDAwMTAxMDMwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDAwMDAxMDAwMDAwMDEwMTAxMDEwMTAxMDEwMTAxMDEwMDAwMDAwMDAwMDAwMDAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDAwMDAwMDEwMDAwMDAwMTAxMDEwMTAxMDEwMTAxMDEwMDAwMDAwMDAwMDAwMDAwMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMDAwMDAwMTAwMDAwMTAxMDEwMTAxMDEwMDAwMDEwMTAwMDAwMDAwMDAwMDAwMDAwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMDAwMDAwMDAxMDAwMTAxMDEwMTAxMDEwMTAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMTAxMDAwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAzMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAwMDAwMDAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAxMDEwMDAwMDEwMTAwMDAwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDMwMTAxMDEwMTAxMDEwMTAxMDEwMTAwMDAwMDAwMDEwMTAxMDEwMTAxMDMwMTAxMDEwMTAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMTAxMDAwMDAwMDAwMDAwMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAwMDAwMDAwMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMTAxMDEwMDAwMDAwMDAwMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDAwMDAwMDAwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAxMDEwMTAwMDAwMDAwMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAzMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDAwMDAwMDAwMTAxMDEwMTAwMDEwMTAxMDEwMTAxMDMwMTAxMDEwMTAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAzMDMwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDAwMDAwMDAwMTAxMDEwMTAxMDAwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDEwMDAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDAwMDAwMDAwMTAxMDAwMTAxMDEwMDAwMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAwMDAwMDAwMDAwMDAwMDAwMDAwMDEwMTAxMDEwMDAwMDAwMDAwMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDAwMDAwMDAwMTAxMDAwMDAxMDEwMTAwMDAwMDAxMDEwMTAxMDEwMTAxMDEwMTAxMDAwMDAwMDAwMDAwMDAwMDAwMDEwMTAxMDAwMDAwMDAwMDAwMDAwMDAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDAwMDAwMDAwMTAxMDEwMDAxMDEwMTAxMDAwMDAwMDAwMTAxMDEwMTAxMDEwMTAxMDEwMTAwMDAwMDAwMDAwMDAwMDAwMDAxMDAwMDAwMDAwMDAwMDAwMDAwMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMDAwMDAwMTAxMDEwMDAwMDEwMTAxMDEwMDAwMDAwMDAxMDEwMTAxMDEwMTAxMDEwMTAxMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDEwMTAxMDEwMTAzMDMwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAwMDAwMDAxMDEwMDAwMDEwMTAxMDEwMTAwMDAwMDAwMDEwMTAxMDEwMTAxMDEwMTAxMDEwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAwMDAwMDAwMDAwMDAwMDEwMTAxMDEwMTAxMDAwMDAwMDAwMTAxMDEwMTAxMDEwMTAxMDEwMTAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAxMDEwMTAxMDEwMTAxMDEwMTAxMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDEwMTAwMDAwMDAwMDAwMDAxMDEwMTAxMDEwMTAxMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAxMDEwMTAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAxMDEwMTAxMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMDAwMA==\",\n        \"tileset\": [\n            \"myTiles.transparency16\",\n            \"sprites.castle.tileGrass1\",\n            \"sprites.castle.tileGrass2\",\n            \"sprites.castle.tileGrass3\"\n        ],\n        \"displayName\": \"approximation of western Norway\"\n    },\n    \"*\": {\n        \"mimeType\": \"image/x-mkcd-f4\",\n        \"dataEncoding\": \"base64\",\n        \"namespace\": \"myTiles\"\n    }\n}",
  "tilemap.g.ts": "// Auto-generated code. Do not edit.\nnamespace myTiles {\n    //% fixedInstance jres blockIdentity=images._tile\n    export const transparency16 = image.ofBuffer(hex``);\n\n    helpers._registerFactory(\"tilemap\", function(name: string) {\n        switch(helpers.stringTrim(name)) {\n            case \"approximation of western Norway\":\n            case \"level1\":return tiles.createTilemap(hex`4000400000000100000000000000000000000000000000000101010101010101010101010100000000000000010101010101010101010101010101010101010101010101000001010100000000000000000000000001000001010101010103030301010101000000000000000101010101010101010101010101010101010101010101010000010101000000000000000000010101010100000001010101010101010101000000000000000000010101010101010101010101010101010101010101010100010101010000000000000000000101010101010000000000010101010101000000000101000000000001010101010101010101010101010101010101010101000001010000000000000000000001010101010101000000000000010101000000000101010100000000010101010101010101010101010103030103010101010000010100000000000000000001010101010101010100000000000000000000000101010101010000000001010101010101010101010101010101030101010100000101000000000000000000000000010101010101010000000000000000000101010101010101000000000101010101010101010101010101010301010101000001010000000000000000000000000001010101010101000000000000000101010101010101010000000000010101010101030101010101010101030101010000010100000000000000000000000000000103010101010101000000000001010101010101010101000000000101010101010103010101010101010301010100000101000000000000000000000000000001010101010101010100000001010103030101010101010100000000010101010101010301010101010101010101000001010100000000000000000000000101010101010101010101000000010101010101010101010101000000000101010101010101030101010101010101010000000101000000000000000000000001010101010101010101010000000101010101010101010101010100000000010101010101010103030101010101010100000001010000000000000000000000000101010303010101010100000001010101010201010101010101010000000101010101010101010303010101010101000000010100000000000000000000010101010103010101010101000000010103030101010101010101010100000000010101010101010101010101010101010000000101000000000000000001010101010101010101010101010000000001010103010101010101010101010000000101010101010101010101010301010100000001010000000000000000010101010101010101010101010000000000010101010101010101010101010101000000010101010101010101010101030101000000010101000000000000000000000000000000010101010100000000010000010101010101010101010101010100000101010101010101010101010101010000000001010000000000000000000000000000000101010101000000000101010001010101010101010101010100000000010101010101010101010101010100000000010101000000000000000000000000000000010101010000000001010101000101010301010101010101000100000001010101010101010101010101000000000101010100000000000000000000000000000101010100000000010101010101010103010101010101000001000000010101010101010101010101010000000001010101000000000000000000000000010101010101000000000101010101010101030101010101010000010000000001010101010101010101010000000001010101010100010000000000000000010101010101010100000001010101010101010301010101010100000101000000000001010101010100000000000000010101030101000100000000000000000001010101010100000000010101010101010103010101010101020001010000000000000000000000000000010000000101010301010001000000000000000000010101010100000000000001010101010101030101010101010101010101000000000000000000000001010100000001010103010100000001010000000000000101010000000000000000010101010101010101010101010101010101010101010101010101010101010101000001010103010101000000010101000000000001000000000000000001010101010101010101010101010101010101010101010101010101010101010101010000010101010101010000000101010100000000000000000001010100000101010101010101010101010101010101010101010101010101010101010101010100000101010101010100000000010101010000000000000101010101010000020000010101010101010101010101010101010101010101010101010101010101000001010101010101000000000101010100000000010101010101010101000001010101010101010101010101010101010101010101010101010101010101010000010101010101010100000000010101000001010101010101010101010101010101010101010101010101010101010101010103010101010101010101010100000101010101010101010000000101010100010101010101010101010101020101030303030101010101010101010101010101030103030101010101010101000001010101010101010101000001010101000101010301010101010101010101010101010303010101010101010101010101030101030101010101010101010000010101010101010101010000010101000001010103010101010101010101010101010101010301010101030101010101010301030301010301010101010100000001010101010101010101010101010000010101030101010101010101010101010101010103010101030101010101010103010301010103010101010101000000010101030101010101010101010100000001010101010101010101010101010101010101030303030101010101010101010101010101030101010101010000000101010301010101010101010101000000010101010101010101010101010101010101030301010101010101010101010101010101010301010101010100000001010101030101010101010101010000000101010101010101010101010101010101010303010101010101010101010101010101010303010101010000000000010101010301010101010001010000000000010101010101010101010101010101010101010101010101010101030101010101010303010101010100000000000001010101030101010100000000000000000000000101010101010101010101010101010101010101010101010101010101030301030101010101000100000000010101010101010101000000000000000000000000000000010101000101010101010101010101010101010101010101030101010301010101010001000000000101010101010101010000000000010000010101010100000000000101010101010101010101010101010101010101030101010103010101010100000000000000010101010101010100000000010100010101010101010101010101010101010101010101010101010101010103030101010101010301010101000000000000000101010101010101000000010100000101010101010101010101010101010101010101010101010101010101010101010101010103010101010000000000000101010101010101010000000100000001010101010101010101010101010101010101010101010101010101010101010101010101030101010100000000000001010101010101010100000000000000010103030303030303030101010101010101010101010101010101010101010101010101010101010100000100000001010101010101010101000000000000000101030101010101010101010101010101010101010101010101010101010101010101010101010101000001000000010101010101010101010000000000000001010101010101010101010101010101010101010101010101010101010101010101010101010101000000010000000101010101010101010000000000000000010101010101010101010101010101010101010101010101010101010101010101010101010101010000000100000101010101010000010100000000000000000101010101010101010101010101010101010101010101010101010101010101010101010101010000000001000101010101010100000000000000000000000000000101000101010101010101010101010101010101010101010103010101010101010101010100000001010101010101010101010000000000000000000000000001010000010100000101010101010101010101010101010101030101010101010101010100000000010101010101030101010100000000000000000000000000000101000000000000010101010101010101010101010101010101010101010101010100000000010101010101010101010101010000000000000000000000000101010000000000010101010101010101010101010101010101010101010101010101000000000101010101010101010101010101000000000000000000000001010100000000010101010101010101010101010103010101010101010101010101000000000101010100010101010101030101010100000000000000000000000000000001010101010101010101010101010103030101010101010101010101000000000101010101000101010101010101010101010000000000000000000000010001010101010101010101010101010101010101010101010101010101000000000101000101010000010101010101010101010100000000000000000000010101010000000000010101010101010101010101010101010101010101000000000101000001010100000001010101010101010101000000000000000000010101000000000000000001010101010101010101010101010101010101000000000101010001010101000000000101010101010101010100000000000000000001000000000000000000010101010101010101010101010101010101010000000101010000010101010000000001010101010101010101000000000000000000000000000000000000010101010103030101010101010101010101010100000001010000010101010100000000010101010101010101010000000000000000000000000000000001010101010101010101010101010101010101010100000000000000010101010101000000000101010101010101010100000000000000000000000000000000010101010101010101010101010101010101010100000000000000000000000000000000000001010101010101010101000000000000000000000000000000010101010101010101010101010101010101010100000000000000000000000000010100000000000001010101010101000000000000000000000000000000010101010101010101010101010101010101010100000000000000000000000001010101`, img`\n................................................................\n................................................................\n................................................................\n................................................................\n................................................................\n................................................................\n................................................................\n................................................................\n................................................................\n................................................................\n................................................................\n................................................................\n................................................................\n................................................................\n................................................................\n................................................................\n................................................................\n................................................................\n................................................................\n................................................................\n................................................................\n................................................................\n................................................................\n................................................................\n................................................................\n................................................................\n................................................................\n................................................................\n................................................................\n................................................................\n................................................................\n................................................................\n................................................................\n................................................................\n................................................................\n................................................................\n................................................................\n................................................................\n................................................................\n................................................................\n................................................................\n................................................................\n................................................................\n................................................................\n................................................................\n................................................................\n................................................................\n................................................................\n................................................................\n................................................................\n................................................................\n................................................................\n................................................................\n................................................................\n................................................................\n................................................................\n................................................................\n................................................................\n................................................................\n................................................................\n................................................................\n................................................................\n................................................................\n................................................................\n`, [myTiles.transparency16,sprites.castle.tileGrass1,sprites.castle.tileGrass2,sprites.castle.tileGrass3], TileScale.Sixteen);\n        }\n        return null;\n    })\n\n    helpers._registerFactory(\"tile\", function(name: string) {\n        switch(helpers.stringTrim(name)) {\n            case \"transparency16\":return transparency16;\n        }\n        return null;\n    })\n\n}\n// Auto-generated code. Do not edit.\n"
}

```
