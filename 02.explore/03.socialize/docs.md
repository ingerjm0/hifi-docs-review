---
title: Socialize with Others
taxonomy:
    category: docs 
---
High Fidelity is all about the people you meet and the experiences you have with them. High Fidelity enables people connected by interest, community, and friendship to come together from anywhere in the world.

**On This Page:**
* [Make Connections and Friends](#make-connections-and-friends)
  * [The People App](#the-people-app)
  * [Your Privacy Bubble](#your-privacy-bubble)
* [Attend Live Events](#attend-live-events)
* [Express Yourself](#express-yourself)
  * [The Emote App](#the-emote-app)
* [Give and Receive Gifts](#give-and-receive-gifts)
  * [Send HFC to Others](#send-hfc-to-others)
  * [Send Purchased Items to Others](#send-purchased-items-to-others)
  * [Create a Coupon](#create-a-coupon)
* [Chat with Users](#chat-with-users)
  * [HiFi Local Chat](#hifi-local-chat)
  * [Com Script Version 1](#com-script-version-1)
  * [Sign Post Chat](#sign-post-chat)
  * [Run External Chap Apps in Local Browser](#run-external-chat-apps-in-local-browser)

## Make Connections and Friends

In High Fidelity, you can establish a connection with someone else by shaking hands with them. With your hand controllers, place your hands near each other and hold the grip button. Desktop users can press and hold <kbd class="keyboard">X</kbd> on their keyboard. 

Once you make a connection with someone, they will appear under Connections in the [**People** app](#the-people-app). You will also appear on their list of connections. You will be able to see where they are in the metaverse, and you can travel to them at any time. 

To mark a connection as a friend, check the box next to their name in the People app. ![](make-connection.png)

### The People App

The People app provides a set of tools that help users manage their interactions with people in the metaverse. It gives you a list of the people nearby (in the same domain as you), and gives you easy access to all of your connections. From the People app, you can: 

* Change your availability
* Toggle your visibility between friends, connections, and the entire community
* Set the master volume for the domain you're in
* Teleport directly to a friend's location
![](people-nearby.png)

### Your Privacy Bubble

You can enable a privacy bubble that protects your personal space in the metaverse. When it is enabled, other people will disappear if they get too close to you. Your privacy bubble is disabled by default. To enable it, pull up your tablet or HUD and click **Bubble**.
![](privacy-bubble.png)

## Attend Live Events

One of the great things about virtual reality is that you can attend events. High Fidelity regularly hosts events such as workshops, lectures on VR, and town hall meetings to meet our team. Click here to [view all upcoming events](https://tockify.com/hifieventscalendar/agenda), Events are a great place to meet others and share experiences with others around the world.

To attend an event, simply go to the hosted domain at the time of the event.

## Express Yourself

There are many ways you can express yourself in High Fidelity, such as animating the mouth of your avatar or using gestures in the **Emote** App. 

By default, all avatars will use a standard set of animations, such as your eyes blinking or your mouth opening and closing as you talk. When you are using a VR controller, your avatar will automatically mimic your hand gestures and movements. 

### The Emote App

The Emote app is a way for desktop users to express themselves without using VR controllers. With this app, you can display feelings by: crying, acting surprised, dancing, cheering, waving, falling, pointing, clapping, sitting, or showing love. ![](emote-app.png)

## Give and Receive Gifts

Just like in real life, you can give money or presents to your friends in High Fidelity. You may wish to gift an item to a friend, send money to a connection, have a VIP zone in your domain, or play a poker game with your friends. 

With the Commerce API, you can also award money or items using a coupon. A _coupon_ is a way to send HFC or items to someone at a later time, even when you are not logged in to High Fidelity. For example, you can create a coupon to award the winner of a trivia game 250 HFC, or to give someone a soda when they buy something from a vending machine.

### Send HFC to Others

To send money to a connection or someone nearby:
1. In Interface, pull up your tablet or HUD and go to **Inventory**.
2. In the **Inventory** app, click 'Send Money'. ![](send-money.PNG)
3. Send money to one of your connections or even someone nearby in the same domain.  
	* If you want to send it to one of your connections, click 'Connections; and choose the recipient from the list.
	* If you want to send it to someone nearby, click 'Someone Nearby' and choose your recipient by triggering or clicking on someone nearby to select them. ![](nearby.PNG)
4. Add the amount you wish to send. This amount should be less than or equal to your HFC balance. 
5. You can add an optional public message. Click 'Submit'. 
6. A window pops up confirming that your money has been sent. 

### Send Purchased Items to Others

After you [buy something from the Marketplace](../bank-and-shop#shopping-the-marketplace), you can give it to a connection or someone nearby. To do so: 
1. In Interface, pull up your tablet or HUD and go to **Inventory**.
2. In the Inventory app, click 'Items'. ![](items-tab.png)
3. Scroll to the item you'd like to give and click on the menu. ![](item-menu.png)
4. Select 'Gift'. ![](gift-item.png)
5. Send the item to one of your connections or even someone nearby in the same domain. 
	* If you want to send it to one of your connections, click 'Connections' and choose the recipient from the list.
	* If you want to send it to someone nearby, click 'Someone Nearby' and choose your recipient by triggering or clicking on someone nearby to select them. ![](nearby.PNG)
6. You can add an optional public message. Click 'Submit'. 
7. A window pops up confirming that your item has been sent.  

>>>>>When you send an item to another user, it is removed from your **Inventory**.

### Create a Coupon
You can create a coupon when you want to send money or an item to someone at a later time, even when you are not logged in to High Fidelity.  
>>>> Currently, you can only use a coupon in a script. You will not be able to redeem a coupon anywhere in Interface.

1. In Interface, pull up your tablet or HUD and go to **Inventory**.
2. Choose whether you'd like to later send HFC or an item.
	* If you want to send HFC, click 'Send Money'.
	* If you want to send an item, click 'Items' and scroll to the item you'd like to give. Click on the item's menu and choose 'Gift'.
3. Select 'Create Coupon'.
4. Enter an optional public message explaining the purpose of the coupon. 
5. The Tablet will now display a window with the 'Authorization ID' and 'Coupon ID'. Copy both these values on your computer. Click 'Close'.
6. Include the copied values in a [script where another user receives the HFC or item](../../script/transfer-hfc-tutorial).
![](create-coupon.png)

**Example: Use a Coupon to Hold a Raffle**  

Say you want to pre-authorize 10 of your High Fidelity Coins to be paid out to a user who wins a raffle that you host. In this example, [curl](https://curl.haxx.se/) is used to perform the redemption. But you can redeem a pre-authorized transfer using any script or tool that can perform `HTTP PUT` requests, such as High Fidelity Interface's `request` JavaScript module or a simple PHP form on a website.

1. [Create a coupon](#create-a-coupon) to get an 'Authorization ID' and 'Coupon ID' value pair associated with a 10-HFC Pre-Authorized Money transfer.
2. Copy and paste the 'Authorization ID' and 'Coupon ID' to a text file on your computer.
3. Click 'Close', then 'I'm All Set'.
4. Hold your raffle! In this example, a user with username `steve` has won the raffle.
5. Use the following `curl` command from the command line to dispense the money authorized in (1) to username `steve`:
   1. `curl -X PUT -d authorization_id=<authorization ID from 1> -d coupon_id=<coupon ID from 1> -d username=steve https://highfidelity.com/api/v1/commerce/redeem`


## Chat with Users

High Fidelity doesn't yet have a default text chat option that works well for both HMD and desktop users as most HMD users can't type easily. Our extensible open-source scripting and UI gives you the ability to create the features you want, including text chat. There are some great scripts for chat that have already been built by community members, and a few are described below.

### HiFi Local Chat 

This clean, reliable, and well-written chat script was created by alpha user ctrlaltdavid. 
![](hifi-local-chat-by-ctrlaltdavid.png)
To run the script:

1.  In Interface, go to **Edit > Open and Run Script from URL**.
2. Paste the URL http://ctrlaltstudio.com/downloads/hifi/scripts/chat.js.

The script will start running and you’ll see a text chat window pop-up, enabling you to chat with other users in the same domain who are running the same script. If text chat’s important to you, you might want to add this to your default scripts so it’s always there.
![](chat-screenshot.png)

### COM Script Version 1

AlphaVersionD has authored an equally powerful and friendly script that runs on a domain. This means users just need to visit the domain in which the script is running, and do not have to run anything themselves. For example, if you want everyone in your domain to be able to chat, you can run this script. 

To install COM Script in your domain:

1. In Interface, pull up your HUD or Tablet and go to **Create**. 
2. Click the 'zone' icon to create a zone entity.
3. In the 'Properties' tab of the zone entity, paste this [URL](http://metaversecafes.com/HighFidelity/QueenCity/A_2016_Q_wab/AQUI/COM_v1.0.j)

COM Script version 1 is now running in the zone in your domain!

### Sign Post Chat

![](sign-chat-by-menithal.jpg)

The Sing Post Chat app allows you to communicate with HMD users using a simple entity. This entity behaves like a sign with text as shown in the images.

Get Sing Post Chat in the [marketplace](../../../marketplace/buy).


### Run External Chat Apps in Local Browser

You can also use external browser based chat applications of your choice in High Fidelity. 

1. Launch a local web browser in High Fidelity by pressing <kbd class="keyboard">Ctrl</kbd>-<kbd class="keyboard">B</kbd>.
2. Run the external chat app of your choice such as WhatsApp Web or  Slack. It works great, even in your HMD. While it might not be ideal for random chat encounters, it can be quite handy when larger groups (like colleagues and classmates) need a way to keep in touch without breaking immersion.

![](whatsapp.png)

**See Also**

+ [Bank and Shop](../bank-and-shop)
+ [Tutorial: Transfer Money and Items](../../script/transfer-hfc-tutorial)