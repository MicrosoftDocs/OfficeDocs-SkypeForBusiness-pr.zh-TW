---
title: 商務用 Skype Server 2015 中的 ConferenceUris 表格
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b1721d52-3c65-45ea-8997-06af8fef93fc
description: ConfereneUris 表格是一種支援表格，可儲存參與于資料庫中的會議會話的各個會議 URIs 清單。 表格中的每一筆記錄都代表一個會議 URI。
ms.openlocfilehash: f21e86324559f909ad5a38cd2447003967d21819e9195ab9c73a4e84888cf9b9
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54295390"
---
# <a name="conferenceuris-table-in-skype-for-business-server-2015"></a>商務用 Skype Server 2015 中的 ConferenceUris 表格
 
ConfereneUris 表格是一種支援表格，可儲存參與于資料庫中的會議會話的各個會議 URIs 清單。 表格中的每一筆記錄都代表一個會議 URI。
  
|**欄**|**資料類型**|**索引鍵/索引**|**詳細資料**|
|:-----|:-----|:-----|:-----|
|**NextUpdateTS** <br/> |datetime  <br/> |主要  <br/> |時間戳記，內部使用。  <br/> |
|**ConferenceUriId** <br/> |int  <br/> |主要  <br/> |用於識別此會議 URI 的唯一號碼。  <br/> |
|**ConferenceUri** <br/> |Nvarchar (450)   <br/> ||會議 URI。  <br/> |
|**總和檢查碼** <br/> |int  <br/> ||ConferenceUri 的檢驗。 用於增加資料庫搜尋的速度。  <br/> |
|**UriTypeId** <br/> |int  <br/> |Foreign  <br/> |URI 類型，例如會議：適用于 IM 會議或會議：音訊/視訊會議的音訊-影片。 如需詳細資訊，請參閱 [UriTypes 表格](uritypes.md) 表格。 <br/> |
   

