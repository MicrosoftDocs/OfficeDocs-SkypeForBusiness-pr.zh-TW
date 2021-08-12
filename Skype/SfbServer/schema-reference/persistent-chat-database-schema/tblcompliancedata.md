---
title: tblComplianceData
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
ms.assetid: 05b28f9b-4aba-4b69-ba8d-2ceeb6cbfaac
description: tblComplianceData 包含法規相符性介面卡尚未處理的規範事件。
ms.openlocfilehash: 70929cd85499fb015489054d11e11d492fe00e145e7da32dbf7477deb5e7c60d
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54284463"
---
# <a name="tblcompliancedata"></a>tblComplianceData
 
tblComplianceData 包含法規相符性介面卡尚未處理的規範事件。
  
**Columns**

|**欄**|**類型**|**描述**|
|:-----|:-----|:-----|
|cmplEventID  <br/> |bigint，非 null  <br/> |事件識別碼。  <br/> |
|entryDate  <br/> |smalldatetime，非 null  <br/> |插入時間 (若是 cmplType=9，則可能是未來很久以後，因為此項目在此情況下只是預留位置)。  <br/> |
|cmplType  <br/> |int，非 null  <br/> | 規範事件的類型： <br/>  1: 聊天 <br/>  2: 對話 <br/>  3: 檔案下載 <br/>  4: 檔案上傳 <br/>  9: 暫時性檔案傳輸 <br/>  10: 聊天刪除 (及取代) <br/>  11: 聊天清除 <br/> |
|cmplTime  <br/> |bigint，非 null  <br/> |事件的時間戳記。  <br/> |
|cmplChannelUri  <br/> |nvarchar (255)，非 null  <br/> |通道統一資源識別項 (URI)。  <br/> |
|cmplChatID  <br/> |Bigint  <br/> |聊天識別碼 (對應至 tblChat.chatId 表格)。  <br/> |
|cmplUserID  <br/> |int，非 null  <br/> |發佈者的主體識別碼 (對應至 tblPrincipal.prinID 表格)。  <br/> |
|cmplUserUri  <br/> |nvarchar (255)，非 null  <br/> |使用者 URI。  <br/> |
|cmplMessage  <br/> |nvarchar (max)  <br/> |訊息 (編碼取決於 cmplType)。  <br/> |
   
**機碼**

|**欄**|**描述**|
|:-----|:-----|
|cmplEventID  <br/> |主索引鍵。  <br/> |
   

