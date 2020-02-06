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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 1f440590-c1bc-483e-b7bc-6cc763847768
description: MediaList 資料表是一個靜態資料表，可儲存各種媒體類型的清單。
ms.openlocfilehash: 7742baf17240ca810268721c0e47e37f17e555cd
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815031"
---
# <a name="medialist-table"></a>MediaList 表格
 
MediaList 資料表是一個靜態資料表，可儲存各種媒體類型的清單。
  
|**左欄**|**資料類型**|**索引鍵/索引**|**詳細資料**|
|:-----|:-----|:-----|:-----|
|**MediaId** <br/> |Tinyint  <br/> |首選  <br/> |值：1-7  <br/> |
|**媒體** <br/> |Nvarchar （256）  <br/> || MediaID 和媒體值的靜態對應： <br/>  1--IM <br/>  2-檔案傳輸 <br/>  3-遠端協助 <br/>  4-應用程式共用 <br/>  5--音訊 <br/>  6--影片 <br/>  7-App 邀請 <br/> |
   
如果您要嘗試判斷 LcsCDR 中的值的模態類型，則需要使用下列聯結程式碼片段： 
  
```json
LEFT JOIN on Media.MediaId = MediaList.MediaId
```
