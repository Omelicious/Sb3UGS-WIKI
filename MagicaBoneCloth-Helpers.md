MagicaBoneCloth (MBC) consists of four MonoBehaviours, that play together. The MagicaBoneCloth MB is integrated into the hierarchy, either in the root or close in hierarchy to the strand it works on. It has references to a ClothData MB, a SelectData MB and a MeshData MB. The SelectData MB seems to be optional, but can also be shared by several MagicaBoneCloth MBs. If ClothData MB or MeshData MB are not present, the strand doesn't get animated from the MBC.

### Single Root

![image](https://github.com/enimaroah-cubic/Sb3UGS/assets/104311725/ad8c9244-6a61-40bc-b87b-5d924a397f07)



### Multi Root

MBC MB inside the hierarchy like in the single strand situation


![image](https://github.com/enimaroah-cubic/Sb3UGS/assets/104311725/1ff09f94-7428-4b95-b6fd-bfca04b3ce68)



### Multi Root

MBC MB at the root of the hierarchy


![image](https://github.com/enimaroah-cubic/Sb3UGS/assets/104311725/da2e8cfe-767a-4e8a-a5bc-515990c7ead3)



### Single Root With Mover

![image](https://github.com/enimaroah-cubic/Sb3UGS/assets/104311725/d3fdc6d0-64f4-4241-a11c-4d27da04d506)



### Odd Single Root

![image](https://github.com/enimaroah-cubic/Sb3UGS/assets/104311725/b14717c2-7b33-4b1f-b689-66a2957bb052)
