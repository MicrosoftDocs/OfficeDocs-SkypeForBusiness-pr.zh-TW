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
# <a name="run-query"></a><span data-ttu-id="03e1e-104">執行查詢</span><span class="sxs-lookup"><span data-stu-id="03e1e-104">Run Query</span></span>

<span data-ttu-id="03e1e-105">**摘要：** 瞭解 [執行查詢] 作業，該作業是 [通話品質儀表板] 的資料 API 的一部分。</span><span class="sxs-lookup"><span data-stu-id="03e1e-105">**Summary:** Learn about the Run Query operation, which is part of the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="03e1e-106">[通話品質儀表板] 是商務用 Skype Server 的工具。</span><span class="sxs-lookup"><span data-stu-id="03e1e-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>

<span data-ttu-id="03e1e-107">[執行查詢] 作業是 [通話品質儀表板] 的資料 API 的一部分。</span><span class="sxs-lookup"><span data-stu-id="03e1e-107">The Run Query operation is part of the Data API for Call Quality Dashboard.</span></span>

## <a name="run-query"></a><span data-ttu-id="03e1e-108">執行查詢</span><span class="sxs-lookup"><span data-stu-id="03e1e-108">Run Query</span></span>

<span data-ttu-id="03e1e-109">[執行查詢] 作業能根據指定的尺寸、測量及篩選，在立方體上執行查詢，並傳回資料。</span><span class="sxs-lookup"><span data-stu-id="03e1e-109">Run Query operation provides the ability to run a query on the cube based on specified dimensions, measurements, and filters and return back the data.</span></span>


