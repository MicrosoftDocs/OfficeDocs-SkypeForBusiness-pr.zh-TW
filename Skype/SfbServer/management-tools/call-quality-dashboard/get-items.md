---
title: 取得項目
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
ms.assetid: 9e189a48-4944-4f93-88d7-9d56b56770a6
description: 摘要：瞭解 [取得專案] 作業，這是專案服務的一部分。 專案服務是「呼叫品質」儀表板之存放庫 API 的一部分。 通話品質儀表板是商務用 Skype 伺服器的工具。
ms.openlocfilehash: 7da3ba77e782abe44896a7c1eb51a458d9a7e0b8
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832533"
---
# <a name="get-items"></a>取得項目
 
**摘要：** 深入瞭解 [取得專案] 作業，這是專案服務的一部分。 專案服務是「呼叫品質」儀表板之存放庫 API 的一部分。 通話品質儀表板是商務用 Skype 伺服器的工具。
  
[取得專案] 作業是「用於通話品質」儀表板之 [存放庫 API] 中專案服務的一部分。
  
## <a name="get-items"></a>取得項目

取得專案會傳回存放庫中的所有專案。
  
|**方法**|**要求 URI**|**HTTP 版本**|
|:-----|:-----|:-----|
|GET  <br/> |HTTPs:// \<portal\> /QoERepositoryService/repository/item  <br/> |HTTP/1。1  <br/> |
   
 **URI 參數** -無。
  
 **要求標頭** -沒有其他標頭。
  
 **要求正文** -無。
  
 **回應** -回應包括 HTTP 狀態碼和一組回應標頭。
  
 **狀態碼** -成功的作業會傳回狀態碼 200 (確定) 。
  
 **回應標頭** -沒有其他標頭。
  
 **回應** 內文-以下是 JSON 中的範例回應負載。
  
> [!NOTE]
> 會傳回 Item 物件的陣列。 如需專案物件的詳細資訊，請參閱取得專案。 
  
```json
[{
"itemId": 1652,
"userId": 0,
"type": "application/json"
},
{
"itemId": 1653,
"userId": 0,
"type": "application/json"
},
{
"itemId": 1654,
"userId": 0,
"type": "application/json"
}]
```
