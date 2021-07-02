## Build and test

Now it's time to make your simulation. Start with thinking about the background to your simulation. Will it scroll, or will it be static?

Image, gif or video showing what they will achieve by the end of the step. ![](images/image.png)

**Tip**: Remember to test your project each time you add something. It is much easier to find and fix bugs before you make more changes.

--- task ---

Choose a backdrop to use for your simulation. The backdrop could remain still, or you could make it scroll.

--- /task ---

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

The following blocks will create a scrolling effect on the sprite when the mouse is moved left and right.

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

--- /collapse ---

--- task ---

Think about the sprites you will use for your simulation. Will some of them be still in the scene, will they change costumes, effects or motion when they are interacted with? Will they scroll across the screen?

scratch-scroll-a-sprite

scratch-change-sprite-on-click

scratch-tablet-friendly-control

scratch-animate-a-sprites-costume

--- /task ---

--- task ---

Will any of your sprites need to clone themselves? Will they produce many copies that perform different actions when they start?

scratch-create-clones

scratch-random-clones

--- /task ---

--- task ---

Will there be a musical or sound effect aspect to your simulation? Maybe there's back ground noise, or a sprite plays a tune when it is clicked on?

scratch-music-extension

--- /task ---

--- task ---

Think about the organisation of your blocks, and the inputs that might be needed. Can you use `myblocks`{:class='block3myblocks'} to **optimise** your project?

scratch-using-my-blocks

scratch-my-blocks-inputs

--- /task ---

--- task ---

**Test:** Show someone else your project and get their feedback. Do you want make any changes to your book? 

--- /task ---

--- task ---

**Debug:** You might find some bugs in your project that you need to fix. Here are some common bugs.

--- collapse ---

Each debug in a collapse or ingredient

--- /collapse ---

You might find a bug not listed here. Can you figure out how to fix it?

We love hearing about your bugs and how you fixed them. Use the feedback button at the bottom of this page if you found a different bug in your project.

--- /task ---


--- save ---