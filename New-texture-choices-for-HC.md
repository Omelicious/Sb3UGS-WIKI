As long as there is no sideloader, we are modding hard and create AssetBundles (AB) with the contents and the list entry. The contents in this example is a texture, and the list entry is used from the game to integrate every content; not only new ABs.

Let's begin with the contents - a texture for the iris of the eye. Drag 'n drop mt_eye_00.unity3d into Sb3UGS and double click a texture. Should look like this:
![image](https://github.com/enimaroah-cubic/Sb3UGS/assets/104311725/b567cdfd-bf98-410e-80e2-a6fea10dedff)

Click "Export". There is no dialog with the destination. You find the texture exported in the game folder. If you can't find it, see the Script window with the export statement.

Editing in Gimp

![image](https://github.com/enimaroah-cubic/Sb3UGS/assets/104311725/742cb47c-2121-4068-a95d-114dcbd629bb)
1. Scale upwards, so that the ellipse becomes a circle
2. Rotate the circle. Gimp extends the resolution!
3. Crop to the former upscaled resolution in step #1
4. Scale downwards to original resolution

![image](https://github.com/enimaroah-cubic/Sb3UGS/assets/104311725/eb2c6208-252d-423d-a8a3-0ef26040b5c5)


Drag 'n drop your edited texture into Sb3UGS:
![image](https://github.com/enimaroah-cubic/Sb3UGS/assets/104311725/c9b5a3db-b67e-4fa7-afee-6883992a2ef9)

Click "Replace" in the Texture editor. Don't worry, as long as you don't save the original AB like this you won't lose the original. We get even more destructive now, and delete all other textures in the file. Click on the first texture, shift-Click on another to select a range of textures. Use Ctrl-Click to select the next start of a range of textures. Shift-Click to the end of the second range. 

![image](https://github.com/enimaroah-cubic/Sb3UGS/assets/104311725/e3b585e3-4dfa-4e20-9575-b63deecf6a4d) 

Then Shift-Del all selected textures at once. 

![image](https://github.com/enimaroah-cubic/Sb3UGS/assets/104311725/5e60c167-f4a4-48c6-ac05-d0b5a0a66734) 

And "Save As ..." the file with a new name. 

![image](https://github.com/enimaroah-cubic/Sb3UGS/assets/104311725/2d4a02cf-2f4f-4818-bc5c-192a95ccdbd0) 

In this example I had saved the file as mt_eye_00_645.unity3d which we will now reference in the list entry.

Open 000_00.unity3d and double click mt_eye[000_00] TextAsset. The list entry for texture cf_eye_06 looks like this:

![image](https://github.com/enimaroah-cubic/Sb3UGS/assets/104311725/6bf07283-1f46-416d-b4c3-7c6b24cd2c4b)

We simply overwrite columns Name, MainAB with the new contents file, and EyeTex only if you had renamed the texture. If you did make sure that your texture attributes were like the original before.
**The ID for a new choice must be UNIQUE for the whole game.** If you use an existing ID by accident the original entry is no longer visible in the selection in game. You would use an existing ID to override an original.

Click the first line, shift-click the end of a range. Then press Del to delete the range. This control allows only one range.
Then delete all other TextAssets in the file and like with the contents AB use "Save As ..." with a name following this pattern {three digits}\_{two digits}\_{your choice}.unity3d:

![image](https://github.com/enimaroah-cubic/Sb3UGS/assets/104311725/17b89052-2b3f-4dae-9d04-5c5e3a8a857c)

![image](https://github.com/enimaroah-cubic/Sb3UGS/assets/104311725/ab9523e1-2b60-4f26-97ea-8d9b6233e898)


### A different texture for clothes?

Same thing. This example shows one for the bra category. The texture is handled in the same way as above. Only the list TextAsset and entry are different. So we put co_bra[000_02] TextAsset from 000_00.unity3d into our own list file as above with the edited content. A unique ID, display name and the AB with the texture are different. The texture got the same name in the new file for the new choice.

![image](https://github.com/enimaroah-cubic/Sb3UGS/assets/104311725/ed3a4b3e-3a84-4d6c-b86e-f0e52d1b2bdb)

![image](https://github.com/enimaroah-cubic/Sb3UGS/assets/104311725/e0ed453d-afa0-4a1a-a10f-344a51e5ff2e)

### Clothes with Transparency

Most clothes are opaque and in order to make them transparent you can use lif_main_cloth_alpha shader. This shader might not be present in the current file and needs to be copied over. (See [[Some use cases#editing-monobehaviours]] how to copy assets). But if the material's shader would be switched then the original clothes would no longer be the same. For this reason the whole Animator needs to be copied to make it independent and then the material's shader can be changed. (See the [[First Steps]] for copying the Animator and saving later into a new file). Open a clothes Animator which has that shader (heroine's e.i. It has transparent sleeves). The CustomRenderQueue is 3000 in this example with the tundere top: 
![image](https://github.com/enimaroah-cubic/Sb3UGS/assets/104311725/07fc50d5-3a82-4e5d-8e52-6c7f7cb5343b)
