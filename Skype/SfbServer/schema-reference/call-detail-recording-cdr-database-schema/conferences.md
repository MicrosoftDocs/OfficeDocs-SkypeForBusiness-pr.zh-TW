---
title: 商務用 Skype Server 2015 中的 [會議] 表格
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/15/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c3da6271-b3c6-4898-894f-10456ec794d0
description: 此表格中的每筆記錄都包含一個會議的通話詳細資料。
ms.openlocfilehash: 41a2a25e80b073b568152422defeee1ca3e2ac19
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36192885"
---
# <a name="conferences-table-in-skype-for-business-server-2015"></a>商務用 Skype Server 2015 中的 [會議] 表格
 
此表格中的每筆記錄都包含一個會議的通話詳細資料。
  
|**左欄**|**資料類型**|**索引鍵/索引**|**詳細資料**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |首選  <br/> |由 CDR 代理程式捕獲會議要求的時間。 僅用作主鍵來唯一識別會議實例。  <br/> |
|**SessionIdSeq** <br/> |int  <br/> |首選  <br/> |識別會話的識別碼編號。 與**SessionIdTime**搭配使用, 可唯一識別會議實例。 * <br/> |
|**ConferenceUriId** <br/> |int  <br/> |外  <br/> |會議 URI。 如需詳細資訊, 請參閱[商務用 Skype Server 2015 中](conferenceuris.md)的 [ConferenceUris] 資料表。 <br/> |
|**ConfInstance** <br/> |uniqueidentifier  <br/> | <br/> |適用于週期性會議;每個週期性會議實例都有相同的**ConferenceUri**, 但會有不同的**ConfInstance**。 <br/> |
|**ConferenceStartTime** <br/> |datetime  <br/> | <br/> |會議開始時間。  <br/> |
|**ConferenceEndTime** <br/> |datetime  <br/> | <br/> |會議開始時間。  <br/> |
|**PoolId** <br/> |int  <br/> |外  <br/> |[識別碼] 編號, 可識別捕獲會議的池。 如需詳細資訊, 請參閱 [[彙集] 資料表](pools.md)。 <br/> |
|**OrganizerId** <br/> |Int  <br/> |外  <br/> |識別此會議之召集人 URI 的識別碼編號。 如需詳細資訊, 請參閱 [[使用者] 表格](users.md)。 <br/> |
|**標識** <br/> |Smallint  <br/> || 包含會議屬性的位元遮罩。 可能的值包括: <br/>  0X01 <br/>  合成 <br/>  事物 <br/> |
|**預處理** <br/> |稍微  <br/> ||[監視服務] 使用的內部欄位。  <br/> 此欄位是在 Microsoft Lync Server 2013 中推出。  <br/> |
|**LastModifiedTime** <br/> |Datetime  <br/> ||供監視服務內部使用。  <br/> 此欄位是在商務用 Skype Server 2015 中推出。  <br/> |
   
\*在大部分的會話中, SessionIdSeq 將會有1的值。 如果兩個會話是完全相同的時間, 則其中一個會話的 SessionIdSeq 會是 1, 而另一個則是 2, 依此類推。
  

