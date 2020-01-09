---
title: 更新項目
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b1c15c56-cdae-4f3e-838a-52f0940cf729
description: 摘要：瞭解 [更新專案] 作業，該作業是專案服務的一部分。 專案服務是 [通話品質] 儀表板的 [知識庫 API] 的一部分。 [通話品質儀表板] 是商務用 Skype Server 的工具。
ms.openlocfilehash: 55d21d1e1b8f3814dab7699ff864ba8fea1d23be
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991388"
---
# <a name="update-item"></a>更新項目
 
**摘要：** 瞭解 [更新專案] 作業，該作業是專案服務的一部分。 專案服務是 [通話品質] 儀表板的 [知識庫 API] 的一部分。 [通話品質儀表板] 是商務用 Skype Server 的工具。
  
[更新專案] 作業是 [通話品質] 儀表板的 [知識庫 API] 中的專案服務的一部分。
  
## <a name="update-item"></a>更新項目

更新專案會更新儲存庫中的特定專案。
  

|**法**|**要求 URI**|**HTTP 版本**|
|:-----|:-----|:-----|
|將  <br/> |HTTPs://\<入口\>網站/QoERepositoryService/repository/item/{itemId}  <br/> |HTTP/1。1  <br/> |
   
 **URI 參數**-無。
  
 **要求標頭**-內容類型： application/json。
  
 **要求主體**-JSON。
  
範例要求負載：
  
```json
{
  content : "{ 'Product' : 'New Product Name'",
  type: "application/json"
}
```

 *內容* 要儲存為現有子專案的新內容的 JSON 格式資料。 從技術角度來看，知識庫可以儲存任何架構的內容，但在通話品質儀表板中使用時，必須是報表或查詢。 *類型* 針對 [通話品質] 儀表板，請務必指定 "application/json"。
  
 **回應**-回應包括 HTTP 狀態碼和一組回應標頭。
  
 **狀態碼**-成功的操作會傳回狀態碼204（無內容）。 如果找不到指定的專案識別碼，則會傳回狀態碼404（找不到）。
  
> [!IMPORTANT]
> "無內容" 不是錯誤狀態。 這表示回應並未傳回本文中的任何內容（相反，200 OK 會傳回本文中的內容）。 它表示專案已成功更新。 
  
 **回應標題**-無。
  
 **回應主體**-無。
  

