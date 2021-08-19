## Build and test

Now it's time to make your simulation. Start with thinking about the background to your simulation. Will it scroll, or will it be static?

![Image, gif, or video showing what they will achieve by the end of the step.](images/image.png)

**Tip**: Remember to test your project each time you add something. It is much easier to find and fix bugs before you make more changes.

--- task ---

Choose a backdrop to use for your simulation. The backdrop could remain still, or you could make it scroll.

--- collapse ---
---
title: Scroll a backdrop
---

Really, you're going to scroll a sprite, which you have created by copying a backdrop.

Create a new sprite by copying the images from a backdrop, into your sprite.

![Paint new sprite tool selected.](images/paint-new-sprite.png)
![Copy tool highlighted in the tool bar.](images/copy-backdrop.png)
![Paste tool highlighted in the tool bar.](images/paste-backdrop.png)

Create a new `variable`{:class='block3variables'} called `scroll_x`{:class='block3variables'}.

The following blocks will create a scrolling effect on the sprite when the mouse is moved left and right.

```blocks3
when flag clicked
go to x: (0) y: (0)
create clone of (myself v)
set [scroll_x v] to (0)
forever
if <(mouse x) > (200)> then
change [scroll_x v] by (5)
end
if <(mouse x) < (-200)> then
change [scroll_x v] by (-5)
end
go to x: ((scroll_x v) mod (480)) y: (0)

when I start as a clone
forever
go to x: ((scroll_x v) mod (-480)) y: (0)
```

**Tip:** Instead of using the mouse position, you could use clicking on a button or pressing a key to change the `scroll_x`{:class='block3variables'} variable.

--- /collapse ---

--- /task ---

--- task ---

Think about the sprites you will use for your simulation. Will some of them be still in the scene, will they change costumes, effects, or motion when they are interacted with? Will they scroll across the screen? How will they be controlled if they move?

--- collapse ---
---
title: Move a sprite with key presses
---

```blocks3
when flag clicked
forever
if <key (left arrow v) pressed?> then
change x by (-10)
end
if <key (right arrow v) pressed?> then
change x by (10)
end
```

--- /collapse ---


--- collapse ---
---
title: Move a sprite with on-screen controls
---

Create sprites for your directions and position them on the screen.

![Scratch cat on the Stage with right and left buttons in the bottom right-hand corner of the screen.](images/scratch-controls.png)

The buttons should have controls to broadcast their direction, when they're clicked on.

![Right sprite button.](images/right-sprite.png)
```blocks3
when this sprite clicked
broadcast [right v]
```

The sprite being controlled should move in the direction indicated.
![Scratch Cat sprite.](images/scratch-cat.png)
```blocks3
when I receive [left v]
change x by (-10)
```

--- /collapse ---

--- collapse ---
---
title: Change a sprite when it's clicked
---

You can change the appearance and orientation of a sprite whenever it is clicked. Here are some code examples.

```blocks3
when this sprite clicked
switch costume to [costume 2 v]

when this sprite clicked
change [color v] effect by (25)

when this sprite clicked
turn cw (30) degrees
```

--- /collapse ---

--- collapse ---
---
title: Animate a sprite with costumes
---

There are several ways to animate a sprite using its costumes. Here are a few examples.

```blocks3
when flag clicked
forever
next costume
wait (0.2) seconds

When I receive [right v]
switch costume to [right v]
repeat (3)
next costume
wait (0.2) seconds

When this sprite clicked
repeat (3)
next costume
```

--- /collapse ---

--- collapse ---
---
title: Change the layer of a sprite
---

Sprites that you are using as backdrops need to be on the back layer. Sprites that you want in the foreground need to be on the top layer. You can set the layer of a sprite or its clone.

```blocks3
when flag clicked
go to [back v] layer

when I start as a clone
go to [front v] layer
```

--- /collapse ---

--- /task ---

--- task ---

Will any of your sprites need to clone themselves? Will they produce many copies that perform different actions when they start?

--- collapse ---
---
title: Create clones of a sprite
---
Here are a few ways to make clones and delete them after different events.

```blocks3
when flag clicked
repeat (20)
create clone of (myself v)

when flag clicked
forever
if <touching (mouse-pointer v)> then
create clone of (myself v)

when I start as a clone
forever
if <touching (edge v)> then
delete this clone
```

--- /collapse ---

--- collapse ---
---
title: Randomise your clones
---

When a clone is created, it may need instructions on how to move, but you might want the different clones to behave slightly differently. You can use `random`{:class='block3operators'} blocks to do this.

```blocks3
when I start as a clone
point in direction (pick random (0) to (359))
forever
move (10) steps
wait (0.1) seconds
if on edge, bounce

when I start as a clone
forever
glide (pick random (1) to (10)) secs to (mouse-pointer v)
```

--- /collapse ---

--- collapse ---
---
title: Events to create a clone
---

Clones can be created with many different `events`{:class='block3events'}. The blocks below will create a clone of a sprite everytime it is clicked upon.

```blocks3
when this sprite clicked
create clone of [myself v]
```

You can create clones whenever the mouse is clicked as well, and make the clone appear at the mouse-pointer's location. Clones can appear in any location you like, so you might like them to go to a specific sprite.

```blocks3
when flag clicked
forever
if <mouse down?> then
create clone of [myself v]

when I start as a clone
go to x: (mouse x) y: (mouse y)
```

