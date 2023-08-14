---
title: Understanding ReShade's Depth Buffer 
layout: page
nav_order: 3
parent: ReShade Guides 
---

# Understanding ReShade's Depth Buffer

----------------

## What is ReShade's Depth Buffer?
The depth buffer in a game tells what in the game has “depth”, as in, what is actually 3D, and what is just a plane. It is the basis for effects such as Ambient Occlusion to detect what occludes and what doesn’t, and for Depth of Field to detect what is close to the camera and what isn’t. Without that, those effects don’t know what is close and far, and can’t work. In the next few steps, you will learn how to identify a depth buffer, how to see if it works, common issues which makes the detection not possible, and so on.

{: .warning}
Make sure you correctly set-up ReShade and followed the previous steps on the other pages! This guide will be made on the basis that you followed all of the instructions there and got ReShade set-up and running correctly.

----------------

## Depth Buffer Basics
First of all, what you need to do before anything is to know what each part and color of the Depth Buffer means, this will explain what each means, what to notice and what to do with each case.

{: .warning}
>BEFORE DOING ANYTHING THOUGH, GO TO YOUR GAME GRAPHICS SETTINGS, AND DISABLE THE FOLLOWING:
>
> * MSAA ANTIALIASING - (FXAA or TXAA is fine though, since it doesn’t erase the depth-buffer information by doing multiple samples)
> * SSAA ANTIALIASING

Enough with the remarks, lets get to it. First, go to an area in the game that isn’t a menu, or has geometry, and enable the DisplayDepth.fx shader in your ReShade Home tab, you should see something simular to the image below:
<div class="figure">
<img src="./images/understanding_reshade_depth_buffer/depth_buffer_reversed_example.png" width="850px"/>
</div>
If it looks like the image above, the shader has loaded and is working properly, but please notice that we’re not yet done, since there are still some details wrong about what has been shown above.

{: .important}
> If your shader looks like the images below, it has no data, and you should go back a few steps and read what you should disable, carefully.
> <div class="figure">
> <img src="./images/understanding_reshade_depth_buffer/depth_buffer_no_data_example.png" width="850px"/>
> </div>
> This is what the depth buffer shader looks like with no data.
> <div class="figure">
> <img src="./images/understanding_reshade_depth_buffer/depth_buffer_no_data_reversed_example.png" width="850px"/>
> </div>
This is what the shader looks like when it has no data, and is reversed.

Now, click the “Edit global preprocessor definitions” on the “Home” tab of the ReShade menu and change the ones according to what fits your case:

----------------

### RESHADE_DEPTH_INPUT_IS_REVERSED
Used when you can see the normals, but can’t see the depth image itself (The first result image should represent this perfectly), usually starts at 1 so set it to 0 to fix it, it can also be the other way around.

----------------

### RESHADE_DEPTH_INPUT_IS _UPSIDE_DOWN
As the name says, when the image shown by the DisplayDepth shader is upside down, setting it to 1 should fix the issue.

----------------

### RESHADE_DEPTH_INPUT_IS_LOGARITHMIC
Used when the depth buffer has lots of waves or “stripes”. Very FEW games actually do use this, so you rarely will have to switch or change that.

----------------

### Depth Buffer Advanced Arguments
Those options here will rarely need to be changed, but for old games or emulators, you might have to fiddle around with them. Here is a description of them.

### RESHADE_DEPTH_INPUT_X_SCALE | RESHADE_DEPTH_INPUT_Y_SCALE
Changes the depth buffer size (multiplier, so 1 = original size, 2 = double and so on) on the horizontal (X) and vertical (Y) axis.

----------------

### RESHADE_DEPTH_LINEARIZATION_FAR_PLANE
How far is the “infinite” defined in the depth buffer. Values can either be really low or really high, so you will have to experiment to see which fits best on your case.

----------------

### RESHADE_DEPTH_MULTIPLIER
Multiplies the far plane for easy visualization of really low or really high far plane values.

----------------

{: .highlight}
Depth buffers shouldn’t be more broken than this, but in case they are, please contact crosire with info so it can be looked at and updated at future versions / revisions of ReShade, or via an addon.
