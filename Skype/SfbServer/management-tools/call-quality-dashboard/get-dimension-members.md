---
title: 取得維度成員
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: bd89bbf7-cb98-4cd8-bbfa-0484663d14db
description: 摘要：瞭解「取得維度成員的運作。 「取得維度成員」作業是「呼叫品質」儀表板之資料 API 的一部分。 通話品質儀表板是商務用 Skype Server 的工具。
ms.openlocfilehash: a88ae16a3ccf15a60a36805f475894b657641e6e
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/05/2022
ms.locfileid: "62391035"
---
# <a name="get-dimension-members"></a>取得維度成員
 
**總結：** 深入瞭解「取得維度成員操作。 「取得維度成員」作業是「呼叫品質」儀表板之資料 API 的一部分。 通話品質儀表板是商務用 Skype Server 的工具。
  
「取得維度成員」作業是「呼叫品質」儀表板之資料 API 的一部分。
  
## <a name="get-dimension-members"></a>取得維度成員

取得維度成員操作傳回特定維度的成員清單。 它也可讓您篩選成員清單並取得子集，以降低線路傳輸成本。
  

|**方法**|**要求 URI**|**HTTP 版本**|
|:-----|:-----|:-----|
|POST  <br/> |HTTPs:// \<portal\> /QoEDataService/DimensionMembers  <br/> |HTTP/1。1  <br/> |
   
 **URI 參數** -無。
  
 **要求標頭** -沒有其他標頭。
  
 **要求主體** -這包含我們想要成員的維度名稱。 此外，傳回的成員人數上限，您可以指定一些篩選，以限制傳回的成員。
  
```json
{
"ByPassCache": false,
"DataModelName": "[StartDate].[Month]",
"SearchCaption": "",
"SearchValue": "",
"PageNumber": 0,
"PageSize": 8000
}
```

 **回應** -回應包括 HTTP 狀態碼和一組回應標頭。
  
 **狀態碼** -成功的作業會傳回狀態碼 200 (確定) 。
  
 **回應標頭** -沒有其他標頭。
  
 **回應** 內文-以下是 JSON 中的範例回應負載，以回應 "[StartDate] 的要求。[Month] "維度。
  
> [!NOTE]
> 清單只會顯示一小部分的清單。 
  
```json
{
"MembersCount": 493,
"Members": [["[1990-01-01T00:00:00]",
"January 1990"],
["[1990-02-01T00:00:00]",
"February 1990"],
["[1990-03-01T00:00:00]",
"March 1990"],
 
    ...
    
["[2030-10-01T00:00:00]",
"October 2030"],
["[2030-11-01T00:00:00]",
"November 2030"],
["[2030-12-01T00:00:00]",
"December 2030"],
["[2031-01-01T00:00:00]",
"January 2031"]]
}
```
