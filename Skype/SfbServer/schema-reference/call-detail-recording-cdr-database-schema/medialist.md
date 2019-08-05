---
title: MediaList 表格
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/12/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1f440590-c1bc-483e-b7bc-6cc763847768
description: MediaList 資料表是一個靜態資料表, 可儲存各種媒體類型的清單。
ms.openlocfilehash: 308a9eee57089a02b8e3ff9924e0d9d34162f33e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36192823"
---
# <a name="medialist-table"></a>MediaList 表格
 
MediaList 資料表是一個靜態資料表, 可儲存各種媒體類型的清單。
  
|**左欄**|**資料類型**|**索引鍵/索引**|**詳細資料**|
|:-----|:-----|:-----|:-----|
|**MediaId** <br/> |Tinyint  <br/> |首選  <br/> |值: 1-7  <br/> |
|**媒體** <br/> |Nvarchar (256)  <br/> || MediaID 和媒體值的靜態對應: <br/>  1--IM <br/>  2-檔案傳輸 <br/>  3-遠端協助 <br/>  4-應用程式共用 <br/>  5--音訊 <br/>  6--影片 <br/>  7-App 邀請 <br/> |
   
如果您要嘗試判斷 LcsCDR 中的值的模態類型, 則需要使用下列聯結程式碼片段: 
  
```
LEFT JOIN on Media.MediaId = MediaList.MediaId
```
