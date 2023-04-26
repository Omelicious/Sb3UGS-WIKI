# Work In Progress

HS2 and KK and several other games have clothes split into top and bottom parts. The second state for the clothes is split likewise. This is reflected in the hierarchy and meshes have to be parented to childs of specific transforms with names like **n_top_a** e.i. That part of the hierarchy is the same for both games and is copied later. But the difference between games is the skeleton the meshes are bound to. So we are required to skin the meshes for KK.

This situation after importing HS2 clothes and the KK body.  
![01 - KK char and HS2 healer](https://user-images.githubusercontent.com/104311725/234534826-2460b609-f731-4a0a-832d-df62d6ad1f1b.png)  

The clothes are skinned for HS2 and that can be used to make a rough adaption for the size.  
![02 - rough adaption by scaling HS2 skeleton](https://user-images.githubusercontent.com/104311725/234534832-ce72177b-ef0c-453a-9ff8-56e090c8ecaa.png)  

The additional difference in height of the breasts and even the shape can be adapted by translating, rotating and scaling HS2 breast joints.  
![03 - smaller adaptions with HS2 joints](https://user-images.githubusercontent.com/104311725/234534837-0a22a577-2932-4b58-a1bd-e44cc67af636.png)  

Not all differences in proportions must be adapted at this point. But to reduce complexity of deformers we stopped here, and now copy the full mesh hierarchy with Ctrl-D (Edit / Duplicate) !  
![04 - copying hierarchy and meshes](https://user-images.githubusercontent.com/104311725/234534850-df1b1d1f-d841-46cf-845f-efcaac5a77a9.png)  
The new part of the hierarchy is then moved into the KK hierarchy by drag 'n drop with the middle mouse button.  
![04a - moving copied hierarchy and meshes](https://user-images.githubusercontent.com/104311725/234534858-3a048369-007f-41e4-8865-bf5d9bb5b9b4.png)
![05 - merge, shrinkwrap, etc](https://user-images.githubusercontent.com/104311725/234534861-a16bb50d-3c6b-43db-a7d8-fe64b06fd9be.png)
![06 - skinning 01 - import original meshes](https://user-images.githubusercontent.com/104311725/234534865-d9c6d551-74cf-441f-90ed-688d89990429.png)
![07 - skinning 02](https://user-images.githubusercontent.com/104311725/234534869-6f5083b4-9a50-4c72-abbe-1fc0c51b48e3.png)
![08 - skinning 03 - bind skeleton](https://user-images.githubusercontent.com/104311725/234534874-fbfefa3b-c3d5-4c90-9ced-d17bb2b0b09b.png)
![09 - skinning 04 - copy skin weights procedure](https://user-images.githubusercontent.com/104311725/234534883-99090064-547a-483d-89da-0cba163b124f.png)
![11 - verifying the skin using animations](https://user-images.githubusercontent.com/104311725/234534886-f749e604-e98c-4190-9072-d67d07a219fe.png)
![33 - bodymask painting](https://user-images.githubusercontent.com/104311725/234534894-e797a5a3-fe68-4a50-bda8-63c89165a584.png)
![34 - using existing bramask](https://user-images.githubusercontent.com/104311725/234534898-85150542-099b-4aa4-b504-9bb8e3bdd927.png)
![99 - first time in KK](https://user-images.githubusercontent.com/104311725/234534904-807ece96-8512-43fb-b97b-62ddd3b1cced.png)
