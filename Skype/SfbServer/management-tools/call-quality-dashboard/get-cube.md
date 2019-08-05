---
title: 取得立方體
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: c8eeb387-dc1e-44e0-bbf9-a566f8bda551
description: '摘要: 瞭解 [取得 Cube] 作業, 該作業是 [通話品質儀表板] 的資料 API 的一部分。 [通話品質儀表板] 是商務用 Skype Server 的工具。'
ms.openlocfilehash: 970187ce9f95700185ab09bd7aadf9045575b393
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36186949"
---
# <a name="get-cube"></a><span data-ttu-id="83ef8-104">取得立方體</span><span class="sxs-lookup"><span data-stu-id="83ef8-104">Get Cube</span></span>
 
<span data-ttu-id="83ef8-105">**摘要:** 瞭解 [取得 Cube] 作業, 該作業是 [通話品質儀表板] 的資料 API 的一部分。</span><span class="sxs-lookup"><span data-stu-id="83ef8-105">**Summary:** Learn about the Get Cube operation, which is part of the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="83ef8-106">[通話品質儀表板] 是商務用 Skype Server 的工具。</span><span class="sxs-lookup"><span data-stu-id="83ef8-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="83ef8-107">[取得 Cube] 作業是 [通話品質] 儀表板的資料 API 的一部分。</span><span class="sxs-lookup"><span data-stu-id="83ef8-107">The Get Cube operation is part of the Data API for Call Quality Dashboard.</span></span>
  
## <a name="get-cube"></a><span data-ttu-id="83ef8-108">取得立方體</span><span class="sxs-lookup"><span data-stu-id="83ef8-108">Get Cube</span></span>

<span data-ttu-id="83ef8-109">[取得 Cube] 操作會傳回可用尺寸與測量的清單。</span><span class="sxs-lookup"><span data-stu-id="83ef8-109">Get Cube operation returns the list of available dimensions and measurements.</span></span>
  

|<span data-ttu-id="83ef8-110">**法**</span><span class="sxs-lookup"><span data-stu-id="83ef8-110">**Method**</span></span>|<span data-ttu-id="83ef8-111">**要求 URI**</span><span class="sxs-lookup"><span data-stu-id="83ef8-111">**Request URI**</span></span>|<span data-ttu-id="83ef8-112">**HTTP 版本**</span><span class="sxs-lookup"><span data-stu-id="83ef8-112">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="83ef8-113">獲取</span><span class="sxs-lookup"><span data-stu-id="83ef8-113">GET</span></span>  <br/> |<span data-ttu-id="83ef8-114">HTTPs://\<入口\>網站/QoEDataService/CubeStructure</span><span class="sxs-lookup"><span data-stu-id="83ef8-114">https://\<portal\>/QoEDataService/CubeStructure</span></span>  <br/> |<span data-ttu-id="83ef8-115">HTTP/1。1</span><span class="sxs-lookup"><span data-stu-id="83ef8-115">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="83ef8-116">**URI 參數**-無。</span><span class="sxs-lookup"><span data-stu-id="83ef8-116">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="83ef8-117">**要求標頭**-沒有其他標頭。</span><span class="sxs-lookup"><span data-stu-id="83ef8-117">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="83ef8-118">**要求主體**-無。</span><span class="sxs-lookup"><span data-stu-id="83ef8-118">**Request Body** - None.</span></span>
  
 <span data-ttu-id="83ef8-119">**回應**-回應包括 HTTP 狀態碼和一組回應標頭。</span><span class="sxs-lookup"><span data-stu-id="83ef8-119">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="83ef8-120">**狀態碼**-成功的操作會傳回狀態碼 200 (確定)。</span><span class="sxs-lookup"><span data-stu-id="83ef8-120">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="83ef8-121">**回應標題**-沒有其他標頭。</span><span class="sxs-lookup"><span data-stu-id="83ef8-121">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="83ef8-122">**回應主體**-以下是 JSON 中的回應載荷範例。</span><span class="sxs-lookup"><span data-stu-id="83ef8-122">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
> [!NOTE]
> <span data-ttu-id="83ef8-123">這個範例只會顯示每個 Cube 元素群組的前兩個元素。</span><span class="sxs-lookup"><span data-stu-id="83ef8-123">This sample is only showing first two elements of each groups of Cube elements.</span></span> 
  
```
{
"Kpis": [{
"FriendlyName": "Poor Trend Month",
"DataModelName": "[KPIValue].Poor Trend Month",
"Description": null
},
{
"FriendlyName": "Poor Rate Trend Month",
"DataModelName": "[KPIValue].Poor Rate Trend Month",
"Description": null
}],
"Dimensions": [{
"Category": "Access Location Pair",
"Attributes": [{
"FriendlyName": "Location Pair",
"DataModelName": "[Access Location Pair].[Location Pair]",
"Description": "Description of Location Pair"
}]
},
{
"Category": "Audio Bandwidth Est",
"Attributes": [{
"FriendlyName": "Metric",
"DataModelName": "[Audio Bandwidth Est].[Metric]",
"Description": "Description of Metric"
}]
}],
"Measurements": [{
"FriendlyName": "Audio Streams Count",
"DataModelName": "[Measures].[Audio Streams Count]",
"Description": "Description of Audio Streams Count"
},
{
"FriendlyName": "Audio Good Streams JPDR Count",
"DataModelName": "[Measures].[Audio Good Streams JPDR Count]",
"Description": "Description of Audio Good Streams JPDR Count"
}]
}
```

 <span data-ttu-id="83ef8-124">*Kpi* -已保留。</span><span class="sxs-lookup"><span data-stu-id="83ef8-124">*KPIs*  - Reserved.</span></span> <span data-ttu-id="83ef8-125">[要求負載] 的 [Kpi] 區段可讓 [執行查詢] 作業傳回多維資料集中定義之 Kpi 的值。</span><span class="sxs-lookup"><span data-stu-id="83ef8-125">The KPIs section of a request payload allows Run Query operation to return values for the KPIs defined in the cube.</span></span> <span data-ttu-id="83ef8-126">QoE Cube 中尚不存在任何 Kpi。</span><span class="sxs-lookup"><span data-stu-id="83ef8-126">No KPIs exist in the QoE Cube yet.</span></span>
  
 <span data-ttu-id="83ef8-127">[*維度*]-在執行查詢作業的要求負載之 [篩選] 和 [維度] 區段中可能會用到的維度清單。</span><span class="sxs-lookup"><span data-stu-id="83ef8-127">*Dimensions*  - The list of dimensions that may be used in Filters and Dimensions sections of a request payload for Run Query operation.</span></span> <span data-ttu-id="83ef8-128">若要在篩選運算式中使用維度, 您需要指定可使用 [取得維度成員] 操作取得的維度成員。</span><span class="sxs-lookup"><span data-stu-id="83ef8-128">To use a dimension in a filter expression, you need to specify a dimension member, which can be obtained using Get Dimension Members operation.</span></span>
  
 <span data-ttu-id="83ef8-129">*度量衡*-可在執行查詢作業的要求負載測量區段中使用的度量單位清單。</span><span class="sxs-lookup"><span data-stu-id="83ef8-129">*Measurements*  - The list of measurements that may be used in Measurements section of a request payload for Run Query operation.</span></span>
  

