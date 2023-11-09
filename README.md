# SARL1BMatch

A docker of our proposed multi-view SAR image matching method published at IEEE TGRS 2022. It can be downloaded from this link:

# How to use 
1. Load this docker in Ubuntu 18.04. (sudo docker load -i xymtest.tar.gz)
2. Prepare test data.
   
   2.1 Create a folder in /mnt/test
   
   2.2 Create a txt file named List.txt, which contains the absolute path of the SAR data to be tested. There are two rows, with each row storing tiff/RPC/meta.xml separated by a tab. An example is given as follows,
   ![image](https://github.com/xym2009/SARL1BMatch/assets/19380078/b8d83993-5d3f-4722-bcc9-291085a9da52)

   2.3 Put the DEM file covering the SAR data in /mnt/test, and rename it to DEM.tif. An example is given as follows,
   ![image](https://github.com/xym2009/SARL1BMatch/assets/19380078/94a57c94-0f00-48e8-9003-11b94170b48a)

3. Implementation: sudo docker run --rm -v /mnt/:/mnt sarmatchbyxym:latest
4. The output is stored in the folder /mnt/test/output/, which includes two matched geotiffs and the file of correspondences.
![image](https://github.com/xym2009/SARL1BMatch/assets/19380078/607b89a2-90ae-4c6d-a154-5aa8eb5bc23d)
5. The correspondences are stored in txt format. The first line is the number of all-matches. Then each line is stored in the following type,
    Num imgx1 imgy1 imgx2 imgy2 1.0 lon1 lat1 height1 lon2 lat2 height2
![image](https://github.com/xym2009/SARL1BMatch/assets/19380078/40ebb3f0-d6be-4594-a7a8-c9b6d55c930e)

# Notice
This docker is only suitable for GaoFen-3 SLC images (A C-band SAR satellite of China), since we have to read the metaXML of SAR images. We only tested GF-3 SAR images with spotlight and strip modes.

# Contact Us
If you have any questions on this method or this docker, please contact Yuming Xiang (z199208081010@163.com/xiangym@aircas.ac.cn).

For more details, please refer to the corresponding paper: "A Geometry-Aware Registration Algorithm for Multiview High-Resolution SAR Images" (https://ieeexplore.ieee.org/abstract/document/9882139).

If you are using this method in your project, we kindly ask you to cite:

    @article{xiang2022geometry,
      title={A Geometry-Aware Registration Algorithm for Multiview High-Resolution SAR Images},
      author={Xiang, Yuming and Jiao, Niangang and Liu, Rui and Wang, Feng and You, Hongjian and Qiu, Xiaolan and Fu, Kun},
      journal={IEEE Transactions on Geoscience and Remote Sensing},
      volume={60},
      pages={1--18},
      year={2022},
      publisher={IEEE}
    }

