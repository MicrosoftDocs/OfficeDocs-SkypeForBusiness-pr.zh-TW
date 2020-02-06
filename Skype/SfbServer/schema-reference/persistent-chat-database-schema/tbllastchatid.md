---
title: tblLastChatId
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
ms.assetid: 17a4ffbe-cca9-4ec5-ae46-38a15274889a
description: tblLastChatId 包含每位使用者所產生（並在 tblChat 資料表中使用）的最後一個聊天 ID。
ms.openlocfilehash: 95498f077948e1b400d0a370762c121def703e8c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814581"
---
# <a name="tbllastchatid"></a>tblLastChatId
 
tblLastChatId 包含每位使用者所產生（並在 tblChat 資料表中使用）的最後一個聊天 ID。
  
**分欄**

|**左欄**|**類型**|**說明**|
|:-----|:-----|:-----|
|個  <br/> |int，not null  <br/> |[Node ID] （聊天室-僅限類型）。  <br/> |
|lastChatID  <br/> |Bigint，not null  <br/> |上次使用的聊天 ID。  <br/> |
   
**鍵**

|**左欄**|**說明**|
|:-----|:-----|
|\<lastChatID\>  <br/> |主鍵（只有一個代表可充分處理）。  <br/> |
|個  <br/> |在 tblNode 資料表中使用 [查閱] 的外鍵。  <br/> |
   
## <a name="see-also"></a>另請參閱

[tblChat](tblchat.md)
