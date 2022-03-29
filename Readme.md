# BetterUtility v1.0
By: Harvest


# What does this Plugin do?
This plugin is a simple utility plugin that applies miscellaneous code edits for your mod.

It is designed to protect certain mod settings (from the noobs at least)


__IMPORTANT__: This plugin requires a bin file to be pre-compiled. I have
included one to prevent you from crashing right at the start.
__YOU MUST RECOMPILE AND RELAUNCH THE GAME AFTER EVERY TXT CHANGE.__

  
In order to recompile the bin file:
1. Apply a change to BetterUtility.txt
2. Join a game with -direct -txt enabled
3. Close the game
4. Relaunch the game

  
To release your mod without the txt
1. Delete BetterUtility.txt from the excel folder
2. Disable the -txt command line parameter

  

The direct line in D2Mod.ini controls whether or not you are
actively updating settings by checking if the .txt/bin files
exist and will load different functions accordingly.
Use direct=0 if you want to use MPQ mode.

  

# Installation

1. Add these line to your D2Mod.ini.
```
BetterUtility=BetterUtility.dll

[BetterUtility]
direct=1;
```

2. If you haven't already installed the NewTxt plugin, then also add
```
NewTxt=NewTxt.dll
```

3. Copy the BetterUtility.txt and BetterUtility.bin files to your
data\global\excel\ folder.

  
  

# Uninstall
To remove the plugin you just have to delete the entries you made
in your mod ini and the BetterUtility.txt and BetterUtility.bin files
from your data\gloabl\excel\ folder.

  
  

# Text file Columns
```
 *Settings   -       Setting description, does nothing.

 HcIDx       -       Incremental line value (DO NOT CHANGE)

 Enabled     -       BOOLEAN, Is setting enabled?

 Par1        -       Additional parameter for certain settings (see Below)

 Par2        -       Additional parameter for certain settings (see Below)

 Par3        -       Additional parameter for certain settings (see Below)

 Par4        -       Additional parameter for certain settings (see Below)

```
  

