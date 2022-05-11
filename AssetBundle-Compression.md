Unity supports AssetBundle compression. This means that the whole file is compressed - it has nothing to do with texture compression.

Sb3UGS has an indicator in front of the filename for compression.

![Compressed_regular_AssetBundle](https://user-images.githubusercontent.com/104311725/167833864-e322bf92-d98a-4421-a855-25958962a9fe.png)

If you want to know which compression method had been used for a file, you can dump the file information into the Log window.

Saving any file with compression will close it after writing the file.

![Compress_instead_of_Save](https://user-images.githubusercontent.com/104311725/167834076-63060452-2254-49dd-881d-1142f4849032.png)

In case of zipmods, you want to make sure that your final AssetBundle is compressed with LZ4H.