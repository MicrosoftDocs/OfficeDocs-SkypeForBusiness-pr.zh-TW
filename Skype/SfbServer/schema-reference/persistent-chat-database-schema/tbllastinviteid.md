---
title: tblLastInviteId
ms.reviewer: ''
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
ms.assetid: 222b3508-5963-4ddc-b4f3-e8412767e61b
description: tblLastInviteId 表格含有每個使用者產生 (也用於 tblPrincipalInvites 表格) 的最後一個邀請 ID。
ms.openlocfilehash: b81f358b4e042cd11b77b3f3e34db3819b7f7a70
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/05/2022
ms.locfileid: "62393665"
---
# <a name="tbllastinviteid"></a>tblLastInviteId
 
tblLastInviteId 表格含有每個使用者產生 (也用於 tblPrincipalInvites 表格) 的最後一個邀請 ID。
  
**Columns**

|**欄**|**類型**|**描述**|
|:-----|:-----|:-----|
|Tblprincipal.prinid  <br/> |int，非 null  <br/> |主體識別碼。  <br/> |
|lastInviteID  <br/> |int，非 null  <br/> |最後一個邀請 ID。  <br/> |
   
**Keys**

|**欄**|**描述**|
|:-----|:-----|
|Tblprincipal.prinid  <br/> |主索引鍵。  <br/> |
|Tblprincipal.prinid  <br/> |在 tblPrincipal.prinID 表格中查閱外部索引鍵。  <br/> |
   
## <a name="see-also"></a>另請參閱

[tblPrincipalInvites](tblprincipalinvites.md)
