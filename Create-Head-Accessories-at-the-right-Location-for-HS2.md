1. In this example I used N_Head_top because it is the attachment point used for the original's list entry of the halloween hat
![Head_Accessories_Location_1](https://user-images.githubusercontent.com/104311725/167849360-604e24f1-4af1-421a-a269-55fadd160e38.png)
2. **Combined** computes the world tranformation matrix
3. **Copy** this matrix into **Matrix # 1**
4. Select **N_move** Transform in the halloween hat's hierarchy
5. **Paste** from **Matrix #1**, then **Apply Changes**

![Head_Accessories_Location_2](https://user-images.githubusercontent.com/104311725/167849479-1eb2f5a3-db24-4d55-a926-9ddc36ad0355.png)

So in your 3d editor you would put that matrix into your **N_move** Transform during editing. But before exporting you would set it to Identity.