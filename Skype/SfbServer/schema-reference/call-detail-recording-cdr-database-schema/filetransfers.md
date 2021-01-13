---
title: FileTransfers view
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
ms.assetid: e52c3ad0-152e-4a18-af1c-1aff0d205151
description: FileTransfer view 會儲存對等檔案傳輸會話的資訊。 此視圖已引進于 Microsoft Lync Server 2013。
ms.openlocfilehash: 8b3c2db012b8969bd4b5b75ca19ed090f8227c53
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821683"
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
   

