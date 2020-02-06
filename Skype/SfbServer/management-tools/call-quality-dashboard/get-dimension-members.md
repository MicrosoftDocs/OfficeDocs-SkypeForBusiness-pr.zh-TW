---
title: 取得維度成員
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
ms.assetid: bd89bbf7-cb98-4cd8-bbfa-0484663d14db
description: 摘要：瞭解 [取得維度成員] 操作。 [取得維度成員] 作業是 [通話品質儀表板] 的資料 API 的一部分。 [通話品質儀表板] 是商務用 Skype Server 的工具。
ms.openlocfilehash: ba80e14c011d6cecb9b70f8a8faf32764b5b433d
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816822"
---
# <a name="get-dimension-members"></a>取得維度成員
 
**摘要：** 瞭解取得維度成員的操作。 [取得維度成員] 作業是 [通話品質儀表板] 的資料 API 的一部分。 [通話品質儀表板] 是商務用 Skype Server 的工具。
  
[取得維度成員] 作業是 [通話品質儀表板] 的資料 API 的一部分。
  
## <a name="get-dimension-members"></a>取得維度成員

[取得維度成員] 操作會傳回特定維度之成員的清單。 它也提供篩選成員清單及取得子集的功能，以減少線路傳輸成本。
  

|**法**|**要求 URI**|**HTTP 版本**|
|:-----|:-----|:-----|
|發佈  <br/> |HTTPs://\<入口\>網站/QoEDataService/DimensionMembers  <br/> |HTTP/1。1  <br/> |
   
 **URI 參數**-無。
  
 **要求標頭**-沒有其他標頭。
  
 **要求主體**-這包含我們想要其成員的維度名稱。 此外，在傳回的成員數目上限，您可以指定一些篩選來限制傳回的成員。
  
```
{
"ByPassCache": false,
"DataModelName": "[StartDate].[Month]",
"SearchCaption": "",
"SearchValue": "",
"PageNumber": 0,
"PageSize": 8000
}
```

 **回應**-回應包括 HTTP 狀態碼和一組回應標頭。
  
 **狀態碼**-成功的操作會傳回狀態碼200（確定）。
  
 **回應標題**-沒有其他標頭。
  
 **回應主體**-以下是 JSON 中的範例回應載荷，以回應「[開始日期] 的要求。[Month] "維度。
  
> [!NOTE]
> 清單只會顯示清單的一小部分。 
  
```
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
