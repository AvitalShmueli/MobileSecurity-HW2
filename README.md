
# HW2 - Mobile Security

Home Assignment Exercise for Mobile Security course, in Afeka - the academic college  
of Engineering in Tel Aviv.

## Overview

In this assignment we were asked to decompile an APK of an app and fix the code so the app will run correctly.  In order to do so, I decompiled the APK and created a new project in Android Studio, copying only the necessary files to my project and fixed some bugs.

The app's name is "Survive Game". To start the game you need to enter your ID number and then guess the arrows pattern in order to survive and get to your city.
The city is based on the 8th digit of your ID.

## The fixes

I have copied the following files:
1. <ins>java files:</ins>
   - Activity_Game
   - Activity_Menu

2. <ins>layout files:</ins>
   - activity_game.xml
   - activity_menu.xml

3. <ins>drawable files:</ins>
   - ic_down.xml
   - ic_left.xml
   - ic_right.xml
   - ic_up.xml

I added a new string to the strings.xml file - I copied the value of "url" from the decompiled values file. When I copied this value I noticed that the url is corrupted and that few invisible characters were added to the url. I removed the unnecessary characters and checked the url in the browser.

I examined the manifest of the decompiled APK and saw that it uses INTERNET permission so I added INTERNET permissions to the manifest of my project.

In the Activity_Menu  file I fixed the argument of the notification length of the Toast function to LENGTH_LONG (instead of 1).

I also added a validation on the start game button that checks if the length of the ID is different than 9 to prevent the app from crushing. 
