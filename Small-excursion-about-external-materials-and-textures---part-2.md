The files are taken from Honey Select release version, but the principle applies to all Unity based games.

Start Sb3UGS and open ca_head_06.unity3d alone.

![External_Links_Part_2_-_1](https://user-images.githubusercontent.com/104311725/167848044-bd3cb1f1-c4c6-4be8-b40b-1a753c4a4320.png)

ca_head_06.unity3d has one external reference which is always shown **checked**.

If you open another file which is unreferenced then this will be added to the list **unchecked**.

![External_Links_Part_2_-_2](https://user-images.githubusercontent.com/104311725/167848161-fc02e148-0286-4df0-b059-a94062854f23.png)

Here mat_cha_02.unity3d has been opened.

Check that entry to link the current file with this file. The link is one way only. It points to mat_cha_02.unity3d in this case, but mat_cha_02.unity3d will not get linked to ca_head_06.unity3d. You will get a message for this in the Log window.

Open the "Material & Texture Animator" by double clicking some materials and/or textures in mat_cha_02.unity3d.

Switch to ca_head_06.unity3d, open Animator p_acs_head_veil_hut and select MeshRenderer acs_head_veil_hut_base. Open the selection for materials.

![External_Links_Part_2_-_3](https://user-images.githubusercontent.com/104311725/167848244-9ddc711a-556d-466f-a157-522484a66145.png)

When you switch the material to such an external asset the material and textures are not copied into your file. You will not find a tab for Materials and Textures in your file. The submesh just references this material.