---
title: 取得整合記錄
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
ms.assetid: 8856f6bc-5460-4f35-acf2-f7662f01579b
description: 摘要：瞭解 [取得整合記錄] 作業，該作業是 [通話品質儀表板] 的資料 API 的一部分。 [通話品質儀表板] 是商務用 Skype Server 的工具。
ms.openlocfilehash: 9caa909e80a0bab5257af16fe77e9d154947a56e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816812"
---
# <a name="get-integration-log"></a>取得整合記錄
 
**摘要：** 瞭解 [取得整合記錄] 作業，該作業是 [通話品質儀表板] 的資料 API 的一部分。 [通話品質儀表板] 是商務用 Skype Server 的工具。
  
[取得整合記錄] 作業是 [通話品質] 儀表板的資料 API 的一部分
  
## <a name="get-integration-log"></a>取得整合記錄

取得整合記錄作業會傳回說明 QoE Cube 處理中之活動的記錄專案清單。
  
出於安全性考慮，預設會停用這個作業。 停用時，會傳回空字串。 若要啟用此操作，系統管理員必須針對資料 API 的主機 web 應用程式設定 web.config。
  

|法|**要求 URI**|**HTTP 版本**|
|:-----|:-----|:-----|
|獲取  <br/> |HTTPs://\<入口\>網站/QoEDataService/IntegrationLog  <br/> |HTTP/1。1  <br/> |
   
 **URI 參數**-無。
  
 **要求標頭**-沒有其他標頭。
  
 **要求主體**-無。
  
 **回應**-回應包括 HTTP 狀態碼和一組回應標頭。
  
 **狀態碼**-成功的操作會傳回狀態碼200（確定）。
  
 **回應標題**-沒有其他標頭。
  
 **回應主體**-以下是記錄專案的範例結構。
  
```
[
{"LogCategory":"<category>","LogTime":"2015-03-18T10:28:29.10","LogDescription":"<log description>"}
]
```