|<span data-ttu-id="03e1e-110">**法**</span><span class="sxs-lookup"><span data-stu-id="03e1e-110">**Method**</span></span>|<span data-ttu-id="03e1e-111">**要求 URI**</span><span class="sxs-lookup"><span data-stu-id="03e1e-111">**Request URI**</span></span>|<span data-ttu-id="03e1e-112">**HTTP 版本**</span><span class="sxs-lookup"><span data-stu-id="03e1e-112">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="03e1e-113">發佈</span><span class="sxs-lookup"><span data-stu-id="03e1e-113">POST</span></span>  <br/> |<span data-ttu-id="03e1e-114">HTTPs://\<入口\>網站/QoEDataService/RunQuery</span><span class="sxs-lookup"><span data-stu-id="03e1e-114">https://\<portal\>/QoEDataService/RunQuery</span></span>  <br/> |<span data-ttu-id="03e1e-115">HTTP/1。1</span><span class="sxs-lookup"><span data-stu-id="03e1e-115">HTTP/1.1</span></span>  <br/> |

 <span data-ttu-id="03e1e-116">**URI 參數**-無。</span><span class="sxs-lookup"><span data-stu-id="03e1e-116">**URI Parameters** - None.</span></span>

 <span data-ttu-id="03e1e-117">**要求標頭**-沒有其他標頭。</span><span class="sxs-lookup"><span data-stu-id="03e1e-117">**Request Headers** - No additional headers.</span></span>

 <span data-ttu-id="03e1e-118">**要求主體**-以下是 JSON 中的範例要求負載。</span><span class="sxs-lookup"><span data-stu-id="03e1e-118">**Request Body** - Here is a sample request payload in JSON.</span></span> <span data-ttu-id="03e1e-119">它包含查詢所需的維度、篩選和度量。</span><span class="sxs-lookup"><span data-stu-id="03e1e-119">It contains dimensions, filters, and measurement required for a query.</span></span>

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

 <span data-ttu-id="03e1e-120">*篩選*-要套用的篩選運算式清單，讓產生的資料集只會反映感興趣資料的子集。</span><span class="sxs-lookup"><span data-stu-id="03e1e-120">*Filters*  - A list of filter expressions to be applied such that the resulting data set will reflect only the subset of the data that are of interest.</span></span>

 <span data-ttu-id="03e1e-121">[*維度*]-將用於匯總資料的維度清單。</span><span class="sxs-lookup"><span data-stu-id="03e1e-121">*Dimensions*  - A list of dimensions that will be used for aggregating the data.</span></span> <span data-ttu-id="03e1e-122">至少需要一個維度，但可能會指定多個維度，以取得額外的子匯總層級。</span><span class="sxs-lookup"><span data-stu-id="03e1e-122">At least one dimension is required but multiple dimensions may be specified to obtain additional level of sub-aggregations.</span></span>

 <span data-ttu-id="03e1e-123">*度量衡*：度量的清單（也稱為事實），根據您指定的大小來匯總所要的度量單位。</span><span class="sxs-lookup"><span data-stu-id="03e1e-123">*Measurements*  - A list of measurements, also known as facts, that are the desired metrics to be aggregated based on the dimensions you specified.</span></span>

 <span data-ttu-id="03e1e-124">*趨勢*-其他控制指示以自訂結果資料。</span><span class="sxs-lookup"><span data-stu-id="03e1e-124">*Trend*  - Additional control instructions to customize the result data.</span></span>

 <span data-ttu-id="03e1e-125">**回應**-回應包括 HTTP 狀態碼和一組回應標頭。</span><span class="sxs-lookup"><span data-stu-id="03e1e-125">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>

 <span data-ttu-id="03e1e-126">**狀態碼**-成功的操作會傳回狀態碼200（確定）。</span><span class="sxs-lookup"><span data-stu-id="03e1e-126">**Status Code** - A successful operation returns status code 200 (OK).</span></span>

 <span data-ttu-id="03e1e-127">**回應標題**-沒有其他標頭。</span><span class="sxs-lookup"><span data-stu-id="03e1e-127">**Response Headers** - No additional headers.</span></span>

 <span data-ttu-id="03e1e-128">**回應主體**-以下是 JSON 中的回應載荷範例。</span><span class="sxs-lookup"><span data-stu-id="03e1e-128">**Response Body** - Below is a sample response payload in JSON.</span></span> <span data-ttu-id="03e1e-129">它包含包含資料的資料表，也會包含中繼資料，這會顯示查詢執行時間，以及資料是否來自快取。</span><span class="sxs-lookup"><span data-stu-id="03e1e-129">It contains a data table which contains the data, also it will contain a meta data, which shows query execution time and whether or not the data is from the cache.</span></span>

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

 <span data-ttu-id="03e1e-130">*執行時間*-伺服器傳回資料所需的總時間。</span><span class="sxs-lookup"><span data-stu-id="03e1e-130">*Execution Time*  - The total time it took for the server to return the data.</span></span> <span data-ttu-id="03e1e-131">這可能會包含也可能不會涉及快取。</span><span class="sxs-lookup"><span data-stu-id="03e1e-131">This may or may not involve cache.</span></span>

 <span data-ttu-id="03e1e-132">*資料結果*-查詢的結果。</span><span class="sxs-lookup"><span data-stu-id="03e1e-132">*Data Result*  - The result of the query.</span></span> <span data-ttu-id="03e1e-133">它是包含維度成員所有相片順序的二維陣列，且每個元素都包含維度的成員名稱，以及指定測量的匯總值。</span><span class="sxs-lookup"><span data-stu-id="03e1e-133">It is a two-dimensional array containing all permutations of the dimensions' members, and each element containing the dimensions' member names as well as the aggregated values of the specified Measurements.</span></span>

 <span data-ttu-id="03e1e-134">*從*快取到診斷的結果。</span><span class="sxs-lookup"><span data-stu-id="03e1e-134">*Result is From Cache*  - For diagnostics.</span></span> <span data-ttu-id="03e1e-135">指出結果是來自快取，或是來自 QoE 立方體。</span><span class="sxs-lookup"><span data-stu-id="03e1e-135">Indicates whether the result came from the cache or from the QoE Cube.</span></span>
