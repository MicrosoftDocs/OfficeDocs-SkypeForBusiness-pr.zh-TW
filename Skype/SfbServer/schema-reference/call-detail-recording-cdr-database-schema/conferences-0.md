---
title: 會議視圖
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
ms.assetid: c0e5c4db-c135-401f-9296-e9a49f6499a1
description: '[會議] 視圖會儲存會議的相關資訊。 此視圖已在 Microsoft Lync Server 2013 中推出。'
ms.openlocfilehash: 9f9448769256bfb05e6552a41c2521defa65ded0
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815361"
---
# <a name="conferences-view"></a>會議視圖
 
[會議] 視圖會儲存會議的相關資訊。 此視圖已在 Microsoft Lync Server 2013 中推出。
  
|**左欄**|**資料類型**|**詳細資料**|
|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |會話要求的時間。 與 SessionIdSeq 搭配使用，可唯一識別會話。 如需詳細資訊，請參閱[商務用 Skype Server 2015 中](dialogs.md)的 [對話方塊] 表格。 <br/> |
|**SessionIdSeq** <br/> |int  <br/> |識別會話的識別碼編號。 與 SessionIdTime 搭配使用，可唯一識別會話。 如需詳細資訊，請參閱[商務用 Skype Server 2015 中](dialogs.md)的 [對話方塊] 表格。 <br/> |
|**ConferenceUri** <br/> |Nvarchar （450）  <br/> |會議的 URI。  <br/> |
|**ConferenceUriType** <br/> |Nvarchar （256）  <br/> |會議 URI 的類型。 如需詳細資訊，請參閱[UriTypes 資料表](uritypes.md)。 <br/> |
|**ConfInstance** <br/> |uniqueidentifier  <br/> |用於週期性會議。 每個週期性會議實例都有相同的 ConferenceUri，但 ConfInstance 不同。  <br/> |
|**ConferenceStartTime** <br/> |datetime  <br/> |會議的開始時間。  <br/> |
|**ConferenceEndTime** <br/> |datetime  <br/> |會議的結束時間。  <br/> |
|**OrganizerUri** <br/> |Nvarchar （450）  <br/> |組織會議的使用者 URI。  <br/> |
|**OrganizerType** <br/> |Nvarchar （256）  <br/> |組織會議的使用者 URI 類型。 如需詳細資訊，請參閱[UriTypes 資料表](uritypes.md)。 <br/> |
|**OrganizerTenant** <br/> |Nvarchar （256）  <br/> |組織會議的使用者租使用者。 如需詳細資訊，請參閱[承租人資料表](tenants.md)。 <br/> |
|**集區** <br/> |Nvarchar （256）  <br/> |主持會議之池的完整功能變數名稱。  <br/> |
|**標識** <br/> |Smallint  <br/> |包含會議屬性的位元遮罩。 可能的值包括：  <br/> 0X01-綜合交易  <br/> |
   

