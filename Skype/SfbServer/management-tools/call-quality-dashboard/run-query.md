---
title: 執行查詢
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 45a77f7e-b137-462b-9146-3a0f43d8e0c7
description: 摘要：瞭解 [執行查詢] 作業，該作業是 [通話品質儀表板] 的資料 API 的一部分。 [通話品質儀表板] 是商務用 Skype Server 的工具。
ms.openlocfilehash: 8d31ea4c597ea3353fdd5da3e863938aababe819
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991398"
---
# <a name="run-query"></a>執行查詢

**摘要：** 瞭解 [執行查詢] 作業，該作業是 [通話品質儀表板] 的資料 API 的一部分。 [通話品質儀表板] 是商務用 Skype Server 的工具。

[執行查詢] 作業是 [通話品質儀表板] 的資料 API 的一部分。

## <a name="run-query"></a>執行查詢

[執行查詢] 作業能根據指定的尺寸、測量及篩選，在立方體上執行查詢，並傳回資料。


|**法**|**要求 URI**|**HTTP 版本**|
|:-----|:-----|:-----|
|發佈  <br/> |HTTPs://\<入口\>網站/QoEDataService/RunQuery  <br/> |HTTP/1。1  <br/> |

 **URI 參數**-無。

 **要求標頭**-沒有其他標頭。

 **要求主體**-以下是 JSON 中的範例要求負載。 它包含查詢所需的維度、篩選和度量。

```json
{
"Filters": [{
"DataModelName": "[StartDate].[Month]",
"Caption": "July 2013",
"Value": "[2015-03-01T00:00:00]",
"Operand": 0,
"UnionGroup": ""
}],
"Dimensions": [{
"DataModelName": "[StartDate].[Month]"
}],
"Measurements": [{
"DataModelName": "[Measures].[Audio Good Streams Count]"
},
{
"DataModelName": "[Measures].[Audio UnClassified Streams Count]"
},
{
"DataModelName": "[Measures].[Audio Poor Streams Count]"
},
{
"DataModelName": "[Measures].[AudioPoorPercentage]"
}],
"Trend": {
"EnableTrend": true,
"SpanCount": 7,
"TrendDate": "2015-3",
"Type": 0
}
}
```

 *篩選*-要套用的篩選運算式清單，讓產生的資料集只會反映感興趣資料的子集。

 [*維度*]-將用於匯總資料的維度清單。 至少需要一個維度，但可能會指定多個維度，以取得額外的子匯總層級。

 *度量衡*：度量的清單（也稱為事實），根據您指定的大小來匯總所要的度量單位。

 *趨勢*-其他控制指示以自訂結果資料。

 **回應**-回應包括 HTTP 狀態碼和一組回應標頭。

 **狀態碼**-成功的操作會傳回狀態碼200（確定）。

 **回應標題**-沒有其他標頭。

 **回應主體**-以下是 JSON 中的回應載荷範例。 它包含包含資料的資料表，也會包含中繼資料，這會顯示查詢執行時間，以及資料是否來自快取。

```json
{
"ExecutionTime": "00:00:00.2102630",
"DataResult": [["September 2014",
        1792,
        34,
        78,
        4.171],
        ["October 2014",
        37017,
        1731,
        3305,
        8.197],
        ["November 2014",
        79184,
        3033,
        5556,
        6.557],
        ["December 2014",
        122253,
        4050,
        5444,
        4.263],
        ["January 2015",
        31246,
        1069,
        1342,
        4.118]],
"ResultIsFromCache": false,
"ErrorType": 0
}
```

 *執行時間*-伺服器傳回資料所需的總時間。 這可能會包含也可能不會涉及快取。

 *資料結果*-查詢的結果。 它是包含維度成員所有相片順序的二維陣列，且每個元素都包含維度的成員名稱，以及指定測量的匯總值。

 *從*快取到診斷的結果。 指出結果是來自快取，或是來自 QoE 立方體。
