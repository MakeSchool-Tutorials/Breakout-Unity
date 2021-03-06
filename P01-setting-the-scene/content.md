---
title: "Setting the Scene"
slug: setting-the-scene
---

> [action]
>
To get started, make an empty 3D project and call it Breakout.
>
![Create a new 3D Unity project](assets/set_up.png)
>
Import the Breakout Package, which you can get via:
>
```
cd Desktop
git clone https://github.com/MakeSchool-Tutorials/Breakout-Unity-Starter.git
```
>
![Import the Breakout Package](assets/image09.png)

This will populate your Assets folder in the Project Panel with a structure of objects that we'll use to build the game.

![Imported files appear in the Assets folder](assets/new_assets.png)

We've also provided a Scene that shows the final layout of the objects, named Breakout.

![The final layout](assets/final.png)

Feel free to double-click to open it and check it out if you'd like.

![The final game](assets/final_layout.png)

# Creating the scene

> [action]
>
We'll need to create a new Scene, so that you can set everything up from the basic pieces (`File->New Scene`).
>
![New Scene](assets/new_scene.png)
>
Now open up the `Prefabs` folder and drag the `Ball`, `Board`, and `Paddle` into the Hierarchy Panel.
>
![Drag the Ball, Board, and Paddle Prefabs into the Hierarchy Panel](assets/drag_ballboardpaddle.gif)
>
We've reduced the size of our icons to make them easier to see.
>
![Drag the slider at the bottom of the Project Panel to reduce icon size](assets/reduce_icon_size.gif)

<!--  -->

> [info]
>
Dragging objects from the Project Panel into the Hierarchy Panel or the Scene View adds those objects to the Scene. Dragging into the Hierarchy Panel allows you to drag multiple and sets their positions to the defaults for you, whereas dragging into the Scene View only allows you to drag one, but allows you to position it visually when you drop it in.

<!-- -->

# Hooking it up

> [action]
>
Select the `Paddle` in the Hierarchy Panel and drag the `Ball` in the Hierarchy Panel into the `Ball` slot (under `Paddle Controller` in the Inspector on the right).
>
![Drag the ball into the Paddle's Ball slot](assets/drag_ball_into_slot.gif)

This assigns one of the components, which is a script, on the `Paddle` to reference the `Ball` in our Scene.

# Positioning our elements

We now want to position our `Board` and `Paddle`.

> [action]
>
Click to select the `Board` in the Hierarchy and then set its position in the Inspector to `(0,0,0)`. Then set the Paddle to position `(0,-2,0)`.
>
![Set the Board and Paddle positions](assets/Capture1.png)

# Material desires

You may have noticed that the `Paddle` is pink, this is because it has no _Material_. _Materials_ give objects color, and pink is the color Unity assigns if no color is defined.

> [action]
>
Open on the `External/Metal textures pack/pattern 02` folder in your Project and drag `Pattern 02` to the `Paddle` to apply the Material to the Paddle.
>
![Drag a Material onto the Paddle](assets/drag_material.gif)

If you're interested in a more technical definition of what a material does, it tells the 3D renderer how to draw an object. Specifically, it tells the renderer what kind of shader to use, and what properties to send to that shader.

> [info]
>
A shader is a piece of code the describes the rules on how to draw an object. Some shaders allow an object to be transparent like glass, others have rules to texture an object, or make it metallic. Shaders can do fancy things like tell the renderer how to bend light, or just to color a mesh with an image or solid color.

In this case we have drawn a _texture_ (image) on an object.
