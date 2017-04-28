# xivbar
This addon displays vital bars for easy tracking

![alt text](http://i.imgur.com/QA6WSUY.png)

You can choose from 2 different styles 'ffxiv' and 'ffxi':
![alt text](http://i.imgur.com/Ilol46V.png)

and you can use a compact version for a smaller resolution:
![alt text](http://i.imgur.com/tnxBCLL.png)

## How to install:
1. Download the repository [here](https://github.com/SirEdeonX/FFXIAddons/archive/master.zip)
2. Extract the **_xivbar_** folder to your **_Windower4/addons_** folder

## How to enable it in-game:
1. Login to your character in FFXI
2. Press insert to access the windower console
3. Type ``` lua l xivbar ```

## How to have windower load it automatically:
1. Go to your windower folder
2. Open the file **_Windower4/scripts/init.txt_**
3. Add the following line to the end of the file ``` lua l xivbar ```

## How to edit the settings
1. Login to your character in FFXI
2. Edit the addon's settings file: **_Windower4\addons\xivbar\data\settings.xml_**
3. Save the file 
4. Press Insert in FFXI to access the windower console 
5. Type ``` lua r xivbar ``` to reload the addon
6. Press Insert in FFXI again to close the windower console

### Available Settings
* Compact - true/false - sets compact mode
* Offset X - any number - move the bar left (negative number) or right (positive number) the given number of pixels
* Offset Y - any number - move the bar up (negative number) or down (positive number) the given number of pixels
* Style - ffxi/ffxiv - changes the style of the bars

There are also other settings you can change such as text colors.
