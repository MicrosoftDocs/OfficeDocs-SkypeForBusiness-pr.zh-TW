---
title: FileTransfers 視圖
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e52c3ad0-152e-4a18-af1c-1aff0d205151
description: FileTransfer view 會儲存對等檔案傳輸會話的相關資訊。 此視圖已在 Microsoft Lync Server 2013 中推出。
ms.openlocfilehash: 303a8cf624b19f9701cabbd491fcb7b08dfba25d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36192856"
---
# <a name="filetransfers-view"></a>FileTransfers 視圖
 
FileTransfer view 會儲存對等檔案傳輸會話的相關資訊。 此視圖已在 Microsoft Lync Server 2013 中推出。
  
> [!NOTE]
> [FileTransfers] 視圖會包含 [ [SessionDetails] 視圖](sessiondetails-0.md)中的所有資料行, 以及下方所列的欄。
  
|**左欄**|**資料類型**|**詳細資料**|
|:-----|:-----|:-----|
|**副檔名** <br/> |Nvarchar (256)  <br/> |已傳輸檔案的名稱。  <br/> |
|**C** <br/> |Nvarchar  <br/> |用來識別與此郵件相關聯的每一封後續訊息。  <br/> |
|**FileIdentity** <br/> |uniqueidentifier  <br/> |唯一識別碼, 區分涉及相同檔案名的檔案傳輸。  <br/> |
|**接受** <br/> |稍微  <br/> |可以是 TRUE 或 Null。 如果為 TRUE, 則 [拒絕] 和 [取消] 將會是 Null。  <br/> |
|**否決** <br/> |稍微  <br/> |可以是 TRUE 或 Null。 如果為 TRUE, 則 [接受] 和 [取消] 將會是 Null。  <br/> |
|**取消** <br/> |稍微  <br/> |可以是 TRUE 或 Null。 如果為 TRUE, 則 [接受] 和 [拒絕] 會是 Null。  <br/> |
   

