---
title: tblLastInviteId
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 222b3508-5963-4ddc-b4f3-e8412767e61b
description: tblLastInviteId 包含每位使用者所產生 (並在 tblPrincipalInvites 資料表中使用) 的最後一個邀請識別碼。
ms.openlocfilehash: f36b0824bb8e9dbf2cb0aa14575cc1649bde708a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36192733"
---
# <a name="tbllastinviteid"></a>tblLastInviteId
 
tblLastInviteId 包含每位使用者所產生 (並在 tblPrincipalInvites 資料表中使用) 的最後一個邀請識別碼。
  
**分欄**

|**左欄**|**類型**|**說明**|
|:-----|:-----|:-----|
|prinID  <br/> |int, not null  <br/> |Principal ID。  <br/> |
|lastInviteID  <br/> |int, not null  <br/> |上次使用邀請 ID。  <br/> |
   
**鍵**

|**左欄**|**說明**|
|:-----|:-----|
|prinID  <br/> |主鍵。  <br/> |
|prinID  <br/> |在 tblPrincipal prinID 資料表中使用 [查閱] 的外鍵。  <br/> |
   
## <a name="see-also"></a>另請參閱

[tblPrincipalInvites](tblprincipalinvites.md)
