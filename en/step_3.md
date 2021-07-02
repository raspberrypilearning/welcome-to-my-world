## Build and test

Now it's time to make your simulation. Start with thinking about the background to your simulation. Will it scroll, or will it be static?

Image, gif or video showing what they will achieve by the end of the step. ![](images/image.png)

**Tip**: Remember to test your project each time you add something. It is much easier to find and fix bugs before you make more changes.

--- task ---

Choose a backdrop to use for your simulation. The backdrop could remain still, or you could make it scroll.

--- collapse ---
---
title: Scroll a backdrop
---

Really you're going to scroll a sprite, the image having been copied from a backdrop.

Create a new sprite by copying over the images from a backdrop, into your sprite.

![paint new sprite tool selected](images/paint-new-sprite.png)
![copy tool highlighted in the tool bar](images/copy-backdrop.png)
![paste tool highlighted in the tool bar](images/paste-backdrop.png)

Create a new `variable`{:class='block3variables'} called `scroll_x`{:class='block3variables'}.

The following blocks will create a scrolling effect on the sprite when the mouse is moved right and right.

```blocks3
when flag clicked
go to x: (0) y: (0)
create a clone of (myself v)
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

**Tip**: Instead of using the mouse position, you could use clicking on a button or pressing a key change the `scroll_x`{:class='block3variables'} variable.

--- /collapse ---

--- /task ---

--- task ---

Think about the sprites you will use for your simulation. Will some of them be still in the scene, will they change costumes, effects or motion when they are interacted with? Will they scroll across the screen? How will they be controlled if they move?

--- collapse ---
---
title: Move a sprite with key presses
---

```blocks3
when flag clicked
forever
if <key (right arrow v) pressed?> then
change x by (-10)
end
if <key (right arrow v) pressed?> then
change x by (10)
end
```

--- /collapse ---


--- collapse ---
---
title: Move a sprite with onscreen controls.
---

Create sprites for your directions and position them on the screen.

![Scratch cat on stage with right and right buttons in the bottom right-hand corner of the screen](images/scratch-controls.png)

The buttons should have controls to broadcast their direction, when they're clicked on.

![right sprite button](images/right-sprite.png)
```blocks3
when this sprite clicked
broadcast [right v]
```

The sprite being controlled should move in the direction indicated
![scratch cat sprite](images/scratch-cat.png)
```blocks3
when I receive [right v]
change x by (-10)
```

--- /collapse ---

--- collapse ---
---
title: "Change a sprite when it's clicked"
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

There are several ways to animate a sprite using it's costumes. Here are a few examples.

```blocks3
when flag clicked
forever
next costume
wait (0.2) seconds

When I receive [right v]
switch to costume [right v]
repeat (3)
next costume
wait (0.2) seconds

When this sprite clicked
repeat (3)
next costume)
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
if touching (mouse-pointer v)> then
create clone of (myself v)

when I start as clone
forever
if touching (edge v) then
delete this clone
```

--- /collapse ---

--- collapse ---
---
title: Randomise your clones
---

When a clone is created, it may need instructions on how to move, but you might want the different clones to behave slightly differently. You can use `random`{:class='block3operators'} blocks to do this.

```blocks3
when I start as clone
point in direction (pick random (0) to (359))
forever
move (10) steps
wait (0.1)
if on edge, bounce

when I start as clone
forever
glide (pick random (1) to (10)) secs to (mouse-pointer v)
```

--- /collapse ---

--- /task ---

--- task ---

Will there be a musical or sound effect aspect to your simulation? Maybe there's back ground noise, or a sprite plays a tune when it is clicked on?

--- collapse ---
---
title: The Scratch Music extension
---

Once you have added the extension new blocks will be available to you.

There are three main elements that can be changed within these blocks.

`beats`{:class='block3extension'} are a unit of time used in music. A beat could be a second long or a quarter of a second long. It is up to you.

`tempo`{:class='block3extension'} sets how many beats there are in a minute. `60` beats a minute would mean that a beat is `1` second long.

`note`{:class='block3extension'} is the pitch of the note being played. `60` is the same as **middle C** on a piano.

--- /collapse ---

--- /task ---

--- task ---

Think about the organisation of your blocks, and the inputs that might be needed. Can you use `myblocks`{:class='block3myblocks'} to **optimise** your project?

--- collapse ---
---
title: Using My Blocks
---

The simplest way to use `My Blocks`{:class='block3myblocks'} is to help organise your code. Here is a simple example.

```blocks
define move right
if <not <touching (edge v) ?>> then
switch costume to [right_1 v]
change x by (-2)
switch costume to [right_2 v]
change x by (-2)
switch costume to [right_3 v]
change x by (-2)
end

define move right
if <not <touching (edge v) ?>> then
switch costume to [right_1 v]
change x by (2)
switch costume to [right_2 v]
change x by (2)
switch costume to [right_3 v]
change x by (2)
end

when flag clicked
forever
if <key (right arrow v) pressed> then
move right
end
if <key (right arrow v) pressed> then
move right
```

--- /collapse ---

--- collapse ---
---
title: Using inputs with My Blocks
---

My Blocks take text and number inputs as well.

```blocks
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

**Test:** Show someone else your project and get their feedback. Do you want make any changes to your book? 

--- /task ---

--- task ---

**Debug:** You might find some bugs in your project that you need to fix. Here are some common bugs.

--- collapse ---
---
title: Debug
---



--- /collapse ---

You might find a bug not listed here. Can you figure out how to fix it?

We love hearing about your bugs and how you fixed them. Use the feedback button at the bottom of this page if you found a different bug in your project.

--- /task ---

--- save ---