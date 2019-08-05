---
title: tblFileToken
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 49e7dd79-1607-443c-818a-88c160e4ed06
description: tblFileToken 包含臨時權杖以進行檔案傳輸。
ms.openlocfilehash: 108c9738657354881324ec720f50a51605530922
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36192737"
---
# <a name="tblfiletoken"></a>tblFileToken
 
tblFileToken 包含臨時權杖以進行檔案傳輸。
  
**分欄**

|**左欄**|**類型**|**說明**|
|:-----|:-----|:-----|
|fileToken  <br/> |Nvarchar (50), not null  <br/> |唯一標記 (GUID)。  <br/> |
|fileTokenUserID  <br/> |int, not null  <br/> |要轉移檔案之主體的 ID。  <br/> |
|fileTokenChannelID  <br/> |GUID, 不是 null  <br/> |聊天室節點的 GUID。  <br/> |
|fileTokenExpireDate  <br/> |datetime、not null  <br/> |到期時間。 (權杖會在30分鐘之後到期, 除非已固定 (請參閱此欄中的下列描述)。  <br/> |
|fileTokenComplianceFileUrl  <br/> |Nvarchar (256)  <br/> |已傳送檔案的 URL (適用于合規性服務使用)。  <br/> |
|fileTokenComplianceThumbnailUrl  <br/> |Nvarchar (256)  <br/> |已傳送檔案的縮圖 URL (適用于合規性服務使用)。  <br/> |
|fileTokenComplianceTime  <br/> |datetime2  <br/> |實際檔案傳輸作業 (適用于合規性服務使用) 的時間戳記。  <br/> |
|fileTokenComplianceIsUpload  <br/> |稍微  <br/> |如果上傳則為 True;如果下載 (適用于相容性服務使用), 則為 False。  <br/> |
|fileTokenCompliancePinned  <br/> |bit、not null  <br/> |如果權杖已釘選, 則為 True。 它是用來在表格中保留權杖, 直到合規性服務有機會從它取得相關欄位為止。  <br/> |
   
**鍵**

|**左欄**|**說明**|
|:-----|:-----|
|fileToken  <br/> |主鍵。  <br/> |
|fileTokenChannelID  <br/> |在 tblNode nodeGuid 資料表中使用 [查閱] 的外鍵。  <br/> |
   

