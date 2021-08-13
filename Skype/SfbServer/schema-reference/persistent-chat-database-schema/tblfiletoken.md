---
title: tblFileToken
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
ms.assetid: 49e7dd79-1607-443c-818a-88c160e4ed06
description: tblFileToken 包含用於檔案傳輸的臨時權杖。
ms.openlocfilehash: f099b641f732d2f6ccecf699335e9e88736484cc4eac7bfbce8d4a2d7dd6e810
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54301289"
---
# <a name="tblfiletoken"></a>tblFileToken
 
tblFileToken 包含用於檔案傳輸的臨時權杖。
  
**Columns**

|**欄**|**類型**|**描述**|
|:-----|:-----|:-----|
|fileToken  <br/> |nvarchar (50)，非 null  <br/> |唯一 Token (GUID)。  <br/> |
|fileTokenUserID  <br/> |int，非 null  <br/> |傳輸檔案之主體的識別碼。  <br/> |
|fileTokenChannelID  <br/> |GUID，非 null  <br/> |聊天室節點的 GUID。  <br/> |
|fileTokenExpireDate  <br/> |datetime，非 null  <br/> |到期時間 (權杖於 30 分鐘後到期，除非已固定 (請參閱此欄中下列說明)。  <br/> |
|fileTokenComplianceFileUrl  <br/> |Nvarchar (256)   <br/> |已傳輸檔案的 URL (供 Compliance Service 使用)。  <br/> |
|fileTokenComplianceThumbnailUrl  <br/> |Nvarchar (256)   <br/> |已傳輸檔案的縮圖 URL (供 Compliance Service 使用)。  <br/> |
|fileTokenComplianceTime  <br/> |datetime2  <br/> |實際檔案傳輸作業的時間戳記 (供 Compliance Service 使用)。  <br/> |
|fileTokenComplianceIsUpload  <br/> |位  <br/> |若上傳則為 True；若下載則為 False (供 Compliance Service 使用)。  <br/> |
|fileTokenCompliancePinned  <br/> |位元，非 null  <br/> |True 是表示如果鎖定標記。 它是用來保留表格中的標記，直到合規性服務有機會從該介面中取回相關的欄位。  <br/> |
   
**Keys**

|**欄**|**描述**|
|:-----|:-----|
|fileToken  <br/> |主索引鍵。  <br/> |
|fileTokenChannelID  <br/> |在 Node.nodeGuid 表格中查閱外部索引鍵。  <br/> |
   

