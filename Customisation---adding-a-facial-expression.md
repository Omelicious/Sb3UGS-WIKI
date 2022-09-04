## Under construction

A new blendshape is created and added as described in [[Morphs or Blendshapes]] described.
![Add_expression_01](https://user-images.githubusercontent.com/104311725/188323195-62798d13-899d-4cf1-bd36-0d6b554386b8.png)

![Add_expression_02](https://user-images.githubusercontent.com/104311725/188323343-cac08264-3fcc-4d78-92cf-c1ea12b023bf.png)

The new blendshape here is at index 81. We need to find a free slot in FaceBlendShape MonoBehaviour.

![Add_expression_03 - chara_maker_mouth](https://user-images.githubusercontent.com/104311725/188323593-e861d8dc-8406-40b4-9ed4-3f9ef65650b3.png)

We add a new line, in this case with "40, M exp 40" and extend all arrays in MouthCtrl. Index 40 will be used for each mesh when the new expression will be selected in game. In this case there are more entries right from the start. Thoses exceeding entries are unused and can not be selected in the Chara Maker.

![Add_expression_04 - FaceBlendShape_Mouth_meshes](https://user-images.githubusercontent.com/104311725/188323899-90ee0e71-153f-42b3-a496-515f3cd6f5ae.png)

Here we put our index for the new expression. The Close expression is the shown when the slider in the game is fully left. And Open is the right most position.

![Add_expression_05 - FaceBlendShape_Mouth_entry40](https://user-images.githubusercontent.com/104311725/188324185-23fe1656-08de-454c-af8e-55b343a92a99.png)

The studio doesn't have the same gui. It simply shows the new index 40.

![Add_expression_06 - result](https://user-images.githubusercontent.com/104311725/188324511-138beb9e-8594-4115-a8ef-bb7ce9cbf905.png)

Since we did nothing about the other meshes in MouthCtrl, and pulled back the jaw related vertices in the new expression, the tongue now pokes through.

![Add_expression_00 - break_connection](https://user-images.githubusercontent.com/104311725/188318581-e565926e-9db2-4f06-8e9e-077012f433f3.png)
