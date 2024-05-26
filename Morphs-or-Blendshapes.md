Morphs or Blendshapes are used for animating vertices of meshes. Most often Illusion used morphs for facial expressions. In Sb3UGS after opening an Animator with meshes which have morphs there is an extra Morph tab with groups of morphs and when you select one of them the Morph editor on the right side allows to edit the structure. Creating or editing the morphs must be done in a 3d editor.

![Wiki_-_morphs_-_01_-_gui](https://user-images.githubusercontent.com/104311725/167836373-65c272b3-c290-4966-89d4-0668f0987288.png)

So what's morphed here? The head and the eye lashes are morphed and show a Channel named wink_L. The mesh being morphed is shown in square brackets. Selected in the screenshot is a mesh named P_matuge - the eye lashes. wink_L has two morph frames which indicates that it is a progressive morph aka in-between blendshape. Behind the channel name is shown how many vertices of each submesh are morphed by this channel. (In the workspace on the left side the same mesh was imported and shows both submeshes with the total number of vertices).


Sb3UGS has only two morph frames which can be previewed. In this screenshot the preview shows the first frames of the head's wink_L and the eye lashes's wink_L channels. For different meshes as here the slider below doesn't do anything. But when both frames are for a single mesh then the slider controls the morph strength.
### Replacing morphed meshes

When a morph should be put into another Animator, e.i. into a new file, then the mesh needs to be replaced first.

Drag 'n drop from the workspace into the Animator's blue area, if the destination mesh parent is already present with the same name.

![Wiki_-_morphs_-_02_-_morphed_mesh_replacement](https://user-images.githubusercontent.com/104311725/167836503-92330325-b24d-48e7-8398-3ef2c0240f31.png)

In Unity any morphed mesh must be hosted from a SkinnedMeshRenderer, but in this example our mesh is unskinned. For unskinned meshes the replacement dialog defaults to "Convert to MeshRenderer" and this is unwanted here. The result must be a SkinnedMeshRenderer, without bones in this case.


Although no Morph tabs are visible in the Animator the drag 'n drop will create them during the dragging when it hits the Object Tree. Make sure that the destination SkinnedMeshRenderer is selected before the morph replacement.

![Wiki_-_morphs_-_03_-_morph_replacement](https://user-images.githubusercontent.com/104311725/167836678-dd2f0c24-d454-4af7-b616-c6cb2f6899ee.png)

After pressing "OK" for each morph clip we have the morph group named matu in the Animator.

![Wiki_-_morphs_-_04_-_morph_replacement_result](https://user-images.githubusercontent.com/104311725/167836807-6fcfbbf4-bd96-4728-9dc9-dc113a75e705.png)

Mesh and its morphs are copied.

If the mesh needs to be replaced again, all the morphs are cleared, because the vertex indices could have been changed and then all morphs would become invalid. Clearing the morphs keeps the morph clip indices valid when the morphs get replaced afterwards. The morph indices are used in MonoBehaviours instead of their names. In case of index changes the MonoBehaviours would need to be adapted.
### Exchange of Morphs

The example imported in Maya looks like this:

![Wiki_-_morphs_-_05_-_morph_imported_with_Maya](https://user-images.githubusercontent.com/104311725/167836989-f1b6089d-a30d-4cb6-9533-4f7432cab77d.png)

In Maya there are no submeshes. For this reason Sb3UGS broke the morph channels accordingly, and renamed the meshes and channels. The same naming is required if meshes and morphs are created in Maya. Sb3UGS reverts the naming and combines channels accordingly during replacement as describe above.


Imported with Blender, but the same situation requires to export with "Flat In-between Blendshapes" option. In Blender the FBX importer needs "Custom Properties" option.

![Wiki_-_morphs_-_06_-_morph_imported_with_Blender](https://user-images.githubusercontent.com/104311725/167837143-24715dea-0839-4c89-bd96-fad91fe93fa1.png)

The naming of meshes and morphs in Blender is even more important to have an easy import and replacement in Sb3UGS afterwards. But this naming allows to create in-between Blendeshapes with Blender which can be used in the games.

![Wiki_-_morphs_-_07_-_in-between_blendshapes_exported_with_Blender](https://user-images.githubusercontent.com/104311725/167837260-a3b04fee-7d62-4753-acf2-c02ed3f0ec77.png)

### Custom normals in Blendshapes

Neither Maya nor Blender seemed to be able to import and export custom normals of blend targets. But FbxSDK can import and export them. So you can use Sb3UGS to make backups when they are present and you can restore them.

But bringing custom normals into a Mesh asset for the first time requires to bake shape targets as meshes. The ImportedMesh in the workspace can then be dragged and dopped onto an ImportedMorphKeyframe. See the message in Log for the result. Afterwards you replace the ImportMorphKeyframe like regular.

![CustomNormals in Blendshapes](https://github.com/enimaroah-cubic/Sb3UGS/assets/104311725/b2fdaf7c-0a31-49ae-96dd-4897fc7a8f42)

There is no naming convention for meshes when single keyframes are replaced, but naming meshes as in the example above allows to replace them all togther with a single drag 'n drop. See also the comment in the Morph editor.