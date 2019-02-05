---
title: Add Sound to Entities
taxonomy:
    category: docs
---

You can create an audio file to play different types of audio in High Fidelity. These can be sounds entities make on collision with another object, or background music or ambient sounds. 

We currently support audio files in the following formats:
+ WAV
+ MP3

  

**On This Page**

+ [Add Collision Sounds](#add-collision-sounds)
+ [Add Ambient Audio](#add-ambient-audio)

## Add Collision Sounds

Entities have the ability to add a collision sound, so that the entity will emit a sound every time it comes in contact, or [collides, with another entity](../entity-behavior).

To add a sound:
1. In Interface, pull up your Tablet or HUD and go to **Create**. 
2. Select the entity. 
3. In the **Create** app, click on 'Properties' and scroll down to the 'Collision' settings. 
4. Check the box for 'Collides', then enter the URL of the audio file for 'Collision Sound'. 

### Tutorial: Create a Bouncing Ball
In this example, we will walk through the steps to create a bouncing ball that emits a sound every time it hits a wall.

1. Create a wall to bounce your ball off of.   
    a. [Add a cube entity](../create-entities) to your domain.  
    b. [Resize the entity](../entity-appearance#set-the-size-of-an-entity) to approximately 10m wide, 10m high and 1m deep (X:10, Y:10, Z:1).  
2. Create a ball by [adding a sphere entity](../create-entities) to your domain. Optionally, [change the color](../entity-appearance#change-the-color-of-an-entity) of your ball, so that it is different than your wall.  
3. In the **Create** app, click on 'Properties' and scroll down to the 'Collision' settings. Check the box for 'Collides' and 'Dynamic'.
4. For 'Collision Sound', enter the URL of your sound file. The sound can be a WAV or MP3 file. The URL can be either a web address, or an ATP reference to the assets on this domain server.  
5. Scroll down to the 'Physics' settings. Set the 'Gravity' for Y to -5. This will cause your ball to fall a little more slowly than things on earth (use -9.8 if you want that). Gravity is in units of m/s<sup>2</sup>.

As soon as you click off the ball, the gravity will cause the ball to fall downwards. When it hits the floor, it should stop or bounce a little and the sound should play.

## Add Ambient Audio

To add music or ambient sounds to your domain, you need to:

1. [Create an entity](#create-an-entity).
2. [Write a sound emitter script](#write-a-sound-emitter-script).
3. [Attach the script to the entity](#attach-the-script-to-the-entity).

### Create an Entity

This can either be a primitive shape like a cube or a sphere, or even a 3D model. For example, you can create a 3D model of a record player to play music in your domain.

1. In Interface, pull up your HUD or Tablet and got to **Create**.
2. Add the entity of your choice (model, box, or sphere).

### Write a Sound Emitter Script

This script controls how your sound file is played. For example, you can write a script for audio to played on loop, or only play for a specific time period. This is a [client entity script](../../../script/client-entity-scripts) and will be attached to your entity. 

You can use High Fidelity's [Audio namespace](../../../api-reference/namespaces/audio#.playSound) to write a sound emitter. We've written an example script below:

```javascript
var sound = SoundCache.getSound(Script.resourcesPath() + "sounds/sample.wav"); // Get the content of your audio file
var injector;
var injectorOptions = {
  position: MyAvatar.position // The position in the domain to play the sound. 
};

Script.setTimeout(function () { // Give the sound time to load.
  injector = Audio.playSound(sound, injectorOptions);
}, 1000);
```

### Attach the Script to an Entity

To have your audio play in your domain, you need to add the sound emitter script to your entity. 

1. In Interface, pull up your HUD or Tablet and go to **Create**.
2. Click on the entity you previously created to [edit its properties](../entity-appearance).
3. In the 'Properties' tab, scroll down to 'Script' and your script's path or URL.

You've added ambient audio to your domain! You can [sell the audio](../../../sell/add-item/upload-audio) you've created in the Marketplace. 

**See Also**

+ [Set Entity Behavior on Collision](../entity-behavior#set-entity-behavior-on-collision)

+ [Set How an Entity Moves in a Gravitational Field](../entity-physics#set-how-an-entity-moves-in-a-gravitational-field)

+ [API Reference: Audio](../../../api-reference/namespaces/audio)

+ [Client Entity Scripts](../../../script/client-entity-scripts)

  