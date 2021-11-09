---
title: FileTransfers view
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: e52c3ad0-152e-4a18-af1c-1aff0d205151
description: FileTransfer view 會儲存對等檔案傳輸會話的資訊。 此視圖已引進于 Microsoft Lync Server 2013。
ms.openlocfilehash: eae94d0220cb3443e90665d420b888e86a37d11a
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/08/2021
ms.locfileid: "60850636"
---
# <a name="filetransfers-view"></a>FileTransfers view
 
FileTransfer view 會儲存對等檔案傳輸會話的資訊。 此視圖已引進于 Microsoft Lync Server 2013。
  
> [!NOTE]
> FileTransfers view 包含 [SessionDetails 視圖](sessiondetails-0.md) 中的所有欄，此外還會包含下列欄。
  
|**欄**|**資料類型**|**詳細資料**|
|:-----|:-----|:-----|
|**FileName** <br/> |Nvarchar (256)   <br/> |已傳輸的檔案名稱。  <br/> |
|**Cookie** <br/> |Nvarchar (128)   <br/> |可用來識別與此訊息相關聯的每則後續訊息。  <br/> |
|**FileIdentity** <br/> |唯一  <br/> |唯一識別碼，用於分辨包含相同檔名的檔案傳輸。  <br/> |
|**Accept** <br/> |位  <br/> |可為 TRUE 或 NULL。若為 TRUE，則「拒絕」和「取消」為 NULL。  <br/> |
|**Reject** <br/> |位  <br/> |可為 TRUE 或 NULL。若為 TRUE，則「接受」和「取消」為 NULL。  <br/> |
|**Cancel** <br/> |位  <br/> |可為 TRUE 或 NULL。若為 TRUE，則「接受」和「拒絕」為 NULL。  <br/> |
   

