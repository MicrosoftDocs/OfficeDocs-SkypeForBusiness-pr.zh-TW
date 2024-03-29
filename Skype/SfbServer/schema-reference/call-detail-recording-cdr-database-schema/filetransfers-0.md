---
title: 商務用 Skype Server 2015 中的 FileTransfers 表格
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 7/15/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 5368e67c-d8a9-43a1-9472-a839950dedb3
description: 每筆記錄代表一個檔案傳輸工作階段。
ms.openlocfilehash: 85e284e48d6f8610fee9be71c91c368f2dab6988
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/05/2022
ms.locfileid: "62404575"
---
# <a name="filetransfers-table-in-skype-for-business-server-2015"></a>商務用 Skype Server 2015 中的 FileTransfers 表格
 
每筆記錄代表一個檔案傳輸工作階段。
  
|**欄**|**資料類型**|**索引鍵/索引**|**詳細資料**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |主要，外部  <br/> |工作階段要求的時間。 其會與 **SessionIdSeq** 搭配使用，專門用於識別工作階段。 如需詳細資訊，請參閱[商務用 Skype Server 2015 中的對話方塊表格](dialogs.md)。 <br/> |
|**SessionIdSeq** <br/> |int  <br/> |主要，外部  <br/> |用來識別工作階段的識別碼。 會與 **SessionIdTime** 搭配使用，專門用於識別工作階段。 如需詳細資訊，請參閱[商務用 Skype Server 2015 中的對話方塊表格](dialogs.md)。 <br/> |
|**檔案名稱** <br/> |Nvarchar (256)   <br/> ||檔案的名稱。  <br/> |
|**FileIdentity** <br/> |唯一  <br/> ||唯一識別碼，用於分辨包含相同檔名的檔案傳輸。  <br/> |
|**Cookie** <br/> |Nvarchar (128)   <br/> |主要  <br/> |可用來識別與此訊息相關聯的每則後續訊息。  <br/> |
|**Accept** <br/> |位  <br/> ||可為 TRUE 或 NULL。若為 TRUE，則「拒絕」和「取消」為 NULL。  <br/> |
|**Reject** <br/> |位  <br/> ||可為 TRUE 或 NULL。若為 TRUE，則「接受」和「取消」為 NULL。  <br/> |
|**Cancel** <br/> |位  <br/> ||可為 TRUE 或 NULL。若為 TRUE，則「接受」和「拒絕」為 NULL。  <br/> |
|**LastModifiedTime** <br/> |Datetime  <br/> ||供監控服務內部使用。  <br/> 此欄位是在商務用 Skype Server 2015 中引入。  <br/> |
   

