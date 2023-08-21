---
title: Configuring iMMERSE Shaders
layout: page
parent: iMMERSE & qUINT
grand_parent: Shader Repositories
---

# Configuring iMMERSE Shaders

This guide page will walk you through each step of configuring the shaders under the entire iMMERSE suite.

Click the suite you'd like to start configuring below:

---

<details markdown="block">
<summary>iMMERSE Shader Guides</summary>

Coming Soon >:)

</details>

---

<details markdown="block">
<summary>iMMERSE Pro Shader Guides</summary>

> This portion will serve as a guide for setting up and configuring specific shaders within the iMMERSE Pro shader suite!

<details markdown="block">
<summary>iMMERSE Pro Clarity</summary>

> Clarity is a shader that allows you to enhance texture and imaged details by adjusting the image's local contrast.
> 
> This allows you to add a soft glow or sharp, gritty textures to your game without the standard issues of haloing or noise.
> 
> Below is our guide on how to utilize Clarity to your advantage, and what you should look out for in order to get the best image possible!

<details markdown="block">
<summary>Adding Details | No Depth Separation</summary>

> Since Clarity is a local contrasting sharpener, you can easily get more precieved quality or "Clartiy" out of your game's textures, this guide will go over how to do so without destroying your image all together without using depth separation!
> 
> 
---
> 
> ### Step 1: Enable the Shader
> 
> Simply check the shader `iMMERSE Pro Clarity [MartysMods_CLARITY.fx]` in the `Home` tab of ReShade.
> 
> ![Check Clarity Shader](./images/immerse/immerse_clarity_enable.png)
> 
> This will activate Clarity and give you the arguments at the bottom to change.
> 
> ![Show User Clarity Options with Defaults](./images/immerse/show_user_clarity_arguments.png)
> 
---
> 
> ### Step 2: Configure `Texture Intensity` for Increased Perception and Clarity
> 
> To configure `Texture Intensity` for increased perception and clarity in the scene, move the slider to the right.
> 
> This does not take much.<br>
> You will notice that textures end up popping out more, and the contrast of the overall scene will increase.
> 
> However, do not go extremely overboard with this effect, as it can damage the game author's original envision for the game!
> 
> Example of the base game:
> 
> ![Clarity Texture Intensity Base Game Image](./images/immerse/clarity_base_game_image.png)
> 
> Example of a properly configured `Texture Intensity`:
> 
> ![Clarity Texture Intensity Properly Configured](./images/immerse/clarity_properly_configured.png)
> 
> Example of a poorly configured `Texture Intensity`:
> 
> ![Clarity Texture Intensity Poorly Configured](./images/immerse/clarity_poorly_configured.png)
> 
> Once you have configured this argument to your liking, you might notice that the scene is slightly darker than it should be - this is where `Local Contrast Intensity` will come into play!
> 
---
> 
> ### Step 3: Configure `Local Contrast Intensity` to Remove Some Contrast
> 
> In order to remove some contrast from the image, while still keeping the benifits that iMMERSE Pro Clarity has to offer, you can configure the `Local Contrast Intensity` argument!
> 
> This argument is touchy, so it only needs a little bit.
> 
> You are going to want to match the original game world's contrast with this, so that when you flick iMMERSE Pro Clarty on and off, you would see no difference in the white and black points!
> 
> Moving this slider to the right, will increase the local contrast intensity giving the image a brighter feeling, while moving it to the left and give you a darker feel.
> 
> Example of the base game:
> 
> ![Clarity Local Contrast Base Game Image](./images/immerse/clarity_base_game_image.png)
> 
> Example of a properly configured `Local Contrast Intensity`:
> 
> ![Clarity Local Contrast Properly Configured](./images/immerse/clarity_properly_configured.png)
> 
> Example of a poorly configured `Local Contrast Intensity`:
> 
> ![Clarity Local Contrast Poorly Configured](./images/immerse/clarity_local_contrast_poorly_configured.png)
> 
> If you get results that are close to the original game, with the added benifits of increased texture resolve/quality - you have set up Clarity without any depth separation properly!

</details>

</details>

</details>

---

<details markdown="block">
<summary>iMMERSE Ultimate Shader Guides</summary>

Coming Soon >:)

</details>