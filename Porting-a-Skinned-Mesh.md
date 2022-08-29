HS2 has bigger coordinate values than KK. The rucksack and its skeleton need to be scaled down. But KK doesn't like scaling for two reasons: DynamicBones run wild, and outlines get scaled as well. The former would apply to all games with DynamicBones.

We import one original similar mesh to get the size right, and the original rucksack from HS2. Since Maya merges Transforms nicely, some renaming beforehand prevents merging. Both games require N_move e.i.

![Porting a Skinned Mesh - 01](https://user-images.githubusercontent.com/104311725/187253541-c670459a-f9f9-4ed3-ad2f-a9ca1f60feea.png)

We scale down the root bone of the skeleton first. Both pairs of shoulder straps (original KK backpack is the grey one and HS2 rucksack) are close now. 
![Porting a Skinned Mesh - 02](https://user-images.githubusercontent.com/104311725/187253109-cb7bd84c-f93a-4a7e-a5be-8226dcd8805d.png)

Copying the skeleton (joint0 and childs down to joint3) creates a copy with a new name joint4 as child of N_move. Moving this skeleton to its destination KKFBXASC045N_move allows to rename joint4 back to joint0. 
![Porting a Skinned Mesh - 03](https://user-images.githubusercontent.com/104311725/187253122-40029f67-9092-409e-8109-a23b1e0afe08.png)

Now we get rid of the scaling in the Channel Box / Layer editor. 
![Porting a Skinned Mesh - 04](https://user-images.githubusercontent.com/104311725/187253132-0e2f902a-5351-4ae2-a3c3-ec35109f1be6.png)

Then we copy the mesh Transform (with its mesh) and move the copy to its destination. 

![Porting a Skinned Mesh - 05 - an unskinned copy](https://user-images.githubusercontent.com/104311725/187253143-d9bc20f6-43e6-49f8-8d67-fd2a3cfc5a02.png)

Bind the new mesh to the new skeleton. 

![Porting a Skinned Mesh - 06 - default skin](https://user-images.githubusercontent.com/104311725/187253147-4a038092-97f4-44cf-aee9-8de1321c6fe7.png)

Copy the skin weights by name. 

![Porting a Skinned Mesh - 07 - copy skin weights by name](https://user-images.githubusercontent.com/104311725/187253155-8d9aba66-c99a-4b56-ade1-e645c422c786.png)

Before export we do some renaming to simplify replacement (also see [Replacing Meshes](https://github.com/enimaroah-cubic/Sb3UGS/wiki/Replacing-Meshes)). 
![Porting a Skinned Mesh - 08 - export import replace](https://user-images.githubusercontent.com/104311725/187253161-4feeb8d1-1fbe-4068-83b9-2fbaa2ff1a29.png)

DynamicBone values had been copied as well. And since we roughly scaled down by 10, radius and similar values need to be scaled accordingly. 
![Porting a Skinned Mesh - 09](https://user-images.githubusercontent.com/104311725/187253173-1bc8b053-f4f8-4f11-a326-1b9cb595d946.png)
