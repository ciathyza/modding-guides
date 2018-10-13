# Cleaning files & Merging with Merge Plugins

Hello, BS Teams and Skyrim fans,

there are a few merging procedures, Version Control and Merge Plugins are the most common ones.
I find it straightforward and intuitive, and I think simplicity amplifies performance in a hobby community,
so when I was asked I was happy to share what we found out about merge scripts using it the last 2 years.

## 1) Preparations (Installation & Pre-Merge-Fixing)

- you carefully downloaded and installed Merge Plugins (and set it up with the settings at bottom of this post) by Mator: https://www.nexusmods.com/skyrim/mods/69905
- you have TS5EDIT(you always need to check what you are actually doing): https://www.nexusmods.com/skyrim/mods/25859/?
(check at the bottom for settings and link to the script compiler download. Don't worry, just copy paste...)
(you can use Merge Plugins outside of Mod Organizer, too. only I don't really appreciate handling mod files with NMM and I would never dare to touch the steam folder,
because of all the dirty edits that potentially arise when you consistently overwrite permanently the vanilla files. I even reinstall the game vanilla from time to time and have zero mods on the profile I use for development to keep it clean. Note that MO runs on a 32-bit basis, so any application based on the 64-bit technology will not run. )
- you have an esm
- you have espsthat had been built on that esm, and now you want to merge these records into the esm.
- you have carefully checked every esp loaded with the esm at the same time; (pre-merge fixing)
(exactly in the order it will be merged, and you really have an idea about the 7 or so most common error types;
and how to treat all occurring things within TS5edit; and resolved already all! unexpected errors. No critical errors are left. This is not optional, 
it can break your esmcompletely after the merge. Pre- and post-merge fixes should get its own thread and we should discuss it deeper at another point.
It´s a central matter of quality control that modders releasing themselves on Nexus or working in big teams that they care for the quality of their contribution.
It can practically freeze a big teams development if the management staff has to clean and redo all the contributors work; and Nexus mods have a high chance of breaking games or creating conflicts if not cleaned.)


"How do I clean my files?"
- load all files in order, apply filter for checking errors, check errors. Don't get shocked, read the explanation of colours. Dark red = looses conflict, bright red = wins conflict.
-"remove identical to master records" (i always do that) will remove entries that are there and overwrite but do not fill new content. Unnecessary dirty edits.
- "undelete deleted references" will remove the delete flags that had been set inside an esp to delete references within an esm. (not recommended if stuff was deleted on purpose!)
- if a reference is missing, it must be either filled in TS5edit or CK OR you completely remove it. This can cause CTD !
- If things get overwritten, you can actually drag and drop the correct entries onto the "wrong" one, or simply enter IDs. This can be super convenient when resolving conflicting Level Design!
- you should always remove any Navmesh record if your contributor/you didn't navmesh on purpose. Auto-generated navmesh is a big source of trouble, and manually deleting it in TS5edit will cost you time.
- the VMAD error is a reference deleted (trigger box for example) like the usual "reference deleted but contains base object" - those can be deleted on purpose. If so, ignore them. 
I recommend you to read this very important, very short and condensed and easy to understand CK wiki page, defining errors and treatment:
https://www.creationkit.com/index.php?title=TES5Edit_Cleaning_Guide_-_TES5Edit
and this YouTube tutorial by the developer of Merge scripts/Plugins himself: 

*but for now, let's* *assume our build and the* *esps* *are clean.* 

## **2) Merging the Files**

### a) Loading merge plugins (i am a MO user)

[![1.jpg](https://cdn.discordapp.com/attachments/305129046839263235/425328504260001812/1.jpg)](https://cdn.discordapp.com/attachments/305129046839263235/425328504260001812/1.jpg)



**b) let it locate your game folders, load the correct profile**

**![2.PNG](https://cdn.discordapp.com/attachments/305129046839263235/425328500015235082/2.PNG)**



**c) check which files you want to be loaded in. (my files are a bit empty because the new cycle just started right now)**

**![3.PNG](https://cdn.discordapp.com/attachments/305129046839263235/425328502821355522/3.PNG)**



**d) check the esps you want to merge for errors (yes, I didn't convert the esm here, because I don't execute the merge right now).**

**![4.jpg](https://cdn.discordapp.com/attachments/305129046839263235/425329035921326090/4.jpg)**





**![7.PNG](https://cdn.discordapp.com/attachments/305129046839263235/425329497655738369/7.PNG)**



**e) Go in the "merges" tab and add a new merge.**

**![8.jpg](https://cdn.discordapp.com/attachments/305129046839263235/425329718955343872/8.jpg)**



**f) "Overwrites" and "conflicting" always worked without any issues, all Form-IDs match afterward.**

**![9.PNG](https://cdn.discordapp.com/attachments/305129046839263235/425329871351316491/9.PNG)**



**g) Add the esps you want to have to your merge. Mind the order, start with your old esm (which should formally be an esp at this point, but I mean your main file).**

**![10.jpg](https://cdn.discordapp.com/attachments/305129046839263235/425330322557763585/10.jpg)**



**f) If your esps have errors you need to set "ignore errors" to be able to merge the esp in. (that can be normal if you deleted references from the esm within your esp for example; but for that reason, its absolutely essential you UNDERSTAND the errors! (see links on top))**

**![11.jpg](https://cdn.discordapp.com/attachments/305129046839263235/425330704461856788/11.jpg)**



**g) Now, you can simply click on "build merge" (The same command like the hammer button in the top menu, you can push it, if the text does not show up!)**

**![12.jpg](https://cdn.discordapp.com/attachments/305129046839263235/425330929809096704/12.jpg)**



**f) Hands off! Patience! Do not touch it, it happened that the process broke upon wild clicking ;-) (might have been my system...)after the successful merge, you should click done, and then (AFTER you also close the Merge Plugins!) it will only create the newly merged esp (your new esm to be)in the output folder/****e****xamplemerge folder (see the name I gave it above).  Talking about Output folders, it is set up in settings as shown below:g) Settings for the Merge Plugins**

![13.PNG](https://cdn.discordapp.com/attachments/305129046839263235/425331312845520896/13.PNG)





![14.PNG](https://cdn.discordapp.com/attachments/305129046839263235/425331316125597707/14.PNG)



**...check these settings, download the Champollion compiler who can handle the scripts!**
*(update: the exact paths, because hard to read in the screenshot, are.../Skyrim/PapyrusCompiler/PapyrusCompiler.exe.../Skyrim/Data/Scripts/source/TESV_Papyrus_Flags-**flg* *(you need to create this folder and unpack and insert vanilla scripts!)*

**You can download Champollion here: (32bit only for classic Mod Organizer users!):https://www.nexusmods.com/skyrim/mods/35307?tab=filesAlso, you need to have the unpacked vanilla scripts at hand, in your steam folder.**
*(simply download the unpacker for BSA files of your liking from nexus and then create a \**scripts/source/...** folder in your steam folder;copy in the scripts of the vanilla game. Check the screenshot above, its "**Papyrus flags path**".)*

**Set this up carefully, or your scripts do not get handled the way they have to, to be recompiled, and there is a chance you can throw away your Quests if IDs got renumbered on Merge!h) The disadvantage of this merging method:**

*Also note that the \**Dialogue views tab** (first screenshot below) Branch locations (yellow and gray boxes) on the interface aren't saved,so that gets screwed up. Dialogue Views Branches will all be sitting on top of each other at the top left corner. You can drag and drop them out of each other again;but it would cost you a few minutes extra.However, we talked a while ago if there is the option to export an excel from CK and then re-import. There may be a clever workaround to store that coordinates of the Branch windows.But in reality, I prefer working with the excel-chart like **Player dialogue tab** (second screenshot below);especially when handling many topics, so I don't really think it changes anything or is a real downside myself.* 



[![900px-QuestDialogueViewsWindow.png](https://www.creationkit.com/images/thumb/4/44/QuestDialogueViewsWindow.png/900px-QuestDialogueViewsWindow.png)](https://www.creationkit.com/images/thumb/4/44/QuestDialogueViewsWindow.png/900px-QuestDialogueViewsWindow.png)



*(This is* *more handy* *for me:)*

[![900px-QuestPlayerDialogueViewsWindow.png](https://www.creationkit.com/images/thumb/8/8a/QuestPlayerDialogueViewsWindow.png/900px-QuestPlayerDialogueViewsWindow.png)](https://www.creationkit.com/images/thumb/8/8a/QuestPlayerDialogueViewsWindow.png/900px-QuestPlayerDialogueViewsWindow.png)

i) Finalising the esp before flagging it as esm again.

You should open your esp now in CK first, and click save; so all the "deleted flags" set by newly merged in esps regarding esm content actually do delete finally. 

(The "esm" being a protective flag against edits on an esp, did hinder this process previously. After that, the "Deleted base" error on your esm in TS5edit should be gone. This is one of the error types when checking in TS5edit that are non-critical, if you know what you deleted and you did it on purpose.)

And finally, you only have to rename it so it has the same name as the old build (Southernatmora for us) and flag it as ESM in TS5Edit again. After that, the esp is ready.

3. ## Post-merge Fixing

(here is where I would usually start my post-merge cleanup directly on the esm or even create a new esp and then merge again; so i can read out editor warnings with done fixes and effectively reduce all CK error warnings step by step. You can find them in a notepad doc inside your steam folder, called "EditorWarnings.txt". I strongly recommend to copy paste all content in an excel chart, filter it and auto-mark with colour all entries with the ID of your masterfile; you will sometimes have thousands of warnings, but that's no problem, it simply prints this warning each time its appearing, so if you have an error on a mesh; and that mesh has 3 nitrishapes with wrong shader settings, and you have that mesh 100 times in your dungeon, you already get 300 errrors, however, you only have to repair 1 mesh eventually).

I hope this gives you a good help and we can update this with your feedback.

thanks, for Tascani who worked with me on this. Good Fixing and Merging all of you!

------

Origin: https://www.darkcreations.org/forums/topic/13480-cleaning-files-merging-with-merge-plugins/

