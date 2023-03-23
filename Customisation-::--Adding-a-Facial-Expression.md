A new blendshape is created and added as described in [[Morphs or Blendshapes]] described.
![Add_expression_01](https://user-images.githubusercontent.com/104311725/188323195-62798d13-899d-4cf1-bd36-0d6b554386b8.png)

![Add_expression_02](https://user-images.githubusercontent.com/104311725/188323343-cac08264-3fcc-4d78-92cf-c1ea12b023bf.png)

The new blendshape here is at index 81. We need to find a free slot in FaceBlendShape MonoBehaviour. The list of named expressions for the Character Maker is in abdata\custom\customscenelist\00.unity3d in MonoBehaviour cus_m_ptn.

![Add_expression_03 - chara_maker_mouth](https://user-images.githubusercontent.com/104311725/188323593-e861d8dc-8406-40b4-9ed4-3f9ef65650b3.png)

We add a new line, in this case with "40, M exp 40" and extend all arrays in MouthCtrl. Index 40 will be used for each mesh when the new expression will be selected in game. In this case there are more entries right from the start. Those exceeding entries are unused and can not be selected in the Character Maker.

![Add_expression_04 - FaceBlendShape_Mouth_meshes](https://user-images.githubusercontent.com/104311725/188323899-90ee0e71-153f-42b3-a496-515f3cd6f5ae.png)

Here we put our index 81 for the new expression. The Close expression is the shown when the slider in the game is fully left. And Open is the right most position.

![Add_expression_05 - FaceBlendShape_Mouth_entry40](https://user-images.githubusercontent.com/104311725/188324185-23fe1656-08de-454c-af8e-55b343a92a99.png)

The studio doesn't have the same gui. It simply shows the new index 40.

![Add_expression_06 - result](https://user-images.githubusercontent.com/104311725/188327260-0409c1c5-d160-4b85-9607-a8ff5ce0dd39.png)

Since we did nothing about the other meshes in MouthCtrl, and pulled back the jaw related vertices in the new expression, the tongue now pokes through. In the Character Maker the chin is the fifth slider in the third section - shown value 11.

In abdata\list\customshape.unity3d is the definition for the sliders. In the first column is the slider index. Each line is for one Transform, and for some sliders there are several lines. 

![Add_expression_07 - customization_mask](https://user-images.githubusercontent.com/104311725/188325498-8abc04f0-44f6-48c4-8ad2-8e97747f1533.png)

In this case the chin has only one Transform cf_J_Chin_Base. The following columns are translation(X, Y, Z), rotation(X, Y, Z) and scaling(X, Y, Z). A value of 0 indices that the component is unused, 1 means that it is used. In this example only translation for Z is used. 

In the head's AB we find TextAsset cf_anmShapeHead_00. 

![Add_expression_08 - cf_anmShapeHead_curves](https://user-images.githubusercontent.com/104311725/188326256-759f2a3f-2f6a-457b-843b-8b1c6a3eac51.png)

All columns form nine curves for translation(X, Y, Z), rotation(X, Y, Z), scaling(X, Y, Z) with 25 keys for the Transform in the first column. If the line would be broken for each animation key, it would look like this (meant for understanding only. You don't have to do this for modding.): 

![Add_expression_09 - customization_curve](https://user-images.githubusercontent.com/104311725/188326342-f146c352-a123-4c7c-b162-63ffb0b88af3.png)

The tongue mesh with its morphs imported, the MouthCtrl's corresponding morph t00_sinken03_op fully used, the curve from above keyed, then the timeslider is set to 11 (slider value from chin) * 24 (last key index) / 100 (slider max for chin) = 2.64 and we see the tongue poking through like in the Character Maker. 

![Add_expression_10 - simulated](https://user-images.githubusercontent.com/104311725/188327021-d98d54d3-5547-45a5-870a-d83ae0934472.png)

### Special cases for toon eyes
abdata\list\characustom\00.unity3d has the policy for all heads and adding a new expression in it for only one head would cause problems for the others.
![image](https://user-images.githubusercontent.com/104311725/227203629-411bf77a-1c43-4b4b-b9b8-dbf376730447.png)

