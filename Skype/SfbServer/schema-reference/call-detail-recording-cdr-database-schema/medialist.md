---
title: MediaList 表格
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 7/12/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 1f440590-c1bc-483e-b7bc-6cc763847768
description: MediaList 表格是一種靜態表格，其中儲存了各種媒體類型清單。
ms.openlocfilehash: a72a409e9cc50fb5c8a7b340674276299e0ac4e9
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58596417"
---
# <a name="medialist-table"></a>MediaList 表格
 
MediaList 表格是一種靜態表格，其中儲存了各種媒體類型清單。
  
|**欄**|**資料類型**|**索引鍵/索引**|**詳細資料**|
|:-----|:-----|:-----|:-----|
|**MediaId** <br/> |Tinyint  <br/> |主要  <br/> |值：1-7  <br/> |
|**媒體** <br/> |Nvarchar (256)   <br/> || MediaID 和媒體值的靜態對應： <br/>  1 -- IM <br/>  2-檔案傳輸 <br/>  3-遠端協助 <br/>  4-應用程式共用 <br/>  5 -- 音訊 <br/>  6 -- 視訊 <br/>  7-應用程式邀請 <br/> |
   
若要嘗試判斷 SessionDetailsView LcsCDR 中的值的模態類型，您必須使用下列的聯接程式碼片段： 
  
```SQL
LEFT JOIN on Media.MediaId = MediaList.MediaId
```
