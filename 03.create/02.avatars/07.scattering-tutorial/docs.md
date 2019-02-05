---
title: Tutorial: Add a Scattering Effect
taxonomy:
    category: docs
---

Subsurface Scattering (SSS) is the diffuse reflection caused by light entering a material, being absorbed, scattered, and eventually exiting the material. It's critical for surfaces like paper, marble, wax, and realistic skin. You can add this effect to your avatar in High Fidelity.

**On This Page**

+ [Subsurface Scattering Map and Value](#subsurface-scattering-map-and-value)
+ [Add Scattering to an Avatar](#add-scattering-to-an-avatar)

## Subsurface Scattering Map and Value

Subsurface scattering (SSS) is noticeable when light passes through a thin translucent object like an avatar's skin. It causes the diffusion of light within the shallow top layer of skin. 

Scattering is composed of a "scattering value" and a "scattering map". By setting the scattering value and map, you can influence how light scatters on the geometry of an avatar. 

+ The scattering value is a `[0,1]` number which sets the amount of scatter. 
+ The scattering map is gray scale image that masks the areas of scatter. It is based on the avatar's UV map.

## Add Scattering to an Avatar

Add scattering to an avatar by adding the value and map to the avatar's FST file. 

1. [Create a custom avatar](../create-avatars).
2. Create a scattering map for the subsurface scattering in Adobe Photoshop or its equivalent.
3. [Package Your Avatar](../create-avatars#package-your-avatar) in High Fidelity.
4. Add scattering information to the avatar's FST file. For example:
   ```json
   materialMap = { "body_mat": { "scattering": 1.0, "scatteringMap" : "![skinMap.jpg](http://.../skinMap.jpg)" } }
   ```
5. Wear the avatar to observe the scattering effects in High Fidelity.

Here's an example of the scattering effect. The left image has no scattering and the right image has scattering. You can see the red diffuse reflection along the shadow line.

| ![](no-scattering.jpg) | ![](scattering.jpg) |
| ---------------------- | -------------------|
|                         | |

You can also check out the following avatars that have scattering effects:

+ [Matthew](https://hifi-public.s3.amazonaws.com/sam/models/skinRenderingTest/matthew/matthew.fst) 
+ [Priscilla](https://hifi-public.s3.amazonaws.com/sam/models/skinRenderingTest/priscilla/priscilla.fst)

**See Also**

+ [Create Your Own Avatar](../create-avatars)
+ [Package Your Avatar](../create-avatars#package-your-avatar)
+ [PBR Materials](../../3d-models/pbr-materials-guide)

