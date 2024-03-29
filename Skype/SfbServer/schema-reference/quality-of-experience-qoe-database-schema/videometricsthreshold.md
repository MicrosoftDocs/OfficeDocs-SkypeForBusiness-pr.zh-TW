---
title: VideoMetricsThreshold 表格
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: 2e2f4711-35ba-48c6-b15b-5aba61c4eb75
description: VideoMetricsThreshold 資料表包含了最佳且可接受的值，供經驗品質搭配視訊通話使用。
---

# <a name="videometricsthreshold-table"></a>VideoMetricsThreshold 表格
 
VideoMetricsThreshold 資料表包含了最佳且可接受的值，供經驗品質搭配視訊通話使用。
  

| **欄**                                               | **資料類型**       | **索引鍵/索引**  | **詳細資料**                          |
|:---------------------------------------------------------|:--------------------|:---------------|:-------------------------------------|
| **CallType** <br/>                                       | int  <br/>          | 主要  <br/> | 被指定的電話類型。  <br/> |
| **VideoPostFECPLROptimal** <br/>                         | 十進位 (5，2)   <br/> |                | 預設值為 0.05。  <br/>    |
| **VideoPostFECPLRAcceptable** <br/>                      | 十進位 (5，2)   <br/> |                | 預設值為 0.10。  <br/>    |
| **VideoLocalFrameLostPercentageAverageOptimal** <br/>    | 十進位 (5，2)   <br/> |                | 預設值為 5.0。  <br/>     |
| **VideoLocalFrameLostPercentageAverageAcceptable** <br/> | 十進位 (5，2)   <br/> |                | 預設值為 10.0。  <br/>    |
| **RecvFrameRateAverageOptimal** <br/>                    | 十進位 (9，4)   <br/> |                | 預設值為 12.0000。  <br/> |
| **RecvFramerateAverageAcceptable** <br/>                 | 十進位 (9，4)   <br/> |                | 預設值為 7.0000。  <br/>  |
| **LowFrameRateCallPercentOptimal** <br/>                 | 十進位 (5，2)   <br/> |                | 預設值為 5.0。  <br/>     |
| \****LowFrameRateCallPercentAcceptable** _\_ <br/>        | 十進位 (5，2)   <br/> |                | 預設值為 10.0/。  <br/>    |
| **LowResolutionCallPercentOptimal** <br/>                | 十進位 (5，2)   <br/> |                | 預設值為 5.0。  <br/>     |
| **LowResolutionCallPercentAcceptable** <br/>             | 十進位 (5，2)   <br/> |                | 預設值為 10.0。  <br/>    |
| **VideoPacketLossRateOptimal** <br/>                     | foat  <br/>         |                | 預設值為 0.05。  <br/>    |
| **VideoPacketLossRateAcceptable** <br/>                  | float  <br/>        |                | 預設值為 0.10。  <br/>    |
| **VideoFrameRateAvgOptimal** <br/>                       | float  <br/>        |                | 預設值為 12。  <br/>      |
| **VideoFrameRateAvgAcceptable** <br/>                    | float  <br/>        |                | 預設值為 7。  <br/>       |
| **DynamicCapabilityPercentOptimal** <br/>                | 十進位 (5，2)   <br/> |                | 預設值為 5.00。  <br/>    |
| **DynamicCapabilityPercentAcceptable** <br/>             | 十進位 (5，2)   <br/> |                | 預設值為 10.00。  <br/>   |

