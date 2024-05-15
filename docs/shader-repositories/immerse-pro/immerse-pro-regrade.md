---
title: "ReGrade"
layout: page
nav_order: 6
parent: "iMMERSE Pro"
grand_parent: Shader Repositories
---

# iMMERSE Pro: ReGrade

ReGrade is a color-correction suite designed to be feature-packed enough to be close to commercial tools. With all of its available options, it has the power to bring the usability and versatility of even commercial-level tools to games. Effectively removing the step of toggling between a color-correction software and the game to finish editing, making it all real-time and hassle-free.

While there is no correct values and usage of this shader, people familiarized with Photography, color theory and related areas will make the best usage. However, even people with no experience can get great results by looking at the changes made being shown instantly.

---

## Color Operations and Slots

At first, you should notice lots of drop-down boxes in the section "Color Operations", this tells the shader what color operation is applied on each step. Think of it like building blocks, with the first being the bottom layer, and the last being the top layer.

You have 9 slots available, and the following options, they can be applied in any order as the user desires or needs:

The parameters for each option is explained further down the guide, so if you wanna know the values for each function, keep reading:

* **Levels:** will change the black and white levels of the image.

* **Adjustments:** is for general color and overall image changes without much granularity

* **Lift Gamma Gain:** allows you to tweak the "Lift", "Gamma" and "Gain" levels of the image.

* **Calibration:** allows you modify the default values for the Color Hues and Layers.

* **Color Remapping:** allows you to directly change the colors of the image.

* **Tone Curves:** allows you to change the tones of the exposed and unexposed (bright and dark) parts of the image.

* **Split Toning:** allows you to change the values and colors of the tones (exposed and unexposed) parts of the image separately. Effectively having even more granularity over "Tone Curves".

* **Color Balance:** allows for changing the colors on the Shadows, Midtones and Highlighs of the image, offering granularity beyond just the exposure of the shadows.

* **Special Transforms:** allows for more "artistic" changes on the scene brightness and light levels.

![ReGrade Slots](../images/regrade_slots_preview.png)

Now that you know each of the functions, lets get deeper and start doing some modifications.

---

## Levels

Levels changes the black and white levels of a picture. On a bare explanation: It means it changes what is considered completely back and completely white on the image.
The parameters are:

* **Bypass Levels:** effectively disables the changes made in that layer.

* **Black Level In:** changes where the black levels start.

* **White Level In:** changes where the white levels start.

* **Black Level Out:** changes where the black levels end.

* **White Level Out:** changes the white levels end.

---

## Adjustments

Adjustments are for overall global / wide adjustments of a picture. Its made to have less granularity and serve as quick tweaks to change and stabilize colors and scene without needing to fiddle with settings much.
The parameters for those are:

* **Bypass Adjustements:** disables the changes made in that layer.

* **Contrast:** changes the entire image's contrast.

* **Exposure:** changes the entire image exposure. Exposure is how much light the lens is absorbing. With higher values making the image brighter, and lower values making the image darker.

* **Gamma:** changes the brightness of the image.

* **Filmic Gamma:** changes the brightness of the dark points of the image.

* **Saturation:** changes how much the colors are saturated in the image.

* **Vibrance:** changes how vibrant and colorful the colors are in the image.

---

## Lift, Gamma and Gain

Lift,Gamma and Gain changes separate the bright parts of the image in 3 layers - Dark, Midtones and Bright. Not only that, but it allows to change the colors of each one of them.
The parameters are:

* **Bypass Lift Gamma Gain:** disables the changes made in that layer.

* **Lift Gamma Gain Mode:** changes the way the calculations for it works, with 2 standards available, "American Society of Cinematographers" and "DaVinci Resolve", with the latter mimicing how the software works.

* **Lift:** changes the White levels of the image. If set to non-grey values, it will change the color aswell.

* **Gamma:** changes the midtones of the image. If set to non-grey values, it will change the overall temperature of the image.

* **Gain:** changes the dark levels of the image. If set to non-grey values, it will change the color of dark parts of the image.

---

## Calibration

This adjust overall color and temperature calibrations of the image. Again, for general changes without much need for granularity.
The parameters are:

* **Bypass Calibration:** disables the changes made in that layer.

* **Color Temperature:** changes the white / temperature of the entire image.

* **Lab A Offset:** changes the Magenta / Green balance of the image colors.

* **Lab B Offset:** changes the Orange / Blue balance of the image colors.

* **R G B Primary Mode:** changes how the color changing behaviour works, with 3 methods available: "ReGrade Legacy" mimicing the old ReGrade shader version, "Barycentric" and "Hue Based".

* **R G B Primary Hue:** changes the hue offset of each color channel (Red, Green and Blue)

* **R G B Primary Saturation:** changes the hue saturation value of each color channel (Red, Green and Blue)

---

## Color Remapping

Color remapping allows the user to change the color values of each one of the colors in the image, this allows them to have more control over the colors of the image.

The parameters dictate changes to each one of the colors (Red, Orange, Yellow, Green, Aqua, Blue and Magenta) , separating it by Hue (First Value), Saturation (Second Value) and Color Value (Third Value)

---

## Tone Curve

Tone curve allows the user to change the brightness of the 3 light values of the image per-tone, which means it can use this to make certain gradients within those areas brighter or darker.

The parameters for those are:

* **Shadows:** changes the images Shadow brightness.

* **Darks:** changes the images Dark points brightness.

* **Lights:** changes the images Bright points brightness.

* **Highlights:** changes the images brigthest points brightness.

* **Dark Wash Range:** changes how much dark points washes / bleaches the colours.

* **Dark Wash Intensity:** changes how intense the bleaching of the colors are.

---

## Split Toning

Split toning allows the user to change the tint of 2 of the image's tone properties in a curve.

The parameters are:

* **Split Mode:** changes which parts of the image's curve will be changed, being able to pick between Shadows / Highlights and Grey / Saturated Colors.

* **Tint A:** changes the tint / grey value of the first parameter.

* **Tint B:** changes the tint / grey value of the second parameter.

* **Balance:** changes which side will be more intense / prevalent, the lower the value, the more it will prioritize the first value, and the higher the value, the more the second value is prioritize.

* **Blend Mode:** changes how these changes are mixed in the image. With the option being "Soft Light" and "Overlay".

---

## Color Balance

Color balance changes the color Brightness and saturation of the image's lighting.

They are split in Dark, Hightlights and Midtones.

---

## Special Transforms

Special transforms are more artistic changes for the image. 

There are 2 options here skipping the bypass one, which is "Bleach Bypass (Gamma Corrected)," which bleaches taking Gamma into consideration, and "Gamma on Luma - Chroma," which changes the gamma level on the colors and luminosity.

---

## Vignette and Utility

Vignette applies a camera vignette effect, which darkens the image around. It doesn't depend on any of the layer slots since its always applied over all of them, but the difference between this and others is the fact it is deeply integrated into ReGrade, so it takes all the color and image changes into account when applying it.

The parameters for the Vignette are:

* **Mechanical Vignette: Radius** changes the Vignette radius on the image.

* **Mechanical Vignette: Blurryness** changes how out-of-focus the outer-part of the vignette is on the image.

* **Mechanical Vignette: Shape** changes the shape of the vignette, with 0 being circular and higher values aiming for more anamorphic-looking ones.

* **Sensor Vignette: Scale** changes how much of the vignette is visible on the image.

* **Vignette Blending Mode** changes how the Vignette will be blended on the image. With "HDR simulation" focusing on the brightness and color levels and blending with those, with an option to preserve tones, and Standard just placing it over the image. 