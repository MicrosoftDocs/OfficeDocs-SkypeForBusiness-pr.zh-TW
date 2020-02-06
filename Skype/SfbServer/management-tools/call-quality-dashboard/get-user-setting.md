---
title: 取得使用者設定
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 16611a55-79fb-487a-a936-20caca829f87
description: 摘要：瞭解 [取得使用者設定] 作業，該操作是 [使用者設定] 服務的一部分。 [使用者設定] 服務是 [通話品質] 儀表板的 [知識庫 API] 的一部分。 [通話品質儀表板] 是商務用 Skype Server 的工具。
ms.openlocfilehash: 4ab9d4d718a2ff411db72f38b59a758523935504
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816752"
---
# <a name="get-user-setting"></a>取得使用者設定
 
**摘要：** 瞭解 [取得使用者設定] 作業，該操作是 [使用者設定] 服務的一部分。 [使用者設定] 服務是 [通話品質] 儀表板的 [知識庫 API] 的一部分。 [通話品質儀表板] 是商務用 Skype Server 的工具。
  
[取得使用者設定] 作業是 [呼叫品質] 儀表板的 [知識庫 API] 中的 [使用者設定] 服務的一部分。
  
## <a name="get-user-setting"></a>取得使用者設定

[取得使用者] 設定會傳回單一使用者設定。
  

|**法**|**要求 URI**|**HTTP 版本**|
|:-----|:-----|:-----|
|獲取  <br/> |HTTPs://\<入口\>網站/QoERepositoryService/repository/user/{userId}/setting/{key}  <br/> |HTTP/1。1  <br/> |
   
 **URI 參數**-無。
  
 **要求標頭**-沒有其他標頭。
  
 **要求主體**-無。
  
 **回應**-回應包括 HTTP 狀態碼和一組回應標頭。
  
 **狀態碼**-成功的操作會傳回狀態碼200（確定）。
  
 **回應標題**-沒有其他標頭。
  
 **回應主體**-以下是 JSON 中的回應載荷範例。
  
```json
{
"userId": 6,
"key": "ShowDescriptions",
"value": "true"
}
```

 *userId* -使用者識別碼。
  
 設定的*索引鍵。*
  
 設定的*value* （值）。
  

