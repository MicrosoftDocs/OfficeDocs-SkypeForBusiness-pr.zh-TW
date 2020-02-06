---
title: 商務用 Skype Server 2015 中的 ConferenceJoinTimeThresholds 表格
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 3944d724-bdd8-4d1c-a2af-933ee8141529
description: ConferenceJoinTimeThresholds 資料表包含 [會議加入時間摘要] 報告所使用的分類界限。 [會議加入時間摘要] 報告總結使用者成功加入會議所需的時間量。這些時間值會以平均值及下列其中一個類別來報告：
ms.openlocfilehash: 1874a94448be5957079b1c53944bc127df761e5e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815391"
---
# <a name="conferencejointimethresholds-table-in-skype-for-business-server-2015"></a>商務用 Skype Server 2015 中的 ConferenceJoinTimeThresholds 表格
 
ConferenceJoinTimeThresholds 資料表包含 [會議加入時間摘要] 報告所使用的分類界限。 [會議加入時間摘要] 報告總結使用者成功加入會議所需的時間量。這些時間值會以平均值及下列其中一個類別來報告：
  
- 少於2秒。
    
- 介於2秒和5秒之間。
    
- 介於5秒和10秒之間。
    
- 10秒以上。
    
ConferenceJoinTimeThresholds 資料表包含2秒、5秒和10秒的分類值。
  
此表格是在 Microsoft Lync Server 2013 中推出。
  
|**左欄**|**資料類型**|**索引鍵/索引**|**詳細資料**|
|:-----|:-----|:-----|:-----|
|**ThresholdId** <br/> |int  <br/> |首選  <br/> |分類的唯一識別碼。  <br/> |
|**ThresholdValue** <br/> |int  <br/> || 分類的上限。 允許的值為： <br/>  2 <br/>  500 <br/>  第 <br/> |
   

