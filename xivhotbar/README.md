# xivhotbar - [WIP]
This addon adds a hotbar to FFXI, akin to those of more modern MMOs, along with recast times and mp/tp costs. It can also trigger custom commands.

![alt text](http://i.imgur.com/RnpVLbZ.png)

## WIP Version 
This is a very simple version with a lot of features still missing and A LOT of bugs.

#### Latest Changes:
```
 08/05/17
    - fixed job change and battle notice bugs. 
    - added PSDs for custom icons to repository
 07/05/17
    - released WIP version
 ```

#### Limitations:
1. Please note that if you have more than one character with the same name under the same account, even if they're from different servers, the hotbars will be overwritten.
2. The addon still doesn't recognize if you're writing in chat or not and will continue to activate the actions when the buttons are pressing. To write freely in the chat, hide the hotbar by pressing the backslash \\ key
3. The addon still doesn't have commands, so you're gonna have to edit your hotbar directly through the xml. I left my hotbar as an example in **_data/hotbar/Edeon_**
4. The addon still doesn't override the game's keys. So when activating the third hotbar with CTRL, the macro bar ingame will show and activate too. To go around it, you can use an empty macro page.
5. The skill icons and info used were copied from the Timers plugin (you don't need to have it installed). As such, there are some icons that don't work and wrong elements on some skills
6. 2hours recast is not working

####Still todo:
1. Add key mapping
2. Add commands 
3. Allow number of hotbars to be customizable
4. Add click events
5. Add option to disable autoswitching in battle
6. Fix wrong icons / elements
7. Add skillchain info
8. Allow vertical hotbars
9. Add multiple hotbar pages

#### Bugs:
1. ~~Job change error~~
2. ~~When toggling the hotbar, the battle notice gets out of sync~~
3. Mp and Tp cost text changes color

## How to install:
1. Download the repository [here](https://github.com/SirEdeonX/FFXIAddons/archive/master.zip)
2. Extract the **_xivhotbar_** folder to your **_Windower4/addons_** folder

## How to enable it in-game:
1. Login to your character in FFXI
2. Press insert to access the windower console
3. Type ``` lua l xivhotbar ```

## How to have windower load it automatically:
1. Go to your windower folder
2. Open the file **_Windower4/scripts/init.txt_**
3. Add the following line to the end of the file ``` lua l xivhotbar ```

## Controls
1. Hotbars are controlled with 1-0, SHIFT+1-0 and CTRL+1-0
2. You can toggle between battle mode using ALT
3. You can hide the hotbar using \   (this key might change with different keyboards)

## How to add actions to the hotbar
Temporarily, the actions must be added by editing the hotbar file:
1. Login to your character in FFXI. A default hotbar will be created
2. Edit the hotbar file: **_Windower4\addons\xivhotbar\data\hotbar\CHARACTER_NAME\MAIN_SUB.xml_**
3. Save the file 
4. Press Insert in FFXI to access the windower console 
5. Type ``` lua r xivhotbar ``` to reload the addon
6. Press Insert in FFXI again to close the windower console

#### File Structure:
```
 <hotbar>
     <field>
         <hotbar_1>
            <slot_1></slot_1>
                  ...
            <slot_0></slot_0>
         </hotbar_1>
         <hotbar_2></hotbar_2>
         <hotbar_3></hotbar_3>
     </field>
     <battle>
          <hotbar_1></hotbar_1>
          <hotbar_2></hotbar_2>
          <hotbar_3></hotbar_3>
      </battle>
 <hotbar>
 ```

#### Actions Fields:
##### < type >
type of action:
* ct - custom command for things like /attack, /check, emotes, etc.
* ma - magic
* ja - job ability
* ws - weaponskill
* item - item
##### < action >
command or magic/ability/item to use
##### < target >
(optional) target to use it on. All macro targets are available, such as t, stpc, me, p1-8, etc.
##### < alias >
(optional) alias for the text that appears under each slot
##### < icon >
(optional) custom icon name. The file must be available under **_Windower4\addons\xivhotbar\data\images\icons\custom\_**

#### Examples:
* Check current target:
```
 <slot_2>
     <target>t</target>
     <type>ct</type>
     <action>check</action>
     <alias>Check</alias>
     <icon>check</icon>
 </slot_2>
 ```
 
 * Mount Raptor:
 ```
<slot_8>
  <type>ct</type>
  <action>mount raptor</action>
  <alias>Raptor</alias>
  <icon>mounts/mount-raptor</icon>
</slot_8>
  ```
  
* Trust Shantotto:
```
<slot_5>
    <target>me</target>
    <type>ma</type>
    <action>Shantotto</action>
    <icon>trusts/trust-shantotto</icon>
</slot_5>
```

* Dia current target:
```
<slot_1>
    <target>t</target>
    <type>ma</type>
    <action>Dia II</action>
</slot_1>
```

* Protect (choose target ingame)
```
<slot_1>
    <target>stpc</target>
    <type>ma</type>
    <action>Protect</action>
</slot_1>
```

* Warp Ring (must be equipped)
```
<slot_7>
    <target>me</target>
    <type>item</type>
    <action>Warp Ring</action>
    <alias>WarpRing</alias>
</slot_7>
```

* Job Ability
```
<slot_2>
    <target>me</target>
    <type>ja</type>
    <action>Chain Affinity</action>
    <alias>Chain Aff</alias>
</slot_2>
```

## How to edit the settings
1. Login to your character in FFXI
2. Edit the addon's settings file: **_Windower4\addons\xivhotbar\data\settings.xml_**
3. Save the file 
4. Press Insert in FFXI to access the windower console 
5. Type ``` lua r xivhotbar ``` to reload the addon
6. Press Insert in FFXI again to close the windower console

## How to create my own custom theme
1. Create a folder inside the *theme* directory of the addon: **_Windower4\addons\xivhotbar\themes\MY_CUSTOM_THEME_**
2. Create the necessary images. A theme is composed of 3 images: a background each slot (*slot.png*), a frame (*frame.png*), and one image for the battle mode notice (*notice.png*). You can take a look at the default themes.
3. Edit the name of the theme in the settings to yours. This setting must match the name of the folder you just created.
