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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: e52c3ad0-152e-4a18-af1c-1aff0d205151
description: FileTransfer view 會儲存對等檔案傳輸會話的相關資訊。 此視圖已在 Microsoft Lync Server 2013 中推出。
ms.openlocfilehash: d650c04b8dada5828eed5d7bc3039cb77570ce2b
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815201"
---
# <a name="filetransfers-view"></a>FileTransfers 視圖
 
FileTransfer view 會儲存對等檔案傳輸會話的相關資訊。 此視圖已在 Microsoft Lync Server 2013 中推出。
  
> [!NOTE]
> [FileTransfers] 視圖會包含 [ [SessionDetails] 視圖](sessiondetails-0.md)中的所有資料行，以及下方所列的欄。
  
|**左欄**|**資料類型**|**詳細資料**|
|:-----|:-----|:-----|
|**副檔名** <br/> |Nvarchar （256）  <br/> |已傳輸檔案的名稱。  <br/> |
|**C** <br/> |Nvarchar  <br/> |用來識別與此郵件相關聯的每一封後續訊息。  <br/> |
|**FileIdentity** <br/> |uniqueidentifier  <br/> |唯一識別碼，區分涉及相同檔案名的檔案傳輸。  <br/> |
|**接受** <br/> |稍微  <br/> |可以是 TRUE 或 Null。 如果為 TRUE，則 [拒絕] 和 [取消] 將會是 Null。  <br/> |
|**否決** <br/> |稍微  <br/> |可以是 TRUE 或 Null。 如果為 TRUE，則 [接受] 和 [取消] 將會是 Null。  <br/> |
|**取消** <br/> |稍微  <br/> |可以是 TRUE 或 Null。 如果為 TRUE，則 [接受] 和 [拒絕] 會是 Null。  <br/> |
   

