We begin the cycle with an import from Sb3UGS. I had exported the original long KK gloves, and imported the FBX in Blender 2.90.1.

![Blender_Clothes_Cycle_1](https://user-images.githubusercontent.com/104311725/167834474-728177f0-00b4-499d-a4ed-c8ae1512d396.png)

The skinned mesh shows some **translation** and it has lost its original **Parent Bone**. For fixing the parent bone we need to set the Armature's rotation from 90 to 0.

![Blender_Clothes_Cycle_2](https://user-images.githubusercontent.com/104311725/167834616-84179e3d-9e5c-45b7-b5fe-a9384b716fcd.png)

Now everything lies flat on the floor. Make the future mesh parent the only active bone, add select the mesh. Make sure that you are in Object Mode when you set the Parent Bone.

![Blender_Clothes_Cycle_3](https://user-images.githubusercontent.com/104311725/167834845-847b3768-6c05-41bc-bab9-e144c5816f8f.png)

Great, now revert the Armature's rotation back to 90. Next **Apply** the mesh's translation.

![Blender_Clothes_Cycle_4](https://user-images.githubusercontent.com/104311725/167834975-8cd07f3d-cfbc-418c-a67a-304a530f8557.png)

Even better, the mesh looks like shortly after import, but it is now corrected and allows to be exported. The FBX exporter does it right here.

In Unity editor we create an AssetBundle file for the gloves:

In your project folder is an Assets/Editor folder e.g. ...\KKModdingTools\Assets\Editor. The following script will never be executed from the game, it is for Unity editor itself and removes unused bones from the imported meshes: [BlenderFBX_Postprocessor.cs](https://github.com/enimaroah/3D-Misc/blob/master/Unity/BlenderFBX_Postprocessor.cs).

1. Select the FBX file. I had put it into ...\KKModdingTools\Assets\Mods. Change the import options. Don't forget to **Apply**.
![Blender_Clothes_Cycle_5](https://user-images.githubusercontent.com/104311725/167835356-d234c455-693c-4c54-8849-538e9bab6509.png)

2. Drag the FBX file somewhere into the scene. Expand it there to reach p_o_gloves_long01. Set the Layer to CHARA, confirm that you want that for children as well, add a ChaClothesComponent MB in which you register the SkinnedMeshRenderer in rendNormal.

3. Drag p_o_gloves_long down to create a prefab and assign an AssetBundle filename.
![Blender_Clothes_Cycle_6](https://user-images.githubusercontent.com/104311725/167835494-7915bfa6-5dfe-4de0-a287-2ed1b4dfbf88.png)

Then build the AssetBundle, or zipmod and test it in game.

![Blender_Clothes_Cycle_7](https://user-images.githubusercontent.com/104311725/167835641-17c31942-57d3-4f5b-a4c9-1866f5506e30.png)

Inspecting the AssetBundle has some surprises for us.

![Blender_Clothes_Cycle_8](https://user-images.githubusercontent.com/104311725/167835789-6e8f41f2-88f5-4da3-a9e0-7eb61ec2b6c8.png)

1. The bounding box of the mesh greatly differs from the original. That is because of the Bind Poses - Bone Matrices in Sb3UGS. They are a remainder of Blender's FBX importer when the local coordinates were transformed for breaking free from the Bone Parent or from Blender's "Apply" of the translation. For that reason Sb3UGS shows mismatching Bind Poses in the tooltip. This means that the mesh in not in "Rest Pose", and computing the rest pose in that state would shift the mesh in an unwanted way. If we would want to revert that in Sb3UGS, we would use the FBX exported from Blender using "WorldCoordinate" option and additionally we would have to compute the "Rest Pose" after replacement.
2. The number of Bone Hashes is still very high and not aligned with Bones / Bind Pose. Luckily, Unity doesn't use them. Their hash values are computed for the original hierarchy beginning with Armature which is not longer inside the prefab.