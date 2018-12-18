---
title: Define an Entity's Behavior
taxonomy:
    category: docs
---

An entity's behavior controls its interactions with other entities and avatars in High Fidelity. Can an entity be grabbed, does it collide with other entities and avatars, or can a change in the domain's gravity affect it? You can check and change an entity's behavior by editing its properties.

**On This Page:**

+ [Dynamic Entity Behavior](#dynamic-entity-behavior)
+ [Entity Collision Behavior](#entity-collision-behavior)
+ [Entity Grabbing Behavior and Triggers](#entity-grabbing-behavior-and-triggers)
+ [Other Entity Properties](#other-entity-properties)

## Dynamic Entity Behavior

You can make an entity dynamic if you want your entity to be affected by the physics in a domain. For instance, if you want a box entity in your domain to react to a change in gravity, you can do so by making the entity dynamic. If an entity is not dynamic, it is static. A static entity has no gravity and no velocity. It can only be moved by a user.  

For an entity to have collision behavior, it needs to be dynamic. To make an entity dynamic:

1. In Interface, pull up your HUD or Tablet and go to **Create**.
2. Select your entity on the Entity List window or just click on it. 
3. Go to the Properties tab, scroll down to "Collisions" and check "Dynamic".



## Entity Collision Behavior

When an entity has no collision properties, it moves through other entities and avatars like it's not a solid object. For an entity to collide with another entity or avatar, its collision properties need to be changed. 

To change an entity's collision properties, you need to go to an entity's properties page. 

1. In Interface, pull up your HUD or Tablet and go to **Create**.
2. Select your entity on the Entity List window or just click on it. 
3. Go to the Properties tab, scroll down to "Collisions" and check "Collides".

You need to set how your entity behaves when it collides with certain entity types. Under Collisions, if you check:

| Collides With      | Description                                                  |
| ------------------ | ------------------------------------------------------------ |
| Static Entities    | Your entity will collide with static entities. Keep in mind that if your entity is a static entity, it will not collide with another static entity. Only a dynamic entity can collide with a static entity. |
| Kinematic Entities | Your entity will collide with kinematic entities. Kinematic entities have velocity, but are not dynamic. Their behavior is controlled by an external script. |
| Dynamic Entities   | Your entity will collide with dynamic entities.              |
| My avatar          | Your entity will collide with your avatar.                   |
| Other avatars      | Your entity will collide with other user's avatars.          |

![](collision.png)

## Entity Grabbing Behavior and Triggers

Your entity's grabbing properties determine how it behaves when you or another user interacts with it. By default, **Grabbable** and **Follow Controller** are checked. 

In your entity's Properties, if you select:

| Behavior          | Description                                                  |
| ----------------- | ------------------------------------------------------------ |
| Grabbable         | You or other users can grab this entity.                     |
| Follow Controller | Select to make your entity follow the movements of your hand controller instead of your avatar's hands. If your avatar arms are shorter than your real arms, your entity will be grabbed where the controller is (at a distance from your avatar's hands). |
| Triggerable       | Your entity can trigger a script. For instance, you can trigger a cube entity to run a script asking for a tip every time you click the entity. |

![](grab-behavior.png)

## Other Entity Properties

In your entity's Properties, if you select:

| Property                          | Description                                                  |
| --------------------------------- | ------------------------------------------------------------ |
| Cloneable                         | Your entity can be cloned. You can change the Clone settings to manipulate your entity's behavior. |
| *Cloneable:* Clone Lifetime       | Select this option to set how long (in seconds) your clone will exist. |
| *Cloneable:* Clone Limit          | Select to set a limit to how many clones you can create.     |
| *Cloneable:* Clone Dynamic Entity | Select to make the clone entity a dynamic entity.            |
| *Cloneable:* Clone Avatar Entity  | An avatar entity doesn't exist in the Entity Server. Instead, it is specific to a user's Interface client. Select to specify if a cloned entity is created as an avatar entity. For instance, say a user comes to visit the coffee shop in your domain. The user grabs a coffee cup that's been cloned. Once the user is done visiting, the cloned entity leaves with their avatar, ensuring there isn't any clutter left behind. This feature ensures that your entity is cloned locally for each avatar. |
| Cast Shadows                      | Your entity will cast a shadow in your domain.               |









