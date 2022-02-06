---
title: 執行查詢
ms.reviewer: null
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
ms.assetid: 45a77f7e-b137-462b-9146-3a0f43d8e0c7
description: 摘要：瞭解執行查詢作業，此作業是「通話品質」儀表板的資料 API 的一部分。 通話品質儀表板是商務用 Skype Server 的工具。
---

# <a name="run-query"></a>執行查詢

**總結：** 深入瞭解執行查詢作業，此作業是「通話品質」儀表板的資料 API 的一部分。 通話品質儀表板是商務用 Skype Server 的工具。

執行查詢作業屬於通話品質儀表板的資料 API 的一部分。

## <a name="run-query"></a>執行查詢

執行查詢作業可讓您根據指定的維度、度量及篩選，對 cube 執行查詢，並傳回資料。


|**方法**|**要求 URI**|**HTTP 版本**|
|:-----|:-----|:-----|
|POST  <br/> |HTTPs:// \<portal\> /QoEDataService/RunQuery  <br/> |HTTP/1。1  <br/> |

 **URI 參數** -無。

 **要求標頭** -沒有其他標頭。

 **要求** 本文-這裡是 JSON 的範例要求負載。 包含查詢所需的維度、篩選和度量。

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

 *篩選*  器-要套用的篩選運算式清單，讓產生的資料集只會反映出相關資料的子集。

 *維度*  -將用於匯總資料的維度清單。 至少需要一個維度，但是可以指定多個維度以取得其他的子聚合層級。

 *度量衡*  -度量值（也稱為實際值）的清單，也就是根據您指定的尺寸來匯總所需的度量。

 *趨勢*  -其他控制指示自訂結果資料。

 **回應** -回應包括 HTTP 狀態碼和一組回應標頭。

 **狀態碼** -成功的作業會傳回狀態碼 200 (確定) 。

 **回應標頭** -沒有其他標頭。

 **回應** 內文-以下是 JSON 中的範例回應負載。 它包含的資料表格包含資料，也會包含中繼資料，該資料顯示查詢的執行時間，以及資料是否來自快取。

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

 *執行時間*  -伺服器傳回資料所需的總時間。 這可能會包含快取，也可能不包含快取。

 *資料結果*  -查詢的結果。 這是二維陣列，其中包含維度成員的所有相片順序，以及包含維度成員名稱的每個元素，以及指定度量值的匯總值。

 *結果來自*  快取-供診斷用。 會指出結果來自快取還是來自 QoE Cube。
