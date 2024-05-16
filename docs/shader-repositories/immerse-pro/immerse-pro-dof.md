---
title: "Depth of Field"
layout: page
nav_order: 8
parent: "iMMERSE Pro"
grand_parent: Shader Repositories
---

# iMMERSE Pro: Depth of Field

iMMERSE Pro: Depth of Field is a shader which adds depth of field to a scene. It has been developed to be a physically-based shader which emulates all of the parameters and features of a real life camera.

The shader allows for total control for focusing on specific points of interest or objects on a scene, be it a macro-object or micro, and has enough parameters that will certainly fit your virtual photography needs.

---

## Enabling the shader

In ReShade's "Home" tab, enable the shader `iMMERSE Pro Depth of Field [MartysMods_DEPTHOFFIELD.fx]` and the the shader's arguments will appear in the shader arguments section.

## Preparing to focus on the subject / focusing section

Before we start, lets take a look at the base options, first one and most-important is "Focusing Mode," it has 3 options, each one worth taking note.

* "Manual Focus" is first and most advanced one, but also the hardest to use. It allows you to have full control of the "camera" lens for focusing.

* "Autofocus" is the second, its the most limited, and will not fit all cases, but might be useful for gameplay. It always focuses on the closest object inside the area of interest / focus area parameter (more on that later).

* "Autofocus (Point and Click with MMB [Middle Mouse Button])" is the third one. It works like the autofocus function in most mobile phones, you point to the subject you want using the mouse and press the middle mouse button to focus on it. Easy to use and quite controllable, this should be the best and easiest option for amateur photographers.

To help you with those, a parameter named "Enable Focus Helper" is available. Enabling it will show a few pointers on the screen, changing according to the mode. It consists of:
- A small/darker box, which is the focus subject of the lens.
- The bigger, outer box, which is responsible for highlighting the background range.
- A white stripe / line, which is used to represent the focal point transition from near to far.
- A blue overlay, which is used to represent the furthest / infinity focal point of the camera.

![Example of the debug output in `Manual Focus` mode](../images/dof_debug_output.webp)

With those 2 explained, we can start going on and actually preparing the focus.

"Autofocus Center" is responsible for defining where the camera will be focusing on the scene. Despite its name, it is also where the manual focus will be focusing. Change that if you need to focus on something that isn't on the center of the scene.

"Autofocus Detection Range" is responsible for expanding or narrowing the range of focusing. This is useful for precisely narrowing what you want / need to be the focal subject.

"Autofocus Adjustment Speed" determines how responsive the lens/camera is on focus changes. The bigger the number, the faster the camera will react to changes. If you are only using it for gameplay which requires fast movement, its recommended to be kept at the highest value so it doesn't distract from action.

## Tweaking the focus and lens parameters

The section dedicated to the lense is separated on 2 subcategories: "Simple" and "Advanced," with one fine tuning even more the focus, exposure, how many aperture blades the camera has and the blur, and the latter one manipulating the bokeh shapes themselves and lens distortion of the camera.

In the "Simple" section, we have:

* "Focal Length," which is how far the camera will focus. Lower values will produce less blur and have a smaller depth of field, while larger ones will allow the camera to focus more and further.
* "Aperture F-Stops" tells how open or closed the camera blades are. The higher that number is, the more light "goes through" the camera lens, which means more blur and less-defined shapes.

![Aperture F-Stops Example](../images/dof_fstop_preview.webp)

* "Foreground \ Background Blur" tells how much the close and far points of the camera are blurred. While in real life it is always dependant on where and what you're focusing, here, for artistic liberty, the shader allows you to tweak how blurry objects closer or farther from the camera gets blurred.
* "Aperture Blade Count" determines how many blades the camera shutter has, directly influentiating on how the bokeh shapes are defined and visualized.

![Aperture Blade Count Example](../images/dof_blade_preview.webp)

* "Aperture Roundness" defines how sharp or rounded the shapes are. In real life, the blades determine how rounded or not the shapes are, but here, for artistic liberty and freedom, you can tweak on how rounded you want the blades to be;

![Blade Roundness Example](../images/dof_roundness_preview.webp)

In the "Advanced" section, we have:

* "Bokeh Rotation" defines how angled the bokeh shapes are. Best used when "Bokeh Roundness" parameter is set to 0.0

![Example of different bokeh rotations](../images/dof_rotation_preview.webp)

* "Tangential Bokeh Scale" defines how distorted the bokeh shapes are tangentially (from center to outside, in a circular-manner).

![Tangential bokeh scale results](../images/dof_tangential_preview.webp)

* "Sagittal Bokeh Scale" defines how distorted the bokeh shapes are sagittally (outer-lense, in a circular offset).

![Sagittal bokeh scale results](../images/dof_sagittal_preview.webp)

* "Anamorph Bokeh Ratio" defines how distorted the shapes are horizontally. The higher the value, the more "squished" the shapes will appear.

![Anamorph bokeh scale results](../images/dof_anamorph_preview.webp)

* "Spherical Aberration" defines how sharp the inner shapes of the DoF are. The lower the value, the more filled the shapes are, with the higher values focusing the color to the outer-ring of the shape.

* "Spherical Aberration Mode" allows to switch to how many lens the camera has for focusing. With Single being one, and doublet being two. Those change how the aberration distribution on the shapes work.

![Spherical Aberration Mode results](../images/dof_aberration_mode_preview.webp)

## Tweaking the blur and quality of the effect

This part of the shader is more related to the quality and performance than the looks themselves, even though a few of its elements change the overall look, most users won't need to touch that part.

"Bokeh Quality" is self-explainatory. It changes how much points are used to sample / draw the bokeh shape. With higher values improving the quality of the blur and the shapes, but costing more to render.

![Bokeh Quality preview](../images/dof_bokeh_quality.webp)

"Bokeh Highlight Intensity," "Bokeh Highlight Gamma," and "Bokeh Color Intensity" all change how brighter, darker or saturated the shapes are. The images below shows how those look, in order.

![Bokeh Highlight Intensity](../images/dof_highlight_intensity_preview.webp)

![Bokeh Highlight Gamma](../images/dof_highlight_gamma_preview.webp)

![Bokeh Color Intensity](../images/dof_color_intensity_preview.webp)

"Bokeh Smoothness" blurs the sample circles, eventually filling the shapes if they are separated, may be useful as a counter for raising the sample quality, at the cost of sharpness.

"Enable Undersampling Protection" makes it so all areas are sampled equally, preventing areas from being ignored by the blurring or shape sampling algorithms. It improves the quality of the blur, but has a very high performance cost.

"Enable Bokeh Sprites" and "Sprite Bokeh Percentage" tells the shader how much of the disc-sampled shapes to replace with procedural generated ones. The higher the value, the more will be replaces. This allows for even more defined and sharp shapes, at the cost of performance.

The last few are optional, with them being:

* "Bokeh Shape Helper" which will forcefully draw the bokeh shapes on the screen to allow to preview how they will look.

* `DOF_FULL_RESOLUTION`, which is a pre-processor toggle, will render the DoF at the screen resolution. It improves the quality but is overkill and should not ever be necessary. It is there however if someone wants to experiment with it.