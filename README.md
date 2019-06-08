# hw6_team_19
ISA525700 Computer Vision for Visual Effects<br/>Assignment 6: Match Moving SLAM<br/>
===


# Abstract
本研究探討ORB-SLAM 2(Simultaneous localization and mapping)方法，經由Tracking、Mapping、Relocalization、Loop closing，產生相似於AR或MR影片的視覺效果，輔以後製軟體輸出成果進行視覺效果比較。

Keyword: ORB-SLAM2, Tracking, Mapping, Relocalization, Loop closing



# Table of Contents
1. [Introduction](#Introduction)
2. [Method](#Method)
3. [Result](#Result) 
4. [Conclusion](#Conclusion)
5. [Reference](#Reference)


# Introduction

- 本研究探討SLAM (Simultaneous localization and mapping)方法產生影片的視覺效果。實驗必須採用SLAM方法或match moving technique，在影片中置入至少一個物體，它可以是3D model、2D image或文字。 
- 本實驗採自攝影片，以ORB-SLAM2製作影片，輔以後製軟體製作影片為比較方法。依提示過程中使用Rotating與zooming in or out製造視覺效果，並且影片中有Insert 3D Model。


# Mothod

ORB-SLAM是Raul Mur-Artal, J. M. M. Montiel和Juan D. Tardos於2015共同發表在IEEE Transactions on Robotics。ORB-SLAM是基於Real-Time單眼，大小規模與室內外均可適用，對於劇烈運動也具有絕佳效果。支援閉環檢測與重新定位，包含全自動初始化。該系統含蓋SLAM所有模組，如跟蹤（Tracking）、建圖（Mapping）、重定位（Relocalization）、閉環檢測（Loop closing）。由於ORB-SLAM系統是基於feature mapping，能即是計算出相機移動軌跡Moving track，創造重建3D Scenes，ORB-SLAM2係在ORB-SLAM的基礎上，且支持標註定位後的雙眼相機和RGB-D相機。  

-	Tracking 
主要工作為從根據上一frame計算，影像提取ORB feature，或進行全域重新初始化定位，然後追蹤已重建局部地圖，優化定位值，最後依據一些規則，確定新的key frame.   

-	Local Mapping 
這一部分主要完成局部地圖建構。包括對key frame的插入，驗證最近生成的地圖點並進行篩選，然後產生新的地圖點，使用局部捆集調整（Local BA），最後再對插入的key frame進行篩選，刪除多餘的key frame。

-	Loop Closing 
這主要分為兩個Process，分別是閉環探測和閉環校正。閉環檢測先使用WOB進行探測，然後Sim3演算法計算相似變換。閉環校正，主要是閉環融合和Essential Graph的圖片優化。

SLAM是軟體機器人，可自動同步執行在map上建立object，而object在map具有合體視覺效果。Visual SLAM須透過攝影裝置進行SLAM。

ORB-SLAM2有以下特點
- 用於單眼相機、3D，同時可以計算攝影機軌跡與少部份3D重建(立體聲和RGB-D可據真實比例)。
- 能夠循環辨識與與重新定位攝影機，KITTI資料集提供SLAM系統作3D與單眼執行。
- 可以在無ROS情形下編譯。
- 可在不同SLAM之間進行切換GUI與本地化模式。
- 已在Ubuntu 12.04,14.04和16.04兩種版本測試後，確定為容易編譯、高效能與更佳穩定。
- 可以平行執行影像追蹤、區域定位、關閉循環等3個執行緒。


# Result
因製作視覺效果考量下，我們以旋轉攝影與坐姿動作自攝影片。

## Take videos by myselves 

這是在NTHU圖書館拍攝實驗一的原始影片。

[![](http://img.youtube.com/vi/tgXU5NZu7Ak/0.jpg)](http://www.youtube.com/watch?v=tgXU5NZu7Ak "")

這是在實驗室所自己拍攝實驗二影片。

[![](http://img.youtube.com/vi/xSsBWGHv6ls/0.jpg)](http://www.youtube.com/watch?v=xSsBWGHv6ls "")


## Generate the Simultaneous localization and mapping of 3D visual effects

在第一組實驗中，首先取得feature與Trajectory，插入2D image與3D model，在Rotating與zooming in or out微調下，產生match moving technique視覺效果

[![](http://img.youtube.com/vi/xC0J4mSv2Ug/0.jpg)](http://www.youtube.com/watch?v=xC0J4mSv2Ug "")

在第二組實驗中，首先取得feature與Trajectory，插入3D model，用Rotating與zooming in or out微調下，產生match moving technique視覺效果。

[![](http://img.youtube.com/vi/Wy0xvm-Zk7U/0.jpg)](http://www.youtube.com/watch?v=Wy0xvm-Zk7U "")

## Compare above methods
 在實驗一與實驗二比較後，取得feature與Trajectory，讓Virtual object貼近真實object有最AR與MR視覺效果。


# Conclusion
-	在實驗一與實驗二比較後，Virtual object貼近真實object有最AR與MR視覺效果。
- 在實驗一中，使用Rotating與zooming in or out，可以產生最佳的Augmented reality與Mixed reality。
- 在實驗二中，Multi-layer的3D image經由alignment，配合blur、zoom out-in等技術製成3D model插入真實視景，Energy ball產生Stop motion與Motion parallax效果。

# Reference
-	 [1] [Monocular] Raúl Mur-Artal, J. M. M. Montiel and Juan D. Tardós. ORB-SLAM: A Versatile and Accurate Monocular SLAM System. IEEE Transactions on Robotics, vol. 31, no. 5, pp. 1147-1163, 2015. (2015 IEEE Transactions on Robotics Best Paper Award).

-	[2]Tardós. ORB-SLAM2: an Open-Source SLAM System for Monocular, Stereo and RGB-D Cameras. IEEE Transactions on Robotics, vol. 33, no. 5, pp. 1255-1262, 2017.




