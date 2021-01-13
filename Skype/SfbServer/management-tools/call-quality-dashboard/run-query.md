---
title: 執行查詢
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
ms.assetid: 45a77f7e-b137-462b-9146-3a0f43d8e0c7
description: 摘要：瞭解執行查詢作業，此作業是「通話品質」儀表板的資料 API 的一部分。 通話品質儀表板是商務用 Skype 伺服器的工具。
ms.openlocfilehash: bff24ca5a4d651ba276b4b0d795afabce3c6d0dd
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49803113"
---
# <a name="run-query"></a><span data-ttu-id="3926a-104">執行查詢</span><span class="sxs-lookup"><span data-stu-id="3926a-104">Run Query</span></span>

<span data-ttu-id="3926a-105">**摘要：** 深入瞭解執行查詢作業，此作業是「通話品質」儀表板的資料 API 的一部分。</span><span class="sxs-lookup"><span data-stu-id="3926a-105">**Summary:** Learn about the Run Query operation, which is part of the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="3926a-106">通話品質儀表板是商務用 Skype 伺服器的工具。</span><span class="sxs-lookup"><span data-stu-id="3926a-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>

<span data-ttu-id="3926a-107">執行查詢作業屬於通話品質儀表板的資料 API 的一部分。</span><span class="sxs-lookup"><span data-stu-id="3926a-107">The Run Query operation is part of the Data API for Call Quality Dashboard.</span></span>

## <a name="run-query"></a><span data-ttu-id="3926a-108">執行查詢</span><span class="sxs-lookup"><span data-stu-id="3926a-108">Run Query</span></span>

<span data-ttu-id="3926a-109">執行查詢作業可讓您根據指定的維度、度量及篩選，對 cube 執行查詢，並傳回資料。</span><span class="sxs-lookup"><span data-stu-id="3926a-109">Run Query operation provides the ability to run a query on the cube based on specified dimensions, measurements, and filters and return back the data.</span></span>


