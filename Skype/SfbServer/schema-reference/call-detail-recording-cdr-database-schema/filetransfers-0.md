---
title: 商務用 Skype Server 2015 中的 FileTransfers 表格
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/15/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 5368e67c-d8a9-43a1-9472-a839950dedb3
description: 每個記錄代表一個檔案傳輸會話。
ms.openlocfilehash: 8b287d2fc2c40fe7e20cb3abc4ed6e403da701b7
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815211"
---
# <a name="filetransfers-table-in-skype-for-business-server-2015"></a>商務用 Skype Server 2015 中的 FileTransfers 表格
 
每個記錄代表一個檔案傳輸會話。
  
|**左欄**|**資料類型**|**索引鍵/索引**|**詳細資料**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |主要、外部  <br/> |會話要求的時間。 與**SessionIdSeq**搭配使用，可唯一識別會話。 如需詳細資訊，請參閱[商務用 Skype Server 2015 中](dialogs.md)的 [對話方塊] 表格。 <br/> |
|**SessionIdSeq** <br/> |int  <br/> |主要、外部  <br/> |識別會話的識別碼編號。 與**SessionIdTime**搭配使用，可唯一識別會話。 如需詳細資訊，請參閱[商務用 Skype Server 2015 中](dialogs.md)的 [對話方塊] 表格。 <br/> |
|**檔案名** <br/> |Nvarchar （256）  <br/> ||檔案的名稱。  <br/> |
|**FileIdentity** <br/> |uniqueidentifier  <br/> ||唯一識別碼，區分涉及相同檔案名的檔案傳輸。  <br/> |
|**C** <br/> |Nvarchar  <br/> |首選  <br/> |用來識別與此郵件相關聯的每一封後續訊息。  <br/> |
|**接受** <br/> |稍微  <br/> ||可以是 TRUE 或 Null。 如果為 TRUE，則 [拒絕] 和 [取消] 將會是 Null。  <br/> |
|**否決** <br/> |稍微  <br/> ||可以是 TRUE 或 Null。 如果為 TRUE，則 [接受] 和 [取消] 將會是 Null。  <br/> |
|**取消** <br/> |稍微  <br/> ||可以是 TRUE 或 Null。 如果為 TRUE，則 [接受] 和 [拒絕] 會是 Null。  <br/> |
|**LastModifiedTime** <br/> |Datetime  <br/> ||供監視服務內部使用。  <br/> 此欄位是在商務用 Skype Server 2015 中推出。  <br/> |
   

