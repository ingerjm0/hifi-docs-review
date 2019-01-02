---
title: Avatar Scripts
taxonomy:
    category: docs
---
Avatar scripts are bound to an avatar. This means that they run when a user puts on a specific avatar. Likewise, avatar scripts stop running when the avatar is removed or changed. Other users in the domain will be able to see the script in action, but they will not be able to run the script themselves.	

With avatar scripts, you can do things like make your hair flow or create particle clouds around your avatar.

**On This Page**
* [Add an Avatar Script](#add-an-avatar-script)
* [Example of an Avatar Script](#example-of-an-avatar-script)

## Add an Avatar Script
There are two different ways you can add an avatar script to your FST file: either by using our Package Model tool or by manually adding the script.

To add an avatar script using the Package Model tools: 
1. Create a folder called `scripts` in the same location as your FBX file.
2. Copy your avatar script into this new folder.
3. In Interface, go to Edit > Package Model as .fst
4. For Script Directory, enter the path to the `scripts` folder you created above. 

To add an avatar script manually:  
1. Open the FST file for your avatar in the text editor of your choice.  
2. Add a line telling the avatar where to find the script file using the syntax `script = [SCRIPT URL]`.![](add-script.png)

>>>>> You can add multiple scripts to your avatar by adding multiple `script = url` lines.