# Settings 
0. Increase Loot Cap (Parameter = ##, default = 6)
This setting allows you to change the maximum amount of items that monsters can drop

1. Allow Auras to recalculate zero
In vanilla, if an aura calcs any value greater than zero, and the stat is changed, the value will not return to zero.

This setting will fix that.

2. Regen maps in Single Player
Always regenerate maps in Single Player, like on realm.

3. Maximum Items to Gamble (Paramter = ##, default 14)
Changes the amount of items that appear in the gamble window

4. Items* always drop Identified
The order for switches is as follows: Magic,Rare,Set,Unique
to Allow for only Magic and Rare, input: 1,1,0,0

5. Remove Rings and Amulets from gamble
Rings and Amulets are hardcoded to always be the first two items generated in the gamble routine.
To fully remove them, you must also remove the lines in Gamble.txt

6. Shift Click Limit (5 stats per click)
While holding shift, and allocating a stat, the stat will only increase by 5
In vanilla this action would allocate ALL remaining stat points.

7. HyperJoin
Decreases the load time when playing TCP/IP games.

8. Display Smite Damage for all classes

9. Display Kick Damage for all classes

10. Enable Classic blocking
Your chance to block is based on the Block Chance of your shield

11. Use GambleCost for Items
Uses the "GambleCost" column from items.txt to determine cost

12. Change Screenshot Location
***THE FOLDER MUST EXIST BEFORE USING THIS SETTING***
Changes the Screenshot location to Parameter2 column contents "Screenshots/Screenshot%03d.jpg"

13. Disable Classic, Expansion only characters
Goodbye classic....

14. Display ilvl
Displays the item level on items

15. Umon column affects all difficulties
Fixes the umon column in levels.txt to work on all difficulties.
"This column controls which monsters can be selected to be Champions and Random Uniques"

16. Increase Music Limit (Parameter = Last music Index number)
Allows you to add new music to the game

17. Imbue Quality (Parameter = Quality)
Allows you to change the resulting quality with Charsi's Imbue.

***See Appendix***

18. Cain always charges to identify (Parameter = Charge Cost)

19. Make Unique column specify quality
In vanilla the Unique column in Items.txt is a boolean
This setting allows you to insert a specific quality for items (See Appendix)

20. Starting Items get stats (Par1 = Item Level, Par2 = Quality, Par3 = Remove NEWBIE_ITEM flag?)

In vanilla the statlist is deleted for newly created characters

This setting allows new characters to get items with affix's

In vanilla items on newly created characters are flagged as NEWBIE_ITEM which forces them to only sell for 1 gold.

21. Control which qualities can have Runewords (1=TRUE)

***See Appendix***

22. Control which qualities can have Automagic (1=FALSE)

***See Appendix***

23. Anya Reward Quality

***See Appendix***

24. Softcode Book and Scroll Names
Allows new books and scrolls to display the correct name.

25. Telekenisis takes all items.

26. PlayersX command limits

27. CPU Fix
Such CPU, much optimized.

28. Akara Ring Reward: Par1 = Quality, Par3 = iLvl per Difficulty (Norm, NM, Hell), Par4 = ItemCode

The ItemCode must be converted to Hex, AND reversed.

Example, by default this is 206E6972. Converted to ascii = " nir" <- Don't forget the space for 3 letter itemcodes.

To change the itemcode to an amulet, we convert " uma" to hex > 20756D61

29. Ormus Ring Reward: Par1 = Quality, Par3 = iLvl per Difficulty (Norm, NM, Hell), Par4 = ItemCode

The ItemCode must be converted to Hex, AND reversed.

Example, by default this is 206E6972. Converted to ascii = " nir" <- Don't forget the space for 3 letter itemcodes.

To change the itemcode to an amulet, we convert " uma" to hex > 20756D61

30. Book of Skill: Par1 = Stat Index, Par2 = ItemCode

The Stat Index is the "ID" taken from ItemStatCost.txt, so you can change what stat the book grants.

The ItemCode must be converted to Hex, AND reversed.

Example, by default this is 20737361. Converted to ascii = " ssa" <- Don't forget the space for 3 letter itemcodes.

To change the itemcode to a custom item (x01), we convert " 10x" to hex > 31307820

31. Potion of Life: NOT WORKING

32. Lam Esen Tome: Par1 = Stat Index, Par2 = Stat Value, Par4 = ItemCode

33. Den of Evil Reward per difficulty: Par1 = Stat Index, Par3 = Normal, Nightmare, Hell

34. Izual Reward per difficulty: Par1 = StatIndex, Par3 = Normal, Nightmare, Hell

35. Hardcore Only Characters

36. Increase Automagic Limit: Par1 = Number of bits (2^par = limit)

  

# Appendix

Screenshot Location:

If you put the screenshot location into a separate folder, that folder will need to exist before

you take a screenshot else nothing will happen, or you will crash.

You can change the number in %03d to any number you see fit, in this example, you'll print a sreenshot named

ScreenshotXXX.jpg

Change the number to a 5 and you'll get

ScreenshotXXXXX.jpg allowing you to store thousands of screenshots if you wish.

  

Item Qualities:
```
 0 = Dont set quality

 1 = Low Quality

 2 = Normal

 3 = Superior

 4 = Magic

 5 = Set

 6 = Rare

 7 = Unique

 8 = Crafted

 9 = Tempered
```
  

Item Qualities and iLvl:

If the iLvl is not high enough to spawn a Set piece, the game will roll a Magic instead.

If the iLvl is not high enough to spawn a Unique, the game will roll a Rare instead.

  

Runeword and Automagic Switches:
The switch order is as follows
LowQuality,Normal,Superior,Magic,Set,Rare,Unique,Crafted,Tempered

Default Runeword switch:
1,1,1,0,0,0,0,0,0

Default Automagic switch:
0,0,0,0,1,0,1,0,0

  

# Chaneglog 

v1.0 3/29/2022
-Added Hardcore only
-Added Automagic limit

v0.6 04/10/2020
-Shift click limit value can now be adjusted by Par1

v0.5: 11/12/19
-Fixed DOE, Izual, Book of Skill rewards (hopefully)
  
v0.4: 10/21/19
-Added A3Q1 Lam Esen Tome reward control
-Added A1Q1 Den of Evil reward control
-Added A4Q1 Izual reward control

v0.3: 10/19/19
-Code optimizations
-Combined some settings to reduce space
-Added A2Q1 Book of Skill reward control

v0.2: 10/18/19
-Added CPU fix
-Added A1Q3 Akara Ring Reward control
-Added A3Q2 Ormus Ring Reward control

v0.1: 8/10/19
-Initial Alpha Build

  

# Credits

Necrolis, Kingpin, SVR, Nefarius, Myhrginoc, Mentor, afj666, Joel, dav92, Elliot_009, pmpch, and Yohan for code and code locations.

Whist for D2Template, Nefarius for Nefex.