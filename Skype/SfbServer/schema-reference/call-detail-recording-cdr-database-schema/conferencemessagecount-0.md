---
title: ConferenceMessageCount 視圖
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
ms.assetid: 8ee3ee95-fb78-4d4e-bcdd-6ce5a0a23b44
description: '[ConferenceMessageCount] 視圖儲存使用者傳送給會議的郵件數目的相關資訊。 此視圖已在 Microsoft Lync Server 2013 中推出。'
ms.openlocfilehash: a766e63fbca5c30cec3c3891c9ccfc2355f16d2d
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815381"
---
# <a name="conferencemessagecount-view"></a>ConferenceMessageCount 視圖
 
[ConferenceMessageCount] 視圖儲存使用者傳送給會議的郵件數目的相關資訊。 此視圖已在 Microsoft Lync Server 2013 中推出。
  
> [!NOTE]
> [ConferenceMessageCount] 視圖會包含 [ [ConferenceSessionDetails] 視圖](conferencesessiondetails.md)中的所有資料行，以及下方所列的欄。
  
|**左欄**|**資料類型**|**詳細資料**|
|:-----|:-----|:-----|
|**UserUri** <br/> |Nvarchar （450）  <br/> |傳送郵件之使用者的 URI。  <br/> |
|**UserUriType** <br/> |Nvarchar （256）  <br/> |傳送郵件之使用者的 URI 類型。 如需詳細資訊，請參閱[UriTypes 資料表](uritypes.md)。 <br/> |
|**UserTenant** <br/> |uniqueidentifier  <br/> |傳送訊息的使用者租使用者。 如需詳細資訊，請參閱[承租人資料表](tenants.md)。 <br/> |
|**UserMessageCount** <br/> |Smallint  <br/> |使用者在會議會話期間傳送的訊息數目。  <br/> |
   