|<span data-ttu-id="3926a-110">**方法**</span><span class="sxs-lookup"><span data-stu-id="3926a-110">**Method**</span></span>|<span data-ttu-id="3926a-111">**要求 URI**</span><span class="sxs-lookup"><span data-stu-id="3926a-111">**Request URI**</span></span>|<span data-ttu-id="3926a-112">**HTTP 版本**</span><span class="sxs-lookup"><span data-stu-id="3926a-112">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="3926a-113">POST</span><span class="sxs-lookup"><span data-stu-id="3926a-113">POST</span></span>  <br/> |<span data-ttu-id="3926a-114">HTTPs:// \<portal\> /QoEDataService/RunQuery</span><span class="sxs-lookup"><span data-stu-id="3926a-114">https://\<portal\>/QoEDataService/RunQuery</span></span>  <br/> |<span data-ttu-id="3926a-115">HTTP/1。1</span><span class="sxs-lookup"><span data-stu-id="3926a-115">HTTP/1.1</span></span>  <br/> |

 <span data-ttu-id="3926a-116">**URI 參數** -無。</span><span class="sxs-lookup"><span data-stu-id="3926a-116">**URI Parameters** - None.</span></span>

 <span data-ttu-id="3926a-117">**要求標頭** -沒有其他標頭。</span><span class="sxs-lookup"><span data-stu-id="3926a-117">**Request Headers** - No additional headers.</span></span>

 <span data-ttu-id="3926a-118">**要求** 本文-這裡是 JSON 的範例要求負載。</span><span class="sxs-lookup"><span data-stu-id="3926a-118">**Request Body** - Here is a sample request payload in JSON.</span></span> <span data-ttu-id="3926a-119">包含查詢所需的維度、篩選和度量。</span><span class="sxs-lookup"><span data-stu-id="3926a-119">It contains dimensions, filters, and measurement required for a query.</span></span>

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

 <span data-ttu-id="3926a-120">*篩選*  器-要套用的篩選運算式清單，讓產生的資料集只會反映出相關資料的子集。</span><span class="sxs-lookup"><span data-stu-id="3926a-120">*Filters*  - A list of filter expressions to be applied such that the resulting data set will reflect only the subset of the data that are of interest.</span></span>

 <span data-ttu-id="3926a-121">*維度*  -將用於匯總資料的維度清單。</span><span class="sxs-lookup"><span data-stu-id="3926a-121">*Dimensions*  - A list of dimensions that will be used for aggregating the data.</span></span> <span data-ttu-id="3926a-122">至少需要一個維度，但是可以指定多個維度以取得其他的子聚合層級。</span><span class="sxs-lookup"><span data-stu-id="3926a-122">At least one dimension is required but multiple dimensions may be specified to obtain additional level of sub-aggregations.</span></span>

 <span data-ttu-id="3926a-123">*度量衡*  -度量值（也稱為實際值）的清單，也就是根據您指定的尺寸來匯總所需的度量。</span><span class="sxs-lookup"><span data-stu-id="3926a-123">*Measurements*  - A list of measurements, also known as facts, that are the desired metrics to be aggregated based on the dimensions you specified.</span></span>

 <span data-ttu-id="3926a-124">*趨勢*  -其他控制指示自訂結果資料。</span><span class="sxs-lookup"><span data-stu-id="3926a-124">*Trend*  - Additional control instructions to customize the result data.</span></span>

 <span data-ttu-id="3926a-125">**回應** -回應包括 HTTP 狀態碼和一組回應標頭。</span><span class="sxs-lookup"><span data-stu-id="3926a-125">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>

 <span data-ttu-id="3926a-126">**狀態碼** -成功的作業會傳回狀態碼 200 (確定) 。</span><span class="sxs-lookup"><span data-stu-id="3926a-126">**Status Code** - A successful operation returns status code 200 (OK).</span></span>

 <span data-ttu-id="3926a-127">**回應標頭** -沒有其他標頭。</span><span class="sxs-lookup"><span data-stu-id="3926a-127">**Response Headers** - No additional headers.</span></span>

 <span data-ttu-id="3926a-128">**回應** 內文-以下是 JSON 中的範例回應負載。</span><span class="sxs-lookup"><span data-stu-id="3926a-128">**Response Body** - Below is a sample response payload in JSON.</span></span> <span data-ttu-id="3926a-129">它包含的資料表格包含資料，也會包含中繼資料，該資料顯示查詢的執行時間，以及資料是否來自快取。</span><span class="sxs-lookup"><span data-stu-id="3926a-129">It contains a data table which contains the data, also it will contain a meta data, which shows query execution time and whether or not the data is from the cache.</span></span>

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

 <span data-ttu-id="3926a-130">*執行時間*  -伺服器傳回資料所需的總時間。</span><span class="sxs-lookup"><span data-stu-id="3926a-130">*Execution Time*  - The total time it took for the server to return the data.</span></span> <span data-ttu-id="3926a-131">這可能會包含快取，也可能不包含快取。</span><span class="sxs-lookup"><span data-stu-id="3926a-131">This may or may not involve cache.</span></span>

 <span data-ttu-id="3926a-132">*資料結果*  -查詢的結果。</span><span class="sxs-lookup"><span data-stu-id="3926a-132">*Data Result*  - The result of the query.</span></span> <span data-ttu-id="3926a-133">這是二維陣列，其中包含維度成員的所有相片順序，以及包含維度成員名稱的每個元素，以及指定度量值的匯總值。</span><span class="sxs-lookup"><span data-stu-id="3926a-133">It is a two-dimensional array containing all permutations of the dimensions' members, and each element containing the dimensions' member names as well as the aggregated values of the specified Measurements.</span></span>

 <span data-ttu-id="3926a-134">*結果來自*  快取-供診斷用。</span><span class="sxs-lookup"><span data-stu-id="3926a-134">*Result is From Cache*  - For diagnostics.</span></span> <span data-ttu-id="3926a-135">會指出結果來自快取還是來自 QoE Cube。</span><span class="sxs-lookup"><span data-stu-id="3926a-135">Indicates whether the result came from the cache or from the QoE Cube.</span></span>
