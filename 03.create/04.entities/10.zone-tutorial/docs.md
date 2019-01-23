---
title: Tutorial: Modify a Zone Entity's Properties
taxonomy:
    category: docs
---

A zone entity is a 3D area where you can create custom lighting environments. You can define zone boundaries using shapes and customize the zone’s light properties such as its intensity, direction, and color to create different effects. 

The mini tutorials on this page show you how zone entities work and how you can edit their properties to create areas with different lighting effects. 

**On This Page:**

- [Prerequisites](#prerequisities)
- [Create a Zone Entity](#create-a-zone-entity)
- [Create Nested Zones with Different Lighting](#create-nested-zones-with-different-lighting)
- [Change a Zone's Shape](#change-a-zones-shape)
- [Add a Skybox to a Zone](#add-a-skybox-to-a-zone)
- [Add Ambient Light to a Zone](#add-ambient-light-to-a-zone)
- [Add the Haze Effect to a Zone](#add-the-haze-effect-to-a-zone)

## Prerequisites

Consider getting familiar with the following concepts before starting this tutorial:

- [Create New Entities](../create-entities)
- [Change How Entities Look](../entity-appearance)

## Create a Zone Entity

To create a zone entity:

1. In Interface, pull up your HUD or Tablet and go to **Create**.
2. Click the 'Zone' icon to create a zone entity. You'll see a wireframe shape showing the zone's bounding box. 
3. If you are unable to view the zone's bounding box, go to **Edit > Show Zones in Create mode** and select the option. Your zone should now be visible.
4. Go to the 'Properties' tab, and add a name 'Zone-1' for your zone. This is an optional step. We are adding a name to make it easier to find the zone in the 'Entity List' window. 

>>>>> You cannot select a zone entity, like how you would select other entities. To find or select your zone entity in your 'Entity List' window, search for the zone using its name. If you haven't named your zone, click on zones with no names to find yours.


## Create Nested Zones with Different Lighting

Each zone entity you create can have different properties. When your avatar moves through different zones, you will experience each zone's properties. In the case of nested or overlapping zones, you will experience the properties of the smallest zone you are currently inside.

You can understand how an avatar experiences lighting in a zone using this mini tutorial:
1. [Create Two Zone Entities](#create-two-zone-entities)
2. [Nest One Zone Inside the Other](#nest-one-zone-inside-the-other)
3. [Add Different Lighting Effects to Each Zone](#add-different-lighting-effects-to-each-zone)

### Create Two Zone Entities

Follow the steps to [create a zone entity](#create-a-zone-entity) to create two zone entities named 'Zone-1' and 'Zone-2'.

>>>>> By default, zone entities are created at your current position, so to see the zone entities you just created, you may need to reposition your avatar.

### Nest One Zone Inside the Other

To nest a zone, you have to resize one zone to make it smaller than the other, and change its position to bring it inside the larger zone. 
1. In the 'Entity List' window, select 'Zone-1'.
2. In the 'Properties' tab, change the dimensions of 'Zone-1' to `x=5, y=10, z=5`.
3. If you created both zones without moving your avatar, you don't need to change the zone's position. 'Zone-1' will already be inside 'Zone-2'. If you moved while creating the zones, select 'Zone-1' and move it inside 'Zone-2'.

### Add Different Lighting Effects to Each Zone

When you create a zone, it inherits the properties of the zone your avatar was standing in. This means that both zones inherit the lighting properties of your domain. You won't notice when you are entering or leaving a zone. 

All lighting effects have three modes:

+ Inherit: The property is inherited from the zone bounding the current zone.
+ Off: The lighting effect is turned off.
+ On: The lighting effect is turned on and can be changed to values of your choice. 

The keylight represents a parallel source of light, such as the sun. Let's change the keylight properties for each zone:
1. In the 'Entity List' window, select 'Zone-1'.
2. In the 'Properties' tab, change the 'Key Light' property by selecting 'On' from the drop-down.
3. Click on 'Key Light' color, and add these RGB (`255,0,0`) values to add a red key light. 
4. In the 'Entity List' window, select 'Zone-2'.
5. In the 'Properties' tab, change the 'Key Light' property by selecting 'On' from the drop-down.
6. Click on 'Key Light' color, and add these RGB (`0,0,255`) values to add a blue key light. 

When your avatar walks from Zone-1 to Zone-2, you will see the lighting around change from red to blue. 

## Change a Zone's Shape

By default, a zone's shape is a cube, like its bounding box. You can change a zone's shape to the following:

+ None: This will be the default shape (cube).
+ Box: The zone's shape will be a box. 
+ Sphere: The zone entity's shape will be a stretched sphere.
+ Compound: The zone entity's shape will be a convex mesh. 

All shapes will be stretched to fit the zone entity's dimensions.


## Add a Skybox to a Zone

A skybox determines the texture of the sky in your domain. The skybox can be just a color, or an image from a URL. For example, you can have a blue sky or use an image of a the night sky with stars as a skybox. 

To add a blue sky to your zone: 
1. In the 'Entity List' window, select 'Zone-1'.
2. In the 'Properties' tab, change the 'Skybox' property by selecting 'On' from the drop-down.
3. Click on 'Skybox' color, and add these RGB (`0,0,255`) values to add a blue key light. 

To add an image of the night sky to your zone:
1. Host your image on a cloud service and copy the URL.
2. In the 'Entity List' window, select 'Zone-1'.
2. In the 'Properties' tab, change the 'Skybox' property by selecting 'On' from the drop-down.
3. Add the image URL to the 'Skybox URL'.



## Add Ambient Light to a Zone

The ambient light is provided by a cubemap centred around the avatar. The intensity can be set, as well as the URL. For example, let's change the ambient intensity to 1. You can also do this by changing the ambient URL.

## Add the Haze Effect to a Zone
The haze effect simulates atmospheric absorption by water vapour and dust. Haze has a relatively large number of parameters to simulate the different aspects of atmospheric attenuation. You can modify these properties to see how it affects your domain.

| Property | Description |
| --------- | ------------ |
| Range | The range is the horizontal range that visibility is reduced by 95%. In other words, at this range, 95% of a pixel’s colour is the haze colour (the other 5 being the pixel’s original colour).|
| Use Altitude | If this is checked, then the haze effect will decrease with altitude; otherwise, the haze is constant. The Base/Ceiling parameters are only used in this mode. |
| Base/Ceiling | The Base defines the altitude where the haze density is as defined by the Range parameter. The Ceiling defines the altitude where the haze density has decreased by 95%. |
|Haze Color |This is the colour that is blended into the image as the range to pixels increases. This is normally a bluish-grey colour. |
|Background Blend | The background (i.e. the skybox) is very far away. The result of this is that the background image would always be obscured if any level of haze was active. To mitigate this effect, the background image may be blended back into the image. When set to 1.0, the background appears as if haze is not enabled.|
|Enable Glare |This checkbox enables an additional aspect of haze, the effects of haze on the sun. |
|Glare Color |When looking away from the sun (i.e. the Keylight direction) the haze will have the haze colour. This will change to the glare sun as the view direction approaches the sun. |
|Glare Angle|Defines the (solid) angle from the sun that the haze colour and glare colour are blended 50%. |


**See Also**

- [Create New Entities](../create-entities)
- [Change How Entities Look](../entity-appearance)