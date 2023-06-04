# NoRenderDemo

This demonstrates an apparent problem with rendering derived components in VS Community 2022 v17.6.2.

I put the demo in the Counter.razor page.  It includes 2 nested levels of base + derived child components.  Neither level renders when the derived component @inherits its base.  But removing the @inherit (as the demo does for level 1) allows the conponent to render.  You can test this by adding and removing @inherit ChildLevel1Base in ChildLevel1Derived.  The same is true of level 2, which I inclued only because my app has 2 levels.

The base + derived components have worked for a very long time, but stopped rendering when I upgraded from VS Community 2022 v17.5.5 to v17.6.2.  While diagnosing this, I did two things:
(1) I copied the base code into the derived code and removed the @inherit.  This let the "derived" components render; and
(2) I did a rollback to v17.5.5, after which the components started rendering again.

In case it helps to know, after the rollback, I made a copy of my app and once again upgraded to v17.6.2.  When I tried to run the app, the components once again failed to render (no surprise).  I then tried to run the app in VS Community 2019 and the components DID NOT render.  But when I ran the copy of the app that I made, the components DID render using VS 2019.  That is surprising to me, but then I don't understand much of what happens when an app is built.
