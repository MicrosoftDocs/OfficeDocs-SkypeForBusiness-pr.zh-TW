---
title: 商務用 Skype Server 2015 中的 ConferenceJoinTimeThresholds 表格
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 3944d724-bdd8-4d1c-a2af-933ee8141529
description: ConferenceJoinTimeThresholds 表格中包含「會議加入時間摘要報告」所使用的分類界限。「會議加入時間摘要報告」摘要說明了使用者成功加入會議所需的時間；在報告中這些時間值會以平均值及下列其中一項類別表示：
ms.openlocfilehash: 0ecdb432c5e386944e762016236e4c42fe6d9dae
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/05/2022
ms.locfileid: "62386311"
---
# <a name="conferencejointimethresholds-table-in-skype-for-business-server-2015"></a>商務用 Skype Server 2015 中的 ConferenceJoinTimeThresholds 表格
 
ConferenceJoinTimeThresholds 表格中包含「會議加入時間摘要報告」所使用的分類界限。「會議加入時間摘要報告」摘要說明了使用者成功加入會議所需的時間；在報告中這些時間值會以平均值及下列其中一項類別表示：
  
- 少於 2 秒。
    
- 介於 2 秒和 5 秒之間。
    
- 介於 5 秒和 10 秒之間。
    
- 超過 10 秒。
    
ConferenceJoinTimeThresholds 表格包含 2 秒、5 秒及 10 秒的分類值。
  
此表格已引進 Microsoft Lync Server 2013。
  
|**欄**|**資料類型**|**索引鍵/索引**|**詳細資料**|
|:-----|:-----|:-----|:-----|
|**ThresholdId** <br/> |int  <br/> |主要  <br/> |分類的唯一識別碼。  <br/> |
|**ThresholdValue** <br/> |int  <br/> || 分類的上限。允許的值為： <br/>  第 <br/>  5 <br/>  10  <br/> |
   

