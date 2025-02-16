MagicaBoneCloth (MBC) consists of four MonoBehaviours, that play together. The MagicaBoneCloth MB is integrated into the hierarchy, either in the root or close to the strand it works on. It has references to a ClothData MB, a SelectionData MB and a MeshData MB. The SelectionData MB seems to be optional, but can also be shared by several MagicaBoneCloth MBs. If ClothData MB or MeshData MB are not present, the strand doesn't get animated from the MBC.

MBCs can be referenced from ChaClothesComponent MB but there was no example of ChaClothesComponent which used it. The more interesting usage is in ChaCustomHairComponent MB and there those MBCs are always present, except for "Movers". See the example below.

The helpers in Sb3UGS aim to make MBCs valid. They have nothing related to the physics, nor do they reference MBCs automatically in ChaCustomHairComponent MBs. To get a good behaviour in your hair or clothes choose an original with those physics for copying. See the workflow at the bottom.


### Single Root

![image](https://github.com/enimaroah-cubic/Sb3UGS/assets/104311725/ad8c9244-6a61-40bc-b87b-5d924a397f07)



### Multi Root

MBC MB inside the hierarchy like in the single strand situation


![image](https://github.com/enimaroah-cubic/Sb3UGS/assets/104311725/1ff09f94-7428-4b95-b6fd-bfca04b3ce68)



### Multi Root

MBC MB at the root of the hierarchy


![image](https://github.com/enimaroah-cubic/Sb3UGS/assets/104311725/480f57fd-2d98-497a-9e2d-8382d7029892)



### Single Root With Mover

![image](https://github.com/enimaroah-cubic/Sb3UGS/assets/104311725/d3fdc6d0-64f4-4241-a11c-4d27da04d506)



### Odd Single Root

![image](https://github.com/enimaroah-cubic/Sb3UGS/assets/104311725/b14717c2-7b33-4b1f-b689-66a2957bb052)



MBCs are handled like all other MBs in Sb3UGS. Copying is drag 'n drop, even inside the same hierarchy. Since there are different configurations (single root, single root with mover, etc) you want to copy the best match for your situation. In case of movers, copy both MBCs into your hierarchy's strand. The computations in Sb3UGS consider those movers.

The workflow:
1. edit the root(s) first
2. "Check MagicaBoneCloth"
3. correct MBC MB first before the other MBs

If you want to retain a member's data uncheck its checkbox. Sb3UGS skips it for new creation, but computes depending members with the member's unchanged data.

If you compute any of the MBs and have opened an MB editor this editor does not refresh automatically. Use "Revert" to see the computed data.