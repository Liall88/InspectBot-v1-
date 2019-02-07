# InspectBot-v1-
App for InspectBot (v1)

INSPECTBOT V1
App named SBotApp
Created by Liall Arafa 18/04/17 
Queen Mary University London
Undergraduate Project

Please read the thesis included in the project for more detailed information. 


PROJECT AIMS:
This project aims to understand the fundamentals of machine vision and robotics, and utilise both of these techniques to program an effective automated inspection robot (InspectBot) to be used in a warehouse environment. 

WHAT IS INSPECTBOT?

InspectBot is a warehouse robot that utilises a multitude of sensors to autonomously patrol a warehouse environment on an unset path, use colour blob detection to search for warehouse objects, and scan the identification QR codes in order to determine that object. It utilises infrared sensors to autonomously navigate the area and uses machine vision to process images captured by the camera to look for a particular colour blob that will be placed on a special tag on warehouse objects. If the colour blob is detected, InspectBot will then navigate to the warehouse object, orientate to face the object, and scan the QR identification code placed on them. The QR code returns a message indicating what the item is. The QR code message indicates what the item is. 


MAIN IMPLEMENTATION CLASSES:

PatrolDetectFollow .java – This class/activity is responsible for InspectBot autonomous navigation, robotic control, and takes the image processing results from ColorBlobDetector.java and updates the InspectBot state accordingly in the OnWheelphoneUpdate() method. The target HSV colour is set in this class. A ColorBlobDetector object is initialised, which containts the contours on the image in an attribute. If a colour blob is detected, the activity is swapped to QR scanning, in QRScan.java. This activity is run when the “(V1) PATROL, DETECT, SCAN” button on the main activity screen is clicked. 

ColorBlobDetector.java – This class is responsible for image processing.  It detects the colour blob and its contours. An object of type ColorBlobDetector is initialised in PatrolDetectFollow.java. 
QRScan.java – This class/activity is responsible for QR scanning. The activity runs after being started by PatrolDetectFollow.java. On successful scanning, it plays a test audio clip which represents InspectBot indicating to a human that it has located the target object. 

MainActivity.java – Presents the user with the main user interface on opening the app. Is equivalent to a main() method. 

TEST CLASSES:
ColorBlobDetectionActivity.java – This class/activity was used to test colour blob detection. It was implemented in PatrolDetectFollow.java.
 
SBInfraredPatrol.java- This class/activity was used to test infrared autonomous navigation. It was implemented in PatrolDetectFollow.java. 

SBBlobDetectAndFollowActivity.java- This class/activity was used to test the ability of InspectBot to colour blob detect and then navigate towards the colour blob successfully. InspectBot was not able to robustly follow the colour blob had contained bugs, detailed in the section below on page 35. Navigation was not implemented beyond this class. 

ThreadTimer.java – This class/activity was used to test thread time. It works successfully, but due to the limited time frame was not implemented beyond this class. 



BEFORE RUNNING: app is configured to run on targetSDKVersion 19 and minSDK Version 12.
If you want to run the app on other target API’s change the settings in the main build.gradle file. Make sure to download OpenCV Manager for the device to ensure running. Import the Wheelphone, OpenCV, ZXing libraries for Android. Machine vision capabilities and every other feature can be tested without the physical Wheelphone robot attached. Robotic capabilities must have the Wheelphone robot attached.  

TO TEST: download SBotApp.apk and run on target device.

CONTRIBUTORS: Code built upon WheelPhone, OpenCV and ZXing code examples

FOR MORE INFORMATION AND SUPPORT: contact liall88@gmail.com




