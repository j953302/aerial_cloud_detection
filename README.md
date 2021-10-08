# aerial_cloud_detection
利用Mask_Rcnn與HSV 做簡易pixel-wise 的雲層檢測，並簡易推斷厚雲與薄雲的面積。

##過程與結果
1. 先利用現有的資料(約略200張)做labelme的Mask標定，再轉至Mask_rcnn可訓練的資料做訓練，原始資料如下：
![image](https://github.com/j953302/aerial_cloud_detection/blob/main/Result/201022a_012.jpg)

2. 獲得Mask Rcnn初步雲朵位置，因這次的訓練資料較少，所以訓練10次，每次100筆資料訓練，loss如下圖：
![image](https://github.com/j953302/aerial_cloud_detection/blob/main/Result/loss.jpg)
![image](https://github.com/j953302/aerial_cloud_detection/blob/main/Result/201022a_012.png)
這裡的結果沒有很精準是沒問題的，目的只是框選出大部分雲朵的pixel

3. 統計Mask所選取的Pixel HSV中的V值，透過這統計來分析該張相片的厚、薄雲的V閥值
![image](https://github.com/j953302/aerial_cloud_detection/blob/main/Result/201022a_012_dst1.png)
