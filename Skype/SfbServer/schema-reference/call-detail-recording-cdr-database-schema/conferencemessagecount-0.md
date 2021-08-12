---
title: ConferenceMessageCount view
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
ms.assetid: 8ee3ee95-fb78-4d4e-bcdd-6ce5a0a23b44
description: ConferenceMessageCount view 儲存使用者傳送給會議的郵件數目資訊。 此視圖已引進于 Microsoft Lync Server 2013。
ms.openlocfilehash: f3ec657147967a783cbe27a7a78acd6dd0fbfbb9b260d3673bcda0bdf353e5fc
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54322965"
---
# <a name="conferencemessagecount-view"></a>ConferenceMessageCount view
 
ConferenceMessageCount view 儲存使用者傳送給會議的郵件數目資訊。 此視圖已引進于 Microsoft Lync Server 2013。
  
> [!NOTE]
> ConferenceMessageCount view 包含 [ConferenceSessionDetails 視圖](conferencesessiondetails.md) 中的所有欄，此外還會包含下列欄。
  
|**欄**|**資料類型**|**詳細資料**|
|:-----|:-----|:-----|
|**UserUri** <br/> |Nvarchar (450)   <br/> |傳送郵件之使用者的 URI。  <br/> |
|**UserUriType** <br/> |Nvarchar (256)   <br/> |傳送郵件之使用者的 URI 類型。 如需詳細資訊，請參閱 [UriTypes 表格](uritypes.md) 。 <br/> |
|**UserTenant** <br/> |唯一  <br/> |傳送訊息之使用者的租使用者。 如需詳細資訊，請參閱 [承租人資料表](tenants.md) 。 <br/> |
|**UserMessageCount** <br/> |Smallint  <br/> |在會議會話期間使用者所傳送的郵件數目。  <br/> |
   

