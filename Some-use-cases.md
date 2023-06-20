### Making a modified Accessory standalone

After learning the [[Production Cycle]] you have a modified accessory in an original file. So you might want to make the accessory independent and revert the original file afterwards.

You need a small helper AssetBundle file as container for this. And here I used the orignal mole file from the game folder because it has only a few textures in it. The textures are selected and deleted (Shift-Del), the modified accessory p_acs_neck_darklace00 in ao_neck_00.unity3d is selected and gets underlined with "Mark for Copying" as indication for being pasted. After "Paste All Marked" into the mole file, I checked two MBs for verification, then used **"Save As..." which allows to store it in a new path and file**.

![Modified_Accessory_Standalone](https://user-images.githubusercontent.com/104311725/167832473-7e9826ba-569f-42ba-9158-a2512de44f33.gif)

If you forgot to mark an asset, you can repeat the marking and pasting. See the tooltip of "Paste All Marked". It has a list of supported assets for this operation.

### Editing MonoBehaviours

Open MBs (like all other "green" assets) with a double-click in the Object Tree or in the "MonoB. & Other" file tab.
Click on a line then edit the value in the input field at the bottom. For references you can use drag 'n drop. And even for that is a tooltip in the input field.

![DND_demo2](https://github.com/enimaroah-cubic/Sb3UGS/assets/104311725/08ecb590-d5ca-411d-8a0a-8bce514f206e)
