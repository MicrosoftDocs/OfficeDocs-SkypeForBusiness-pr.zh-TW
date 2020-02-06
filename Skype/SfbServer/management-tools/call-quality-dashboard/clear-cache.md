---
title: 清除快取
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
ms.assetid: 08648b16-7a64-41d8-9577-5000a20fce46
description: 摘要：瞭解 [清除快取] 作業，該作業是 [通話品質儀表板] 的資料 API 的一部分。 [通話品質儀表板] 是商務用 Skype Server 的工具。
ms.openlocfilehash: 821b02f204c98f5acefe69df1c848c31cd2205b7
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816882"
---
# <a name="clear-cache"></a>清除快取
 
**摘要：** 瞭解 [清除快取] 作業，該作業是 [通話品質儀表板] 的資料 API 的一部分。 [通話品質儀表板] 是商務用 Skype Server 的工具。
  
[清除快取] 作業是 [通話品質儀表板] 的資料 API 的一部分。
  
## <a name="clear-cache"></a>清除快取

[清除快取] 操作會刪除查詢和資料在伺服器上的快取。 這將會重設快取，然後從 QoE Cube 取得新的資料，之後就會出現新的要求。
  

|**法**|**要求 URI**|**HTTP 版本**|
|:-----|:-----|:-----|
|發佈  <br/> |HTTPs://\<入口\>網站/QoEDataService/ClearCache  <br/> |HTTP/1。1  <br/> |
   
 **URI 參數**-無。
  
 **要求標頭**-沒有其他標頭。
  
 **要求主體**-無。
  
 **回應**-回應包括 HTTP 狀態碼和一組回應標頭。
  
 **狀態碼**-成功的操作會傳回狀態碼200（確定）。
  
 **回應標題**-沒有其他標頭。
  
 **回應主體**-無。
  

