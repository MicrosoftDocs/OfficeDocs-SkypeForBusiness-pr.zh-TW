---
title: MonitoredRegionLink 表格
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: cebda194-7be3-42d6-b6f0-c86f8b0f200a
description: MonitoredRegionLink 資料表是支援資料表。 每筆記錄代表兩個國家/地區之間的一個連結。
ms.openlocfilehash: a6b92460e2b097460681023f7d6877f02c046bdc
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41807811"
---
# <a name="monitoredregionlink-table"></a>MonitoredRegionLink 表格
 
MonitoredRegionLink 資料表是支援資料表。 每筆記錄代表兩個國家/地區之間的一個連結。
  
|**左欄**|**資料類型**|**索引鍵/索引**|**詳細資料**|
|:-----|:-----|:-----|:-----|
|**Region1Key** <br/> |int  <br/> |主要、外部  <br/> |從[Region 資料表](region.md)中參照。  <br/> |
|**Region2Key** <br/> |int  <br/> |主要、外部  <br/> |從[Region 資料表](region.md)中參照。  <br/> |
   

