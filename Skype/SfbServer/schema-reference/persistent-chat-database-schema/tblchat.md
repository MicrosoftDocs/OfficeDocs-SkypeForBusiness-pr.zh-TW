---
title: tblChat
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
ms.assetid: b7fcf1b4-7a3f-4585-a6d9-95e7f030c7dc
description: tblChat 包含所有聊天訊息。
ms.openlocfilehash: 2e764fa9ca64089a7015885bb4d33dc466d7dc214532e698505a19d2cf1a0d4a
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54329417"
---
# <a name="tblchat"></a>tblChat
 
tblChat 包含所有聊天訊息。
  
**Columns**

|**欄**|**類型**|**描述**|
|:-----|:-----|:-----|
|channelId  <br/> |int，非 null  <br/> |節點識別碼。  <br/> |
|chatId  <br/> |bigint，非 null  <br/> |定義聊天室順序) （由 tblLastChatId table 產生）的唯一順序編號 (每個節點識別碼。  <br/> |
|chatDate  <br/> |bigint，非 null  <br/> |聊天訊息的時間戳記。  <br/> |
|userId  <br/> |int，非 null  <br/> |海報的主體識別碼。  <br/> |
|isAlert  <br/> |位元，非 null  <br/> |True 是表示如果郵件是提醒訊息。 如果不是，則為 False。  <br/> |
|內容  <br/> |Nvarchar (max) ，非 null  <br/> |  (純文字版本) 聊天內容。 內容通常會以純文字顯示，但有下列例外： <br/>  檔案表示為 ma-filelink：連結。 <br/>  連結會呈現為 HTML 元素 (，但無法將內容類型視為 HTML) 。 <br/>  故事會編碼為 "[本文] ..."-like 格式。 <br/> |
|rtf  <br/> |Varchar (max)   <br/> | (RTF 版本) 聊天內容。 如果用戶端不提供此值，則可以為 Null。  <br/> |
   
**機碼**

|**欄**|**描述**|
|:-----|:-----|
|\<channelID, chatD\>  <br/> |主索引鍵。  <br/> |
   

