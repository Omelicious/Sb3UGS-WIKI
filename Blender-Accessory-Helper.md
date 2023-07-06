This is easier than the Blender Clothes Cycle because Blender's FBX importer keeps the parenting of unskinned meshes. But to ease with the creating of the mesh parents you can import an accessory and use its hierarchy. 

Check all Transforms. Easy requires that all Transforms have an Identity transformation matrix. 

![N_move helper - 01](https://github.com/enimaroah-cubic/Sb3UGS/assets/104311725/8877bafe-34b3-4b57-aa3b-962d6ef15618)

Imported in Blender, check the parenting in Relations:

![N_move helper - 02](https://github.com/enimaroah-cubic/Sb3UGS/assets/104311725/9f083d94-2883-4e29-a8e9-5d002aac0b1c)

Import your own mesh - Hair in this example. Adapt the size - see the scaling and translation.

![N_move helper - 03](https://github.com/enimaroah-cubic/Sb3UGS/assets/104311725/6f311e7b-e7cf-4f26-b6ef-422c6120f7e8)

And since we did this to the mesh object, we have to Apply those scaling and translation. This bakes the transformation into the local coordinates of the mesh.
The new mesh gets also parented to the same parent as the original. This operation rotates the mesh because the Armature has that nasty 90 degrees for X.

![N_move helper - 04](https://github.com/enimaroah-cubic/Sb3UGS/assets/104311725/8190b4cc-b175-4e6b-9e62-9d6401c48b0d)


![N_move helper - 05](https://github.com/enimaroah-cubic/Sb3UGS/assets/104311725/5b138140-5a17-4ae5-8f4d-155051cff69a)

![N_move helper - 06](https://github.com/enimaroah-cubic/Sb3UGS/assets/104311725/23eb9148-cfd6-4603-97e5-4cba9b401647)

Export in Blender, import in Sb3UGS. The same mesh parent means that the new mesh is imported as second submesh:

![N_move helper - 07](https://github.com/enimaroah-cubic/Sb3UGS/assets/104311725/4a3f8b3d-f768-426d-85db-12e626644a6a)

Drag 'n drop with the following options into the Blue Area: 

![N_move helper - 08](https://github.com/enimaroah-cubic/Sb3UGS/assets/104311725/b57acba8-a87d-4554-aab4-9ee61b8e8c4c)

![N_move helper - 09](https://github.com/enimaroah-cubic/Sb3UGS/assets/104311725/464ff0fe-2d12-4c4a-a16c-1d3ff48203a9)
![N_move helper - 10](https://github.com/enimaroah-cubic/Sb3UGS/assets/104311725/a2793313-ca74-43fa-8550-743a053283b1)
