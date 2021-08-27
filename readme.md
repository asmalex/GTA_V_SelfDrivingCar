GTA V Self Driving Car w/ Motion
======================
Feel the wind in your hair as you cruise through town, and hold tight for every bad LS driver, pothole, and the occasional stunt. Welcome to our GTA V self driving car experiment. There's no guarantees today as your driver is an autonomous car, written by 5 students and a professor in the cornfields of Mt. Pleasant, MI. Experience the thrills of autonomy in our motion simulator. The vehicle's full motion in the game is recreated in our simulator, so you actually feel like you are in the car! The training set is a loop focusing on Los Santos' inner-city southeast of the golf course. Note: the built-in GTA V driving AI *is not used* here. This model is trained based on the first person view from the driver's perspective, keyboard keypresses, and object avoidance from the YOLO model. If you feel you can help us improve our model, we welcome contributions. For more information, check out http://www.waynenterprises.com/ai-ml

**Please do not attempt to run the self-driving car in GTA V online. It is a violation of Rockstar's EULA and your account may be banned!**

:star: Star us on GitHub — it helps increase this project's visibility!

[![GTA V Self Driving Video](https://img.youtube.com/vi/NrPeC1ez-M4/0.jpg)](https://youtu.be/NrPeC1ez-M4)

## Developers
Name | Username | Contributions
------------ | ------------- | -------------
Evan Miller | gastastrophe | Machine Learning Model & Most Development
Michael Dahle | dahle1mr | GTA V Scripting & UDP API
Josh Gutowski | josh-gutowski | Team Member
Allan Bourke | bourk1af | Team Member
Ian Kraft | ianfraft | Team Member
Dr. Alexander Redei | asmalex | Motion Simulation

Credit to Iker García Ferrero - (ikergarcia1996) and Eritz Yerga Gutierrez - (eritzyg) for providing the intial source code. A lot of the pre-processing comes from their code at https://github.com/aidenyg/GTAV-Self-driving-car.

## Installation Instructions

Make sure you have the following installed. 

### Requirements
 - [Grand Theft Auto] (https://store.steampowered.com/agecheck/app/271590/)
 - [Anaconda] (http://www.anaconda.com/)
 - [OpenIV] (http://openiv.com/)

### Preparing GTA V
1. Navigate to your GTA V installation directory
1. Create a *mods* and *scripts* folder in the root GTA V installation directory
1. Copy the *update* folder to *mods* folder (so now it's in */mods/update*)
1. Move all **.rpf** files from root folder to *mods* folder (Note: they are alphabetical. Be sure to copy *common.rpf* too)
1. Copy the following files from **/_installME/GTA_Binaries_And_Scripts/binaries/** to root folder in GTA V
	 - *dinput8.dll* (yes, overwrite it if it already exists)
	 - *ScriptHookV.dll*
	 - *ScriptHookVDotNet.asi*
	 - *ScriptHookVDotNet2.dll*
	 - *ScriptHookVDotNet3.dll*
1. Copy the *GTAScriptHookPlugin.dll* file from */_installME/GTA_Binaries_And_Scripts/scripts* to the */scripts* folder in GTA V
1. Open OpenIV
1. Open the ASI Manager window (under Tools -> ASI Manager)
1. Install ASI loader and OpenIV.asi (they sould turn green. Leave openCamera off, it will appear blue)

### Preparing iPython Notebook
1. Open Anaconda Navigator
1. Open the **/Car/GTAV-Self-driving-car.ipynb**
1. Run the first three lines (this may take a while as new packages are installed
1. Run the rest of the notebook
1. Enjoy!

### Version Table
If you still encounter issues, here are the versions of software tested with this build:

Program | Version
------------ | -------------
Anaconda Navigator |  v1.10.0
Jupyter Notebook | v6.1.4
Python | v3.8.5 (Note: I created a seperate environment in Anaconda for this code)
keras | v2.4.3
Grand Theft Auto V | Steam Edition (Build ID 6337558)
OpenIV | v4.0.1
ScriptHook | v1.0.2245.0
ScriptHookDotNet | v3.1.0
Windows 10  | v2004, Build 19041.867
.NET 4 | v4.8 (only needed if building plugins from scratch, otherwise use the binaries in the */_installMe* folder)

NOTE: additional libraries are installed in the iPython script itself Make sure your imports work before proceeding to execute further parts of the code (warnings are OK, but errors are not)

## Developer Task List
- [x] Collect at least 2 hours of driving data around the training area
- [x] Get GTA V telemetry data forwarded to UDP using openIV scripting
- [x] Train a "good" model
- [x] Test model on city driving
- [ ] Test model on country driving
- [ ] Test self-driving car with person in it

## GTA V Training Loop
The training set is a loop focusing on Los Santos' inner-city and is southeast of the golf course as shown in the map below.
![GTA V Training Loop](https://images.squarespace-cdn.com/content/v1/530c18dce4b0ef6b47240ccd/1615399769205-2AXTPCIT2RNGCBGV0WFO/ke17ZwdGBToddI8pDm48kEEWbSSq0YMxZZqmOBygHs97gQa3H78H3Y0txjaiv_0fDoOvxcdMmMKkDsyUqMSsMWxHk725yiiHCCLfrh8O1z5QHyNOqBUUEtDDsRWrJLTmXGCBAtJNnIca4W5TlG2kqi0bewBMu0JBqWXANkeZNn10V7Thbgh94toP_60xLe-X/Map.PNG?format=750w)
