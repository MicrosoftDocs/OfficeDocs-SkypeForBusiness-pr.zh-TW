---
title: 商務用 Skype Server 2015 中的 ConferenceUris 表格
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
ms.assetid: b1721d52-3c65-45ea-8997-06af8fef93fc
description: ConfereneUris 資料表是一個支援資料表，可儲存已參與在資料庫中的會議會話的各種會議 Uri 清單。 資料表中的每一筆記錄代表一個會議 URI。
ms.openlocfilehash: f1e95cce4fedf26477973a4fba6a9d3a32288f92
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815311"
---
# <a name="conferenceuris-table-in-skype-for-business-server-2015"></a>商務用 Skype Server 2015 中的 ConferenceUris 表格
 
ConfereneUris 資料表是一個支援資料表，可儲存已參與在資料庫中的會議會話的各種會議 Uri 清單。 資料表中的每一筆記錄代表一個會議 URI。
  
|**左欄**|**資料類型**|**索引鍵/索引**|**詳細資料**|
|:-----|:-----|:-----|:-----|
|**NextUpdateTS** <br/> |datetime  <br/> |首選  <br/> |時間戳記，內部使用。  <br/> |
|**ConferenceUriId** <br/> |int  <br/> |首選  <br/> |標識此會議 URI 的唯一號碼。  <br/> |
|**ConferenceUri** <br/> |Nvarchar （450）  <br/> ||會議 URI。  <br/> |
|**求和** <br/> |int  <br/> ||ConferenceUri 的校驗和。 用來提高資料庫搜尋的速度。  <br/> |
|**UriTypeId** <br/> |int  <br/> |外  <br/> |URI 類型，例如會議： IM 會議的聊天或會議：音訊/視訊會議的音訊-視頻。 如需詳細資訊，請參閱[UriTypes 資料表](uritypes.md)表格。 <br/> |
   

