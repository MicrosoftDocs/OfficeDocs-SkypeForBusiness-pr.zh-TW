---
title: 通話品質儀表板 (CQD) 的專案服務
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b6d7b02a-a34e-4fef-986c-ca442e18fa0c
description: 摘要：瞭解專案服務，這是適用于通話品質儀表板的存放庫 API 的一部分。 通話品質儀表板是商務用 Skype 伺服器的工具。
ms.openlocfilehash: b904f814a837af13e4015af5fbaca924739b8997
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49827703"
---
# <a name="item-service-for-call-quality-dashboard-cqd"></a>通話品質儀表板 (CQD) 的專案服務
 
**摘要：** 瞭解專案服務，這是適用于通話品質儀表板的存放庫 API 的一部分。 通話品質儀表板是商務用 Skype 伺服器的工具。
  
專案服務是「呼叫品質」儀表板之存放庫 API 的一部分。
  
## <a name="item-service"></a>項目服務

存放庫 API 提供簡單的內容管理服務（稱為「專案服務」），可用來儲存使用者的任何應用程式定義內容。 
  
系統內容是由系統使用者所擁有，且由具有唯讀許可權的所有使用者共用。 「專用使用者」內容是由一般使用者所擁有，而且只有擁有者可以修改或刪除它們，但所有使用者仍具有對這些使用者的唯讀許可權。
  
> [!NOTE]
> 此 API 檔涵蓋存放庫 API 的唯讀作業。 
  
通話品質儀表板會將報告和查詢儲存為存放庫資料庫中的專案。 專案可以具有選擇性子專案，而通話品質儀表板會使用子專案功能，以階層結構組織報表和查詢。
  
專案服務包含下列概念：
  
- **Item** -存放庫的基本元素。 每個專案都只歸一個使用者所有。
    
- **子專案** -存放庫的基本組織結構。 專案可以有零個、一或多個從屬專案。
    
- **專案上級** -從最頂端專案開始的清單，該專案是使用者的預設專案，會前置至指定的專案。
    
- **專案內容** -儲存在專案中的應用程式特定內容。 通話品質儀表板會儲存報告和查詢內容中的 JSON 標記法。
    
其餘的作業包含在下表中。
  

|**作業**|**描述**|
|:-----|:-----|
|[取得項目](get-items.md) <br/> |取得專案會傳回存放庫中的所有專案。  <br/> |
|[取得項目](get-item.md) <br/> |取得專案會傳回特定專案。  <br/> |
|[取得子項目](get-sub-items.md) <br/> |Get Sub-Items 會傳回特定專案的子專案。  <br/> |
|[取得項目上階](get-item-ancestors.md) <br/> |取得專案祖先會傳回特定專案的祖先。  <br/> |
|[更新項目](update-item.md) <br/> |更新存放庫中的特定專案。  <br/> |
   

