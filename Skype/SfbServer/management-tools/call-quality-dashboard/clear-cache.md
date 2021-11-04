---
title: 清除快取
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
ms.assetid: 08648b16-7a64-41d8-9577-5000a20fce46
description: 摘要：瞭解清除快取作業，此作業是「通話品質」儀表板的資料 API 的一部分。 通話品質儀表板是商務用 Skype Server 的工具。
ms.openlocfilehash: f48c2308785a03ca9e344a31eddc7f5cc7f38a92
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/04/2021
ms.locfileid: "60778193"
---
# <a name="clear-cache"></a>清除快取
 
**摘要：** 深入瞭解「可供通話品質」儀表板之 [資料 API] 的 [清除快取] 作業。 通話品質儀表板是商務用 Skype Server 的工具。
  
「清除快取」作業是「通話品質」儀表板之資料 API 的一部分。
  
## <a name="clear-cache"></a>清除快取

清除快取作業會在伺服器上刪除查詢和資料的快取。 這將會重設快取，我們會在新的要求之後，從 QoE Cube 取得新的資料。
  

|**方法**|**要求 URI**|**HTTP 版本**|
|:-----|:-----|:-----|
|POST  <br/> |HTTPs:// \<portal\> /QoEDataService/ClearCache  <br/> |HTTP/1。1  <br/> |
   
 **URI 參數** -無。
  
 **要求標頭** -沒有其他標頭。
  
 **要求正文** -無。
  
 **回應** -回應包括 HTTP 狀態碼和一組回應標頭。
  
 **狀態碼** -成功的作業會傳回狀態碼 200 (確定) 。
  
 **回應標頭** -沒有其他標頭。
  
 **回應主體** -無。
  

