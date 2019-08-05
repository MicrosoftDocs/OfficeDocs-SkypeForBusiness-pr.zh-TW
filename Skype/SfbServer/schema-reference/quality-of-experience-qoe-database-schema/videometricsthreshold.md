---
title: VideoMetricsThreshold 資料表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2e2f4711-35ba-48c6-b15b-5aba61c4eb75
description: VideoMetricsThreshold 表格包含與視頻通話搭配使用之經驗統計之品質的最佳和可接受的值。
ms.openlocfilehash: a923334596ea6b3e6b56c43682be0f0f6a640f15
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36192612"
---
# <a name="videometricsthreshold-table"></a>VideoMetricsThreshold 資料表
 
VideoMetricsThreshold 表格包含與視頻通話搭配使用之經驗統計之品質的最佳和可接受的值。
  

| **左欄**                                               | **資料類型**       | **索引鍵/索引**  | **詳細資料**                          |
|:---------------------------------------------------------|:--------------------|:---------------|:-------------------------------------|
| **CallType** <br/>                                       | int  <br/>          | 首選  <br/> | 所撥打的通話類型。  <br/> |
| **VideoPostFECPLROptimal** <br/>                         | decimal (5, 2)  <br/> |                | 預設值為0.05。  <br/>    |
| **VideoPostFECPLRAcceptable** <br/>                      | decimal (5, 2)  <br/> |                | 預設值為0.10。  <br/>    |
| **VideoLocalFrameLostPercentageAverageOptimal** <br/>    | decimal (5, 2)  <br/> |                | 預設值為5.0。  <br/>     |
| **VideoLocalFrameLostPercentageAverageAcceptable** <br/> | decimal (5, 2)  <br/> |                | 預設值為10.0。  <br/>    |
| **RecvFrameRateAverageOptimal** <br/>                    | 十進位 (9, 4)  <br/> |                | 預設值為12.0000。  <br/> |
| **RecvFramerateAverageAcceptable** <br/>                 | 十進位 (9, 4)  <br/> |                | 預設值為7.0000。  <br/>  |
| **LowFrameRateCallPercentOptimal** <br/>                 | decimal (5, 2)  <br/> |                | 預設值為5.0。  <br/>     |
| \****LowFrameRateCallPercentAcceptable***\* <br/>        | decimal (5, 2)  <br/> |                | 預設值為 10.0/  <br/>    |
| **LowResolutionCallPercentOptimal** <br/>                | decimal (5, 2)  <br/> |                | 預設值為5.0。  <br/>     |
| **LowResolutionCallPercentAcceptable** <br/>             | decimal (5, 2)  <br/> |                | 預設值為10.0。  <br/>    |
| **VideoPacketLossRateOptimal** <br/>                     | foat  <br/>         |                | 預設值為0.05。  <br/>    |
| **VideoPacketLossRateAcceptable** <br/>                  | 浮  <br/>        |                | 預設值為0.10。  <br/>    |
| **VideoFrameRateAvgOptimal** <br/>                       | 浮  <br/>        |                | 預設值為12。  <br/>      |
| **VideoFrameRateAvgAcceptable** <br/>                    | 浮  <br/>        |                | 預設值為7。  <br/>       |
| **DynamicCapabilityPercentOptimal** <br/>                | decimal (5, 2)  <br/> |                | 預設值為5.00。  <br/>    |
| **DynamicCapabilityPercentAcceptable** <br/>             | decimal (5, 2)  <br/> |                | 預設值為10.00。  <br/>   |

