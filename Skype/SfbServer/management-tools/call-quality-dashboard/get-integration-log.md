---
title: 取得整合記錄
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 8856f6bc-5460-4f35-acf2-f7662f01579b
description: 摘要：瞭解「取得整合記錄」作業，此作業是「通話品質」儀表板的資料 API 的一部分。 通話品質儀表板是商務用 Skype Server 的工具。
ms.openlocfilehash: 8eca61cf97cc79f34be1f6473f3223b9f2a639d4
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/04/2021
ms.locfileid: "60759705"
---
# <a name="get-integration-log"></a>取得整合記錄
 
**摘要：** 深入瞭解「取得整合記錄」作業，此作業是「呼叫品質」儀表板的資料 API 的一部分。 通話品質儀表板是商務用 Skype Server 的工具。
  
「取得整合記錄」作業是「通話品質」儀表板之資料 API 的一部分
  
## <a name="get-integration-log"></a>取得整合記錄

取得整合記錄作業會傳回描述 QoE Cube 處理中之活動的記錄專案清單。
  
根據安全性原因，預設會停用此作業。 停用時，它會傳回空字串。 若要啟用此操作，管理員必須為數據 API 的主 web 應用程式設定 web.config。
  

|方法|**要求 URI**|**HTTP 版本**|
|:-----|:-----|:-----|
|GET  <br/> |HTTPs:// \<portal\> /QoEDataService/IntegrationLog  <br/> |HTTP/1。1  <br/> |
   
 **URI 參數** -無。
  
 **要求標頭** -沒有其他標頭。
  
 **要求正文** -無。
  
 **回應** -回應包括 HTTP 狀態碼和一組回應標頭。
  
 **狀態碼** -成功的作業會傳回狀態碼 200 (確定) 。
  
 **回應標頭** -沒有其他標頭。
  
 **回應** 內文-以下是記錄專案的範例結構。
  
```json
[
{"LogCategory":"<category>","LogTime":"2015-03-18T10:28:29.10","LogDescription":"<log description>"}
]
```


