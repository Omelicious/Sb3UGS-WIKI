A mesh can be deformed in a more complex way than just scaling up and down, rotating or translating when it is **skinned**. Skin means the flexibility, not its colours. Skin is the counterpart to bones. A bone could break, the skin bends.

Where can the skinned mesh bend? Only where a vertex is. For this purpose each vertex gets up to four weights. And such a weight is the measure for bending according to one specific joint. In general animations rotate joints, many in parallel and independently. And each vertex follows up to their four weights for those joints. Any parent of such a joint transforms the mesh as a whole as if it would be unskinned. More to the question of where it can be bent. We need more vertices in areas where we want the mesh to be bent and less vertices in static parts. An example in our body of the former would be the elbow, and for the latter a forearm.

The following example is by far not perfect. You can still do this for learning several aspects.

![First Skinning - 01](https://user-images.githubusercontent.com/104311725/221356458-88e42b7b-1d45-493b-84d6-776f2bf3c793.png)

p_acs_head_nitneko exported and imported in Maya.

![First Skinning - 02](https://user-images.githubusercontent.com/104311725/221356463-0062a631-6da7-44a9-8f6b-84124fa9bade.png)

Adding geometry for smooth bending.

![First Skinning - 03](https://user-images.githubusercontent.com/104311725/221356465-981dc0b0-bad9-4ca3-984d-51cd5e4e5394.png)

Creating the skeleton. You create joints inside the geometry with some length.

![First Skinning - 04](https://user-images.githubusercontent.com/104311725/221356466-d5849ec9-11d3-4761-92ff-f5a5ccec39c9.png)

Binding the skeleton to the mesh. This results in getting some default weights for each vertex. If you have an original mesh from the game with close vertices, you would copy the skin weights afterwards to the new mesh. Without such a template mesh, you have to correct the skin by painting weights manually.

![First Skinning - 05](https://user-images.githubusercontent.com/104311725/221356468-6ea041b3-3f84-4a04-a75e-85f09082ca9f.png)

Replacing in Sb3UGS. First the skeleton, then the mesh. When you select a bone from the bone list of the SkinnedMeshRenderer, the preview shows the weights for that bone. Colours are similar to Maya's. Only a weight of 1.0 would be white in Maya and is full red in Sb3UGS.

![First Skinning - 06](https://user-images.githubusercontent.com/104311725/221356469-c7bab003-d480-40ff-af9b-be0bd8fbec04.png)

For the DynamicBone physics we copy a DynamicBone MB and drag the Transform joint2 onto m_Root in the MB.
