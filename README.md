# hw6_team_19
ISA525700 Computer Vision for Visual Effects
Assignment 6:Match Moving SLAM
Team 19


# Abstract
本研究探討SLAM (Simultaneous localization and mapping)方法產生相似於AR或MR影片的視覺效果，，輔以後製軟體產成成果進行視覺效果比較。

Keyword: SLAM,視覺效果


# Table of Contents
Introduction
Mothod
Example
Conclusion


# Introduction

本研究探討SLAM (Simultaneous localization and mapping)方法產生影片的視覺效果。實驗必須採用SLAM方法或match moving technique，在影片中置入至少一個物體，它可以是3D model、2D image或文字。本實驗採自攝影片，以ORB-SLAM2製作影片，輔以後製軟體製作影片為比較方法。依提示過程中使用Rotating與zooming in or out製造視覺效果，並且影片中有Insert 3D Model。


# Mothod

## SLAM
SLAM是軟體機器人，可自動同步執行在map上建立object，而object在map具有合體視覺效果。Visual SLAM須透過攝影裝置進行SLAM。ORB-SLAM2
- 用於單眼相機、3D，同時可以計算攝影機軌跡與少部份3D重建(立體聲和RGB-D可據真實比例)。
- 能夠循環辨識與與重新定位攝影機，KITTI資料集提供SLAM系統作3D與單眼執行。
- 可以在無ROS情形下編譯。
- 可在不同SLAM之間進行切換GUI與本地化模式。
- 已在Ubuntu 12.04,14.04和16.04兩種版本測試後，確定為容易編譯、高效能與更佳穩定。
- 可以平行執行影像追蹤、區域定位、關閉循環等3個執行緒。


## [Example 1] Motion parallax

Concept
	 

Experiment

Analysis 


Discussion


## [Example 2] Stop motion

Concept


Experiment


Analysis 

discussion


## [Example 3]Live photo
Concept


Experiment


Analysis 

discussion


# Conclusion



# Reference
- [1] 
- [2] 
- [3] 

