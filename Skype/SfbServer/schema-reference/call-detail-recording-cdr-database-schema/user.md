---
title: 使用者視圖
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 796f77e6-1da6-4969-b18b-3537209a1fe4
description: '[使用者] 視圖儲存已參與通話的使用者相關資訊, 或在資料庫中有記錄的會話。 此視圖已在 Microsoft Lync Server 2013 中推出。'
ms.openlocfilehash: 2fe0ba4748a776a8f17065a3c5db21d34bd6340d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36192784"
---
# <a name="user-view"></a>使用者視圖
 
[使用者] 視圖儲存已參與通話的使用者相關資訊, 或在資料庫中有記錄的會話。 此視圖已在 Microsoft Lync Server 2013 中推出。
  
|**左欄**|**資料類型**|**詳細資料**|
|:-----|:-----|:-----|
|UserId  <br/> |int  <br/> |標識此使用者的唯一號碼。  <br/> |
|UserUri  <br/> |Nvarchar (450)  <br/> |使用者的 Uri。  <br/> |
|TenantKey  <br/> |uniqueidentifier  <br/> |使用者租使用者。 如需詳細資訊, 請參閱[承租人資料表](tenants.md)。 <br/> |
|UriType  <br/> |Nvarchar (256)  <br/> |使用者 URI 的類型。 如需詳細資訊, 請參閱[UriTypes 資料表](uritypes.md)。 <br/> |
   

