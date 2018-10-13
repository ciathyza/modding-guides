# r/skyrimmods - Merge Plugins - A simple guide on fixing Navmesh Conflicts

If you merge two mods that add Navmeshes, they may conflict with each other, and you'll have to rebuild the meshes in the Creation Kit. I've looked at many tutorials but none of them really helped me. I recently found a decent tutorial, but I still had to jump through a lot of hoops since 1. all the tutorial's screenshots weren't showing (fuck you, Photobucket) and 2. Skyrim's Creation Kit was created by, and for, crab people. So I figured I would make a guide for everyone who's shared my struggle. And I'm gonna make it as simple to understand as humanly possible :)

------

## PREPARATIONS

(You only need to follow these steps once, then you're set)

1. [Learn how to Merge Plugins correctly.](https://www.youtube.com/watch?v=0S6cpCwTezE) If you don't already, I don't know why you're here.
2. Open SkyrimEditor.ini (in your Skyrim folder, where TESV.exe is located) and find the line SResourceArchiveList2. Now edit it so it looks exactly like this: SResourceArchiveList2=Skyrim - Shaders.bsa, Update.bsa, Dawnguard.bsa, Hearthfires.bsa, Dragonborn.bsa, Unofficial Skyrim Legendary Edition Patch.bsa
3. Open Wrye Bash, with these plugins loaded in this order: Skyrim.esm, Update.esm, Dawnguard.esm, Hearthfires.esm, Dragonborn.esm, Unofficial Skyrim Legendary Edition Patch.esp. In the left pane, click on Skyrim.esm. In the right pane, you should see a "Modified" text box with a date in it. Erase what's there and paste this into it: 11/11/11 12:00:00 then hit "Save". Now do the same for the other plugins I mentioned, but add one second to the time for each sequential plugin. For example, Update.esm is next, so it will say 11/11/11 12:00:01. Do the rest of the plugins in the order I stated earlier. We're doing this because the Creation Kit loads plugins in the order they were modified (for some reason), and doing this will assure the actual game gets loaded before any mods.

------

## FIXING NAVMESH CONFLICTS

1. Merge your mods in Merge Plugins. If you get an error saying "There were some NavMesh conflicts" then you've come to the right place.
2. Open your merged plugin in TES5Edit. Expand it in the left pane, then right click "Navigation Mesh Info Map" and click "Remove" (yes, you know what you're doing). Exit TES5Edit once that's done, the plugin will save automatically.
3. Open Wrye Bash, loading your merged plugin and any master files it requires. Highlight your merged plugin in the left pane. In the right pane, go to the "Modified" text box and paste in 11/11/11 12:01:00. Click the "Save" button.
4. If your mod requires any additional masters, right click them in the left pane and select "Esmify self". Then select them in the left pane and paste 11/11/11 12:00:59 into the "Modified" text box, then click the "Save" button.
5. Open SkyrimEditor.ini and find SResourceArchiveList2 again. You will see a list of .bsa files, separated by commas. If your merged mod has any .bsa files associated with it, add them to this list. You can see associated .bsa files by checking Mod Organizer's "Archives" tab. Save the file after editing it.
6. Open the Creation Kit via Mod Organizer. Click "File" in the top left, then select "Data". Highlight your merged mod and click the "Set as Active Mod" button. Highlight the mod again and click OK.
7. You're going to have a bunch of errors pop up, that's okay. Select "Yes to All" on all of them, and pray to Talos that the CK doesn't crash.
8. If it doesn't crash, then all you have to do is click the save icon in the top left (If you see "Computing Bounds For Navmeshes ...%" at the bottom of the window during the save, it worked). Once that process finishes, close the CK. (Your merged mod has been relocated to Mod Organizer's "overwrite" folder, go ahead and move it back to its own folder)
9. Reopen SkyrimEditor.ini and undo what you did in step 5.
10. Reopen Wrye Bash, loading your merged plugin and its masters. Right click the masters in the left pane and select "Espify self". Click the Save button.
11. Now just to be safe, open your merged mod in TES5Edit, right click it in the left pane, and select "Check for errors". Any errors will pop up in the right pane, and if they do, do some quick Googling to see if they're worth worrying about. For example, if an error ends with "Record marked as deleted but contains: Base", then all you need to do is clean it just like you cleaned your Skyrim masters (thanks [/u/Sacralletius](https://www.reddit.com/u/Sacralletius)).

------

If you have any questions, feel free to ask in the comments, but otherwise, that's all there is to it! Happy merging!

## COMMENTS

[Plockton](https://www.reddit.com/user/Plockton) NLVA

You should go through your merge and visit  where the relevant mods are in the render window and manually inspect the nav anyway. You also need to check editorwarnings.txt and resolve all pathfinding errors. That solved a lot of CTD issues for me and increased my stability for sure.

Also loot has a super useful redate plugins function.

Point 10 btw- Are you actually saying ignore those errors?

Also you need to clarify esmifying and espifying required masters.

I also am unsure of point 2. If you remove the map does that not mean you lose all the custom nav edits added by the authors. E.g. you remove the nav edits completely so the kit does what? Replaces it with vanilla? Then you would have to completely manually rebuild the nav, which for something like ETaC is a big job. Have i picked that up right? I always leave the merged nav in the plugin and fix it manually in the kit. Has always worked for me but would be nice to get clarification.



[Sacralletius](https://www.reddit.com/user/Sacralletius) Falkreath

> I also am unsure of point 2. If you remove the map does that not mean you lose all the custom nav edits added by the authors. E.g. you remove the nav edits completely so the kit does what? Replaces it with vanilla? Then you would have to completely manually rebuild the nav, which for something like ETaC is a big job. Have i picked that up right? I always leave the merged nav in the plugin and fix it manually in the kit. Has always worked for me but would be nice to get clarification.

He was talking about the NAVI record, not the NAVM records. The NAVI record is regenerated each time you save a plugin in the CK that has NAVM edits.

[Plockton](https://www.reddit.com/user/Plockton) NLVA

So to clarify, NAVM contains the information pertaining to specific vertices, edges, triangles etc? And NAVI is like a big index of all that NAVM stuff? So ingame, whilst NAVM is not merged at runtime, NAVI is - and therefore NAVI doesn't care about load order and "it just works"?

[Sacralletius](https://www.reddit.com/user/Sacralletius) Falkreath

100% correct.

[Sacralletius](https://www.reddit.com/user/Sacralletius) Falkreath

Nice guide. Some small points, though, which [/u/Plockton](https://www.reddit.com/u/Plockton) pointed out earlier:

If the ESP has any non-ESMified ESP masters, those must be ESMified first, before loading the child plugin in the CK.

> "Record marked as deleted but contains: Base", then it can be safely ignored.

These are UDRs, or deleted referenceres. I shouldn't ignore those, however, it's easy to fix them. In TES5Edit, just use the inbuilt functions "Apply Filter for Cleaning" and "Undelete and Disable References."

[mator](https://www.reddit.com/user/mator) teh autoMator

You can use LOOT to redate all of your plugins all at once, makes that step a lot less cumbersome.  Also, I've always seen the CK respecting the order of plugins in plugins.txt - redating plugins shouldn't be necessary.

[Arthmoor](https://www.reddit.com/user/Arthmoor) Destroyer of Bugs

The CK absolutely does not go by the order of plugins.txt. It still uses timestamps exclusively. Even with SSE.

Further, for LE, this needs to be kept in mind too: <https://afkmods.iguanadons.net/index.php?/topic/4394-skyrim-ck-timestamps-on-official-files-issue/>

[Plockton](https://www.reddit.com/user/Plockton) NLVA

Never noticed that but I work with the CK on a separate drive from my MO because reasons, will need to copy my plugins.txt over and see what happens. Also, see that window that pops up at the end of a merge that says stuff about rebuilding nav, typically with specific coords - does that get dumped to a log file? I had a look but couldn't see it so apologies if I'm being blind.

Also also, what do you think about grabbing some of the pertinent info from a thread like this and tossing it in with any merge plugins navmesh log. Might save a bit of grief.

[mator](https://www.reddit.com/user/mator) teh autoMator

> Also, see that window that pops up at the end of a merge that says stuff about rebuilding nav, typically with specific coords - does that get dumped to a log file?

I don't recall.  I'd have to check.

It tends to reference records though.  Everything will be a lot better in zMerge.

[NarwhalJenkins](https://www.reddit.com/user/NarwhalJenkins) Raven Rock

If I want to get into editing, (about to put together a heavy mod list) should I learn zEdit or Tes5Edit?

I will have to use Merge Plugins, Smash and Wrye Bash and was wondering what to best way to learn to use your awesome tools was.

[mator](https://www.reddit.com/user/mator) teh autoMator

zEdit and TES5Edit have GUIs that are almost identical, so it doesn't matter which you learn.  I of course would prefer folks use zEdit, but it's not yet quite as feature rich as TES5Edit, so if there's something you want to use that isn't there you can use TES5Edit instead.

Both Merge Plugins and Smash are in the process of being deprecated.  They will be rebuilt as zEdit application modes.

[NarwhalJenkins](https://www.reddit.com/user/NarwhalJenkins) Raven Rock

Thanks. Will learn how to use zEdit.

[EpicCrab](https://www.reddit.com/user/EpicCrab) Markarth

Everything [/u/plockton](https://www.reddit.com/u/plockton) and [/u/sacralletius](https://www.reddit.com/u/sacralletius) have said is true. I'd add that you should probably redo or at least check and fix the navmesh where two different mods alter it; in the best case scenario, you'll have problems with NPCs trying to walk through static objects one of your mods places because another mod overrode its navmesh edits, and in the worst, you'll have NPCs not able to reach some places.

Also it's probably easier for you to unpack your bsa files than edit the ini every time you want to do anything. They run slightly faster as bsa files during gameplay but it's slower in the CK to load bsa files you don't need.

[Thallassa](https://www.reddit.com/user/Thallassa) Beep Boop

This doesn't fix navmesh conflicts, it only fixes NAVI.

[nicktheduke](https://www.reddit.com/user/nicktheduke)

Useful information.

However, with #8 - You should edit something like idk "Cabbage" and rename it "Cabbage1" then change it back to "Cabbage" so that CK thinks something has changed. There's been a few times where navmesh wasn't properly generated without doing that.

[nicktheduke](https://www.reddit.com/user/nicktheduke)

Also I'm probably just going to redo all my merges w any previous navmesh errors since I did not change date using Wrye Bash :\

[waylander47](https://www.reddit.com/user/waylander47)

Remind me!

[iCeCoCaCoLa64](https://www.reddit.com/user/iCeCoCaCoLa64) Falkreath

Reminded!

------

Origin: https://www.reddit.com/r/skyrimmods/comments/7brrps/merge_plugins_a_simple_guide_on_fixing_navmesh/

