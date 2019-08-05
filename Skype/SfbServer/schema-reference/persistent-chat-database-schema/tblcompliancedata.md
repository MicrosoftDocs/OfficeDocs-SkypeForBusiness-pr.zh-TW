---
title: tblComplianceData
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 05b28f9b-4aba-4b69-ba8d-2ceeb6cbfaac
description: tblComplianceData 包含尚未由合規性配接器處理的合規性事件。
ms.openlocfilehash: b505b3e05fb2aebba98804f5b7ad6a1d4d2da53e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36192753"
---
# <a name="tblcompliancedata"></a>tblComplianceData
 
tblComplianceData 包含尚未由合規性配接器處理的合規性事件。
  
**分欄**

|**左欄**|**類型**|**說明**|
|:-----|:-----|:-----|
|cmplEventID  <br/> |Bigint, not null  <br/> |事件 ID。  <br/> |
|entryDate  <br/> |Smalldatetime, not null  <br/> |插入的時間 (對於 cmplType = 9, 未來可能是目前的時間), 因為該專案只是該案例中的預留位置。  <br/> |
|cmplType  <br/> |int, not null  <br/> | 合規性事件的類型: <br/>  1: 聊天 <br/>  2: Backchat <br/>  3: 檔案下載 <br/>  4: 檔案上傳 <br/>  9: 暫存檔案傳輸 <br/>  10: 聊天刪除 (使用 [取代]) <br/>  11: 聊天清除 <br/> |
|cmplTime  <br/> |Bigint, not null  <br/> |事件的時間戳記。  <br/> |
|cmplChannelUri  <br/> |Nvarchar (255), not null  <br/> |通道統一資源識別項 (URI)。  <br/> |
|cmplChatID  <br/> |Bigint  <br/> |聊天識別碼 (對應至 tblChat chatId 表)。  <br/> |
|cmplUserID  <br/> |int, not null  <br/> |海報的主體識別碼 (對應至 tblPrincipal prinID)。  <br/> |
|cmplUserUri  <br/> |Nvarchar (255), not null  <br/> |使用者 URI。  <br/> |
|cmplMessage  <br/> |Nvarchar (max)  <br/> |訊息 (編碼依據 cmplType)。  <br/> |
   
**快速鍵**

|**左欄**|**說明**|
|:-----|:-----|
|cmplEventID  <br/> |主鍵。  <br/> |
   

