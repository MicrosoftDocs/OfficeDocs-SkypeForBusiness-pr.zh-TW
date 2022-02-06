---
title: 商務用 Skype Server 2015 中的對話方塊表格
ms.reviewer: null
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
ms.assetid: 487a430b-af66-4ea6-b28e-4e33cfdb7f9e
description: 對話方塊表格是一種支援資料表，可儲存點對點工作階段之 Dialogid 的相關資訊。
---

# <a name="dialogs-table-in-skype-for-business-server-2015"></a>商務用 Skype Server 2015 中的對話方塊表格
 
對話方塊表格是一種支援資料表，可儲存點對點工作階段之 Dialogid 的相關資訊。
  
|**欄**|**資料類型**|**索引鍵/索引**|**詳細資料**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |主要  <br/> |會話要求的時間;與 SessionIDSeq 搭配使用，以唯一識別會話。  <br/> |
|**SessionIdSeq** <br/> |int  <br/> |主要  <br/> |識別工作階段的 ID 號碼。 與 SessionIDTime 搭配使用，以唯一識別會話。  <br/> |
|**ExternalChecksum** <br/> |int  <br/> | <br/> |ExternalID 的校驗和。 此欄位是用來增加資料庫搜尋的速度。  <br/> |
|**ExternalId** <br/> |Varbinary (775)   <br/> | <br/> |以二進位儲存的 SIP 對話方塊識別碼。 二進位檔案的格式為：  <br/> dialog; 從-標籤; to-標記  <br/> 您可以使用下列語法將此資料轉換成文字格式：  <br/>  `cast(cast(ExternalId as varbinary(max)) as varchar(max))` <br/> |
   

