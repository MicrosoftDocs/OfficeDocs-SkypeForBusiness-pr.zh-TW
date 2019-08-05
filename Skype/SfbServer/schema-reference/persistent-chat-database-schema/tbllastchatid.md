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
localization_priority: Normal
ms.assetid: 17a4ffbe-cca9-4ec5-ae46-38a15274889a
description: tblLastChatId 包含每位使用者所產生 (並在 tblChat 資料表中使用) 的最後一個聊天 ID。
ms.openlocfilehash: f14d8090fd3252d88ef747de93a987f51870a63b
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36192736"
---
# <a name="tbllastchatid"></a>tblLastChatId
 
tblLastChatId 包含每位使用者所產生 (並在 tblChat 資料表中使用) 的最後一個聊天 ID。
  
**分欄**

|**左欄**|**類型**|**說明**|
|:-----|:-----|:-----|
|個  <br/> |int, not null  <br/> |[Node ID] (聊天室-僅限類型)。  <br/> |
|lastChatID  <br/> |Bigint, not null  <br/> |上次使用的聊天 ID。  <br/> |
   
**鍵**

|**左欄**|**說明**|
|:-----|:-----|
|\<lastChatID\>  <br/> |主鍵 (只有一個代表可充分處理)。  <br/> |
|個  <br/> |在 tblNode 資料表中使用 [查閱] 的外鍵。  <br/> |
   
## <a name="see-also"></a>另請參閱

[tblChat](tblchat.md)
