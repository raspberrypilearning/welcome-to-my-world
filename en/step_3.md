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