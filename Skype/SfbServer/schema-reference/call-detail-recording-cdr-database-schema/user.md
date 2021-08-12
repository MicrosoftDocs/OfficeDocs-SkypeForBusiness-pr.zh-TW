---
title: 使用者視圖
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
ms.assetid: 796f77e6-1da6-4969-b18b-3537209a1fe4
description: 使用者檢視會儲存在資料庫中有記錄之通話或工作階段中所涉及的使用者相關資訊。 此視圖已引進于 Microsoft Lync Server 2013。
ms.openlocfilehash: 200280f6a82a50490aee77177464b435e647a0a44852ca0db5b59c64bda836f3
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54302247"
---
# <a name="user-view"></a>使用者視圖
 
使用者檢視會儲存在資料庫中有記錄之通話或工作階段中所涉及的使用者相關資訊。 此視圖已引進于 Microsoft Lync Server 2013。
  
|**欄**|**資料類型**|**詳細資料**|
|:-----|:-----|:-----|
|UserId  <br/> |int  <br/> |用於識別此使用者的唯一號碼。  <br/> |
|UserUri  <br/> |Nvarchar (450)   <br/> |使用者的 URI。  <br/> |
|TenantKey  <br/> |唯一  <br/> |使用者的租用戶。 如需詳細資訊，請參閱 [承租人資料表](tenants.md) 。 <br/> |
|UriType  <br/> |Nvarchar (256)   <br/> |使用者 URI 的類型。 如需詳細資訊，請參閱 [UriTypes 表格](uritypes.md) 。 <br/> |
   

