---
title: Avatar Standards Guide
taxonomy:
    category: docs
---

This document outlines the standards you should follow when [creating your avatar](../). Your avatar uses bones to animate the character's limbs and define the scale variable of limbs. You can add custom bones to further adjust the avatar's shape. Customization of your avatar can be fine-tuned using blendshapes to animate the face and scripting to define advanced behaviors.

**On This Page:**
* [Reference Pose](#reference-pose)
* [Skeleton](#skeleton)
* [Flow Bones](#flow-bones)
* [Look-at Vectors](#look-at-vectors)
* [Blendshapes](#blendshapes)
* [Other Considerations](#other-considerations)


## Reference Pose

For the Reference pose, use a T-Pose which complies with the specifications below. You may wish to refer to the properly configured example avatar fbx with source files.
- The character must face along the positive direction of the Z-axis.
- The arms must be spread along the X-axis. The left arm should therefore be pointing along the positive direction of the X-axis.
- The top of the character's head must be up, in the positive direction of the Y-axis.
- The character's hands are flat, palms facing the ground, with the thumbs parallel to the X axis.
- The character's feet need to be perpendicular to the legs (with the toes pointing along the Z-axis as shown). The feet must not be rotated around the Y-axis (meaning the toes of the left foot should not point inward toward the right leg or outward away from the right leg).

![](hifi-skel.png)

You can download the standard High Fidelity skeleton [here](http://hifi-content.s3.amazonaws.com/Examples%20Content/skeleton/standard_hifi_skeleton.fbx). This skeleton conforms to the specifications above.

## Skeleton

The standard humanoid skeleton of your avatar should follow [HumanIK Skeleton](http://download.autodesk.com/global/docs/maya2014/en_us/index.html?url=files/GUID-945BCFFE-A772-4D52-87B8-FCFC50C974FB.htm) with some modifications made for Mixamo. This skeleton system will work with the input systems already in place in High Fidelity, and will allow users to use their input devices to control their avatar's arm and finger movements (if they have any). 

High Fidelity avatars should match the following standard skeletal structure. Each of these joints can be animated.

>>>>>Finger #1 is not the metacarpal; instead, it is the first joint between the [proximal and intermediate](https://en.wikipedia.org/wiki/Finger#/media/File:Scheme_human_hand_bones-en.svg). 

- Hips
    - LeftUpLeg
        - LeftLeg
            - LeftFoot
                - LeftToeBase 
    - RightUpLeg
        - RightLeg
            - RightFoot
                - RightToeBase
    - Spine
        - Spine1
            - Spine2
                - Neck
                    - Head
                        - LeftEye
                        - RightEye
                - LeftShoulder
                    - LeftArm
                        - LeftForeArm
                            - LeftHand
                                - LeftHandThumb1 
                                    - LeftHandThumb2 
                                        - LeftHandThumb3 
                                - LeftHandIndex1
                                    - LeftHandIndex2
                                        - LeftHandIndex3
                                - LeftHandMiddle1 
                                    - LeftHandMiddle2 
                                        - LeftHandMiddle3 
                                - LeftHandRing1 
                                    - LeftHandRing2 
                                        - LeftHandRing3 
                                - LeftHandPinky1 
                                    - LeftHandPinky2 
                                        - LeftHandPinky3 
                - RightShoulder
                    - RightArm
                        - RightForeArm
                            - RightHand
                                - RightHandThumb1 
                                    - RightHandThumb2 
                                        - RightHandThumb3 
                                - RightHandIndex1
                                    - RightHandIndex2
                                        - RightHandIndex3
                                - RightHandMiddle1 
                                    - RightHandMiddle2 
                                        - RightHandMiddle3 
                                - RightHandRing1 
                                    - RightHandRing2 
                                        - RightHandRing3 
                                - RightHandPinky1 
                                    - RightHandPinky2 
                                        - RightHandPinky3 

### Flow Bones

The  `sim` prefix is reserved for flow bones, such as clothing, hair and tails. These bones should _not_ be animated by an animator. ![](flow-bones.png)

For example, consider a full cape that surrounds the avatar: 

>simBackCape1 - first bone of the cape, center back  
>simBackCape# - additional bone(s) of the cape, center back  
>simFrontCape1 - first bone of the cape, center front  
>simFrontCape# - additional bone(s) of the cape, center front  
>simLeftCape1 - first bone of the cape, left  
>simLeftCape# - additional bone(s) of the cape, left  
>simRightCape1 - first bone of the cape, right  
>simRightCape# - additional bone(s) of the cape, right  

Alternatively, you can use the `flow` prefix, separating the name and joint number with an underscore. The same cape as above would look like:

>flow\_BackCape\_01  
>flow\_BackCape\_02  
>flow\_FrontCape\_01  
>flow\_FrontCape\_#  
>flow\_LeftCape\_01  
>flow\_LeftCape\_#  
>flow\_RightCape\_01  
>flow\_RightCape\_#  

## Look-at Vectors

The look-at vectors are driven by the z-vector of the eye joints.

The +z axis of the eye joints should go through the center of the pupil, and should continue to do so as the eye joint is rotated.

The eye joints are defined in the FST.

## Blendshapes

High Fidelity uses Blendshapes to animate your avatar's face. Blendshapes allow you to specify a new state for your avatar's mesh, and facial positions are animated by moving between the different states of your avatar's expressions. Blendshape behaviors are defined in your avatar's FST file, and are added to the avatar mesh using a 3D modeling tool like Blender (Shape Keys) or Maya. Adobe's Fuse program and Mixamo pipeline allow you to export blendshapes as part of your FBX, but if you are modeling an avatar from scratch, you will likely need to specify your own facial expressions.

High Fidelity avatars support a number of blendshapes for creating different facial expressions.

**Basic Blendshapes**  
- `EyeBlink_L`:  Blinking action for the left eye.
- `EyeBlink_R`: Blicking action for the right eye.
- `JawOpen`: Opening of the jaw.

**Audio Blendshapes**  
These blendshapes are used when you speak. 

Your eyebrows are blendshapes that react to a change in volume. They will move upwards when your voice gets louder. These include:
- `BrowsU_C`: Center of the brow going up
- `BrowsU_L`: Outside corner of the left brow going up
- `BrowsU_R`: Outside corner of the right brow going up

Other audio blendshapes are randomly mixed when you speak. These include:
- `MouthSmile_L`: Left side of the mouth lifting up to a smile
- `MouthSmile_R`: Right side of the mouth lifting up to a smile
- `LipsFunnel`: Funneling of the lips, as when you say "Oh!"
- `LipsUpperClose`:  Upper lips rolled inwards

**Eyelid Offset**
To ensure that the top of the eyelid rests on the iris, blendshapes are used to track the current position of the eye along with your head orientation. We apply a small offset to these blendshapes to preview sleepy or crazy eye lids.
- `EyeBlink_L`: Blinking action for the left eye
- `EyeBlink_R`: Blicking action for the right eye
- `EyeOpen_L`: Opening of left eye
- `EyeOpen_R`: Opening of right eye
- `BrowsD_L`: Outside corner of the left brow moving down
- `BrowsD_R`: Outside corner of the right brow moving down

Tweaks to your blendshapes can be made in your 3D modeling tool, or directly in the FST file. In the FST file, blendshapes are defined with the syntax: 

>bs = [blendshape constant] = [your key/blendshape name] = [value between 0 and 1]

Here is an example of modifying your blendshapes in your FST file:

>bs = BrowsU_L = head_BS_brow_up = 0.3  
>bs = BrowsU_C = head_BS_brow_up = 0.3  
>bs = BrowsU_R = head_BS_brow_up = 0.3  
>bs = BrowsD_R = head_BS_brow_down = 0.5  
>bs = BrowsD_L = head_BS_brow_down = 0.5  
>bs = EyeBlink_L = head_BS_L_eye_close = 1  
>bs = EyeBlink_R = head_BS_R_eye_close = 1  
>bs = EyeOpen_L = head_BS_L_eye_open = 1  
>bs = EyeOpen_R = head_BS_R_eye_open = 1  
>bs = JawOpen = JawOpen = 1  
>bs = MouthSmile_R = head_BS_L_smile = 0.6  
>bs = MouthSmile_L = head_BS_R_smile = 0.6  
>bs = LipsFunnel = head_BS_oo = 0.5  
>bs = LipsUpperClose = head_BS_mouth_down = 0.1  

## Other Considerations

#### File Optimization
Content creators will have limited bandwidth on servers (read small print on any unlimited host plans) so optimization is important, for both the end users and content creators. The more polygons and larger textures you use, the more bandwidth you are using from your servers per load. Optimally, keep your avatar models under 20 mb.

#### Textures
We recommend that you try to keep total size of all the textures per avatar below 8 mb. They should be always smaller than 1024x1024, unless all the textures are in a single file. If using multiple texture files, then smaller the better, especially if you can make the textures smaller. Remember that you can get a lot more detail through roughness and normal mapping, than just textures. It is suggested that you keep Albedo at a smaller size than your roughness for best detail through light reflection instead of color variation.
