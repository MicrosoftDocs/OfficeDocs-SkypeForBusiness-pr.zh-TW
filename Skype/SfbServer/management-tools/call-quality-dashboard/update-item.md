---
title: 更新項目
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: b1c15c56-cdae-4f3e-838a-52f0940cf729
description: 摘要：瞭解更新專案作業，此作業是專案服務的一部分。 專案服務是「呼叫品質」儀表板之存放庫 API 的一部分。 通話品質儀表板是商務用 Skype Server 的工具。
ms.openlocfilehash: 4140909786c3144dbc043568a5ca6aa2995a0720
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/08/2021
ms.locfileid: "60845396"
---
# <a name="update-item"></a>更新項目
 
**摘要：** 瞭解更新專案作業，此作業是專案服務的一部分。 專案服務是「呼叫品質」儀表板之存放庫 API 的一部分。 通話品質儀表板是商務用 Skype Server 的工具。
  
更新專案作業是「用於通話品質」儀表板之存放庫 API 中專案服務的一部分。
  
## <a name="update-item"></a>更新項目

更新專案會更新存放庫中的特定專案。
  

|**方法**|**要求 URI**|**HTTP 版本**|
|:-----|:-----|:-----|
|把  <br/> |HTTPs:// \<portal\> /QoERepositoryService/repository/item/{itemId}  <br/> |HTTP/1。1  <br/> |
   
 **URI 參數** -無。
  
 **要求標頭** -Content-Type： application/json。
  
 **要求主體** -JSON。
  
範例要求負載：
  
```json
{
  content : "{ 'Product' : 'New Product Name'",
  type: "application/json"
}
```

 *內容*  要儲存成現有子專案之新內容的 JSON 格式化資料。 從技術上看，存放庫可以儲存任何架構的任何內容，但用於通話品質儀表板時，它應該是報告或查詢。 *類型*  請務必為通話品質儀表板指定 "application/json"。
  
 **回應** -回應包括 HTTP 狀態碼和一組回應標頭。
  
 **狀態碼** -成功的作業會傳回狀態碼 204 (沒有內容) 。 如果找不到指定的專案識別碼，它會傳回狀態碼 404 (找不到) 。
  
> [!IMPORTANT]
> [無內容] 不是錯誤狀態。 這表示回應並未傳回本文中的任何專案 (相比之下，200 OK 會傳回 Body) 中的內容。 這表示專案已成功更新。 
  
 **回應標頭** -無。
  
 **回應主體** -無。
  

