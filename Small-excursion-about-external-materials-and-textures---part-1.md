The files are taken from Honey Select release version, but the principle applies to all Unity based games.


Load cf_shorts_04.unity3d and open Animator p_cf_shorts_11_00.

Select Mesh cf_O_shorts_d and note the message in the Log window:

cf_O_shorts_d[0] has an external Material **FileID=1** PathID=-4868027318105399293

![External_Links_Part1_-_1](https://user-images.githubusercontent.com/104311725/167845444-9e71caa1-43bd-43df-bb3a-2de67ab8d07a.png)

Unselect the Animator. Nothing should be selected now.

From the file's Options menu click "View Data". Last lines of the output are:

References

**FileID=1**: guid=00000000-0000-0000-0000-000000000000 type=0 filePath="" assetPath="archive:/cab-05785cb2276d2d34983aef7c43515e6e/cab-05785cb2276d2d34983aef7c43515e6e"

![External_Links_Part_1_-_2](https://user-images.githubusercontent.com/104311725/167845586-ef8f2dec-8d2a-4d97-b37f-7b6411b82cd2.png)

Search in the whole **abdata **folder for that Cab-String "**CAB**-05785cb2276d2d34983aef7c43515e6e" or limit your search to the files at the end of "**Dump AssetBundle**".
You will find many files with that CAB-String (all ending _04) if you search case insensitive!
If you do it right then you will find mat_cha_04.unity3d. Drag it into Sb3UGS.


Now refresh the Mesh by clicking it in the Mesh list.

![External_Links_Part_1_-_3](https://user-images.githubusercontent.com/104311725/167846105-834967ca-a295-4a1d-b65f-04a839e91e84.png)

Note two things:

* The Material has been loaded and Textures too, because they are in the same file.
* In the mat file more materials have been loaded (shown in bold face). But they are not available for selection yet. To use loaded resources either close and reopen the Animator or switch to the Object Tree and press "Refresh" at the bottom.
    ![External_Links_Part_1_-_4](https://user-images.githubusercontent.com/104311725/167846368-05b12898-7ad8-4a52-8d27-7bda134afd2a.png)

     The grey foreground colour in the Object Tree marks external assets. Remaining question: why haven't all materials in that been loaded? The file with the shorts references only those four.

Select the material and use "Copy -> New".

![External_Links_Part_1_-_5](https://user-images.githubusercontent.com/104311725/167846682-8ddf0d99-fbe6-4aee-a829-659b3adcc8de.png)

Local assets are black. Externals are grey. This is important when using them and since they have the same name they are marked accordingly.

Note also that our shorts file got new tabs for Materials and Textures. This file didn't have any of them before and all types are registered.

**Currently new types make this file invalid for the game!** You get a message in the game's log file:

**The AssetBundle '{your file path}' can't be loaded because it was not built with the right version or build target.**

In this case you have to change the Inventory offset in the file's menu. - Fixed in SB3UGS_v1.2.7 and later versions.

![External_Links_Part_1_-_6](https://user-images.githubusercontent.com/104311725/167846898-57122b35-cf84-49d8-b75a-8470b201a4ae.png)

Now remove the external material cf_M_shorts_11_00. The mesh shows up like at the beginning. Though you could switch to the new local copy.

Do something else instead and reload the shorts file! Two messages are shown in the Log: 

`The given key was not present in the dictionary`.

Remember we have removed the material from the material file which is still in Sb3UGS. If you see this message then usually a file is broken. This can happen e.g. when you edit files standalone and Sb3UGS doesn't even know the referencing file.