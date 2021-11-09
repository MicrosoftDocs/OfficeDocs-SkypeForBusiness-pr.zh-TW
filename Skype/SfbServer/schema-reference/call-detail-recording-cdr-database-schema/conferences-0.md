---
title: 會議視圖
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: c0e5c4db-c135-401f-9296-e9a49f6499a1
description: 會議視圖會儲存會議的相關資訊。 此視圖已引進于 Microsoft Lync Server 2013。
ms.openlocfilehash: 500a03e85a3339d28227a5b65d5a3c206fc34723
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/08/2021
ms.locfileid: "60828626"
---
# <a name="conferences-view"></a>會議視圖
 
會議視圖會儲存會議的相關資訊。 此視圖已引進于 Microsoft Lync Server 2013。
  
|**欄**|**資料類型**|**詳細資料**|
|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |工作階段要求的時間。 與 SessionIdSeq 搭配使用，以唯一識別工作階段。 如需詳細資訊，請參閱[商務用 Skype Server 2015 中的對話方塊表格](dialogs.md)。 <br/> |
|**SessionIdSeq** <br/> |int  <br/> |識別工作階段的 ID 號碼。 與 SessionIdTime 搭配使用，以唯一識別工作階段。 如需詳細資訊，請參閱[商務用 Skype Server 2015 中的對話方塊表格](dialogs.md)。 <br/> |
|**ConferenceUri** <br/> |Nvarchar (450)   <br/> |會議的 URI。  <br/> |
|**ConferenceUriType** <br/> |Nvarchar (256)   <br/> |會議 URI 的類型。 如需詳細資訊，請參閱 [UriTypes 表格](uritypes.md) 。 <br/> |
|**ConfInstance** <br/> |唯一  <br/> |用於週期性會議。 每個週期性會議實例都具有相同的 ConferenceUri，但不同 ConfInstance。  <br/> |
|**ConferenceStartTime** <br/> |datetime  <br/> |會議的開始時間。  <br/> |
|**ConferenceEndTime** <br/> |datetime  <br/> |會議的結束時間。  <br/> |
|**OrganizerUri** <br/> |Nvarchar (450)   <br/> |組織會議之使用者的 URI。  <br/> |
|**OrganizerType** <br/> |Nvarchar (256)   <br/> |組織會議之使用者的 URI 類型。 如需詳細資訊，請參閱 [UriTypes 表格](uritypes.md) 。 <br/> |
|**OrganizerTenant** <br/> |Nvarchar (256)   <br/> |組織會議之使用者的租使用者。 如需詳細資訊，請參閱 [承租人資料表](tenants.md) 。 <br/> |
|**集區** <br/> |Nvarchar (256)   <br/> |主控會議之集區的完整功能變數名稱。  <br/> |
|**Flag** <br/> |Smallint  <br/> |包含會議屬性的位元遮罩。 可能的值為：  <br/> 0X01-綜合交易  <br/> |
   