--- /collapse ---

--- /task ---

--- task ---

Will there be a musical or sound effect aspect to your simulation? Maybe there's background noise, or a sprite plays a tune when it is clicked?

--- collapse ---
---
title: The Scratch music extension
---

Once you have added the extension, new blocks will be available to you.

There are three main elements that can be changed within these blocks.

- `beats`{:class='block3custom'} are a unit of time used in music. A beat could be a second long or a quarter of a second long. It is up to you.

- `tempo`{:class='block3custom'} sets how many beats there are in a minute: `60` beats a minute would mean that a beat is `1` second long.

- `note`{:class='block3custom'} is the pitch of the note being played: `60` is the same as **middle C** on a piano.

--- /collapse ---

[[[generic-scratch-sound-from-library]]]

[[[scratch3-record-sound]]]

[[[scratch3-sound-effects]]]

[[[scratch3-reverse-sound]]]

[[[scratch3-crop-sound]]]

--- /task ---

--- task ---

Do you want your sprites to keep repeating an action, until some condition has been met? You can use `repeat until`{:class='block3control'} blocks to do this.

--- collapse ---
---
title: Using `repeat until`{:class='block3control'} blocks
---

Here is a set of blocks that will keep a sprite moving, until its `y`{:class='block3motion'} position reaches `-250`.

```blocks3
when flag clicked
repeat until <(y position) < [-250]>
change y by (-10)
```

--- /collapse ---

--- /task ---


--- task ---

Think about the organisation of your blocks, and the inputs that might be needed. Can you use `My Blocks`{:class='block3myblocks'} to **optimise** your project?

--- collapse ---
---
title: Use My Blocks to organise code
---

The simplest way to use `My Blocks`{:class='block3myblocks'} is to help organise your code. Here is a simple example.

```blocks3
define move right
if <not <touching (edge v) ?>> then
switch costume to [right_1 v]
change x by (2)
switch costume to [right_2 v]
change x by (2)
switch costume to [right_3 v]
change x by (2)
end

define move left
if <not <touching (edge v) ?>> then
switch costume to [left_1 v]
change x by (-2)
switch costume to [left_2 v]
change x by (-2)
switch costume to [left_3 v]
change x by (-2)
end

when flag clicked
forever
if <key (right arrow v) pressed> then
move right
end
if <key (left arrow v) pressed> then
move left
```

--- /collapse ---

--- collapse ---
---
title: Using inputs with My Blocks
---

`My Blocks`{:class='block3myblocks'} take text and number inputs as well.

```blocks3
define move (direction) (speed)
if <(direction) = [left]> then
change x by ((-1) * (speed))
end
if <(direction) = [right]> then
change x by ((1) * (speed))

when flag clicked
if <(mouse x) < (-200)> then
move [left] (speed)
end
if <(mouse x) > (+200)> then
move [right] (speed)
```

--- /collapse ---

--- /task ---

--- task ---

The key to most 2.5D scenes is changing the size of a sprite to give the impression that it is further away.

--- collapse ---
---
title: Changing sprite sizes relative to position
---

The following blocks will make a sprite smaller as it moves up the screen, and therefore appear further away.

```blocks
when flag clicked
forever
change y by (10)
change size by (-3)
wait (0.2) secs
```

--- /collapse ---

--- /task ---


--- task ---

**Test:** Show someone else your project and get their feedback. Do you want make any changes to your scene? 

--- /task ---

--- task ---

**Debug:** You might find some bugs in your project that you need to fix. Here are some common bugs.

--- collapse ---
---
title: My clones don't appear
---

Are your clones hidden? Make sure that when the clones are created, the `show`{:class='block3looks'} option is used. Also make sure that you have them on the `front layer`{:class='block3looks'}.


--- /collapse ---

--- collapse ---
---
title: My sprite doesn't move off the screen correctly
---

If you want a sprite to cycle from one side of the screen to another, or vanish when it gets to one side of the screen, then you can check its position and perform some action. You might need to check where the centre of your sprite is, on its costume, to make sure this works properly. It's easisest to drag the sprite to the side of the screen, and then check its `x`{:class='block3motion'} and `y`{:class='block3motion'} positions.


--- /collapse ---

--- collapse ---
---
title: My Blocks are not working
---

Have you checked that you are using your new block somewhere in your code. You can `define`{:class='block3myblocks'} a new block, but then you need to use it for the code beneath it to actually run.

--- /collapse ---

--- collapse ---
---
title: My clones aren't doing anything
---

Are you using the `when I start as clone`{:class='block3control'} block, to tell the clone what to do?

Do you have any conditions that might stop the clones from working? For instance, are they supposed to move until they touch the edge of the screen? If a clone is created at the edge of the screen, then they won't do anything.


--- /collapse ---

--- collapse ---
---
title: My sprites are moving in the wrong direction
---

Check that you are using the `change x by`{:class='block3motion'} block to move the sprites left and right, and the `change y by`{:class='block3motion'} block to move them up and down.

Check whether you are using positive and negative numbers correctly, to increase or decrease `x`{:class='block3motion'} and `y`{:class='block3motion'}.

--- /collapse ---

You might find a bug not listed here. Can you figure out how to fix it?

We love hearing about your bugs and how you fixed them. Use the feedback button at the bottom of this page if you found a different bug in your project.

--- /task ---

--- save ---
