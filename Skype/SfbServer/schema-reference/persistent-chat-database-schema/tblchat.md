---
title: tblChat
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
ms.assetid: b7fcf1b4-7a3f-4585-a6d9-95e7f030c7dc
description: tblChat 包含所有聊天訊息。
ms.openlocfilehash: 7221136c435c1d4af836174ddfde5cbd02f4c5f6
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814671"
---
# <a name="tblchat"></a>tblChat
 
tblChat 包含所有聊天訊息。
  
**分欄**

|**左欄**|**類型**|**說明**|
|:-----|:-----|:-----|
|channelId  <br/> |int，not null  <br/> |節點識別碼。  <br/> |
|chatId  <br/> |Bigint，not null  <br/> |定義 tblLastChatId 表格產生的聊天室順序的唯一順序編號（每個節點識別碼）。  <br/> |
|chatDate  <br/> |Bigint，not null  <br/> |聊天訊息的時間戳記。  <br/> |
|userId  <br/> |int，not null  <br/> |海報的主體識別碼。  <br/> |
|isAlert  <br/> |bit、not null  <br/> |如果訊息是提醒訊息，則為 True。 如果不是，則為 False。  <br/> |
|內容  <br/> |Nvarchar （max），not null  <br/> | 聊天內容（純文字版本）。 內容通常是純文字，但有下列例外狀況： <br/>  檔案表示為 ma-filelink：連結。 <br/>  連結是以 HTML 元素表示（雖然無法將內容類型視為 HTML）。 <br/>  案例的編碼方式是「[情景] ...」格式。 <br/> |
|rtf  <br/> |Varchar （max）  <br/> |聊天內容（RTF 版本）。 如果用戶端無法提供，可能會是 Null。  <br/> |
   
**機碼**

|**左欄**|**說明**|
|:-----|:-----|
|\<channelID, chatD\>  <br/> |主鍵。  <br/> |
   

