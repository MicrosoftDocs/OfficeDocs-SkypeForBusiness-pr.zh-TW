---
title: 取得 Cube
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
ms.assetid: c8eeb387-dc1e-44e0-bbf9-a566f8bda551
description: 摘要：瞭解「取得 Cube」作業，此作業是「通話品質」儀表板的資料 API 的一部分。 通話品質儀表板是商務用 Skype 伺服器的工具。
ms.openlocfilehash: a3527f21bc1751c23bba088ae06c3e6702cb8c8e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832623"
---
# <a name="get-cube"></a><span data-ttu-id="8dc5a-104">取得 Cube</span><span class="sxs-lookup"><span data-stu-id="8dc5a-104">Get Cube</span></span>
 
<span data-ttu-id="8dc5a-105">**摘要：** 深入瞭解「取得 Cube」作業，此作業是「通話品質」儀表板的資料 API 的一部分。</span><span class="sxs-lookup"><span data-stu-id="8dc5a-105">**Summary:** Learn about the Get Cube operation, which is part of the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="8dc5a-106">通話品質儀表板是商務用 Skype 伺服器的工具。</span><span class="sxs-lookup"><span data-stu-id="8dc5a-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="8dc5a-107">「取得 Cube」作業是「呼叫品質」儀表板之資料 API 的一部分。</span><span class="sxs-lookup"><span data-stu-id="8dc5a-107">The Get Cube operation is part of the Data API for Call Quality Dashboard.</span></span>
  
## <a name="get-cube"></a><span data-ttu-id="8dc5a-108">取得 Cube</span><span class="sxs-lookup"><span data-stu-id="8dc5a-108">Get Cube</span></span>

<span data-ttu-id="8dc5a-109">取得 Cube 作業會傳回可用的維度和度量清單。</span><span class="sxs-lookup"><span data-stu-id="8dc5a-109">Get Cube operation returns the list of available dimensions and measurements.</span></span>
  

|<span data-ttu-id="8dc5a-110">**方法**</span><span class="sxs-lookup"><span data-stu-id="8dc5a-110">**Method**</span></span>|<span data-ttu-id="8dc5a-111">**要求 URI**</span><span class="sxs-lookup"><span data-stu-id="8dc5a-111">**Request URI**</span></span>|<span data-ttu-id="8dc5a-112">**HTTP 版本**</span><span class="sxs-lookup"><span data-stu-id="8dc5a-112">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="8dc5a-113">GET</span><span class="sxs-lookup"><span data-stu-id="8dc5a-113">GET</span></span>  <br/> |<span data-ttu-id="8dc5a-114">HTTPs:// \<portal\> /QoEDataService/CubeStructure</span><span class="sxs-lookup"><span data-stu-id="8dc5a-114">https://\<portal\>/QoEDataService/CubeStructure</span></span>  <br/> |<span data-ttu-id="8dc5a-115">HTTP/1。1</span><span class="sxs-lookup"><span data-stu-id="8dc5a-115">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="8dc5a-116">**URI 參數** -無。</span><span class="sxs-lookup"><span data-stu-id="8dc5a-116">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="8dc5a-117">**要求標頭** -沒有其他標頭。</span><span class="sxs-lookup"><span data-stu-id="8dc5a-117">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="8dc5a-118">**要求正文** -無。</span><span class="sxs-lookup"><span data-stu-id="8dc5a-118">**Request Body** - None.</span></span>
  
 <span data-ttu-id="8dc5a-119">**回應** -回應包括 HTTP 狀態碼和一組回應標頭。</span><span class="sxs-lookup"><span data-stu-id="8dc5a-119">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="8dc5a-120">**狀態碼** -成功的作業會傳回狀態碼 200 (確定) 。</span><span class="sxs-lookup"><span data-stu-id="8dc5a-120">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="8dc5a-121">**回應標頭** -沒有其他標頭。</span><span class="sxs-lookup"><span data-stu-id="8dc5a-121">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="8dc5a-122">**回應** 內文-以下是 JSON 中的範例回應負載。</span><span class="sxs-lookup"><span data-stu-id="8dc5a-122">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
> [!NOTE]
> <span data-ttu-id="8dc5a-123">這個範例只會顯示每個 Cube 元素群組的前兩個元素。</span><span class="sxs-lookup"><span data-stu-id="8dc5a-123">This sample is only showing first two elements of each groups of Cube elements.</span></span> 
  
```json
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

 <span data-ttu-id="8dc5a-124">*KPIs*  保留。</span><span class="sxs-lookup"><span data-stu-id="8dc5a-124">*KPIs*  - Reserved.</span></span> <span data-ttu-id="8dc5a-125">要求負載的 KPIs 區段允許執行查詢作業，傳回 cube 中所定義之 KPIs 的值。</span><span class="sxs-lookup"><span data-stu-id="8dc5a-125">The KPIs section of a request payload allows Run Query operation to return values for the KPIs defined in the cube.</span></span> <span data-ttu-id="8dc5a-126">QoE Cube 中尚未存在 KPIs。</span><span class="sxs-lookup"><span data-stu-id="8dc5a-126">No KPIs exist in the QoE Cube yet.</span></span>
  
 <span data-ttu-id="8dc5a-127">*維度*  -可用於執行查詢作業之要求負載的篩選和維度區段中的維度清單。</span><span class="sxs-lookup"><span data-stu-id="8dc5a-127">*Dimensions*  - The list of dimensions that may be used in Filters and Dimensions sections of a request payload for Run Query operation.</span></span> <span data-ttu-id="8dc5a-128">若要使用篩選運算式中的維度，您必須指定可以使用「取得維度成員」作業來取得的維度成員。</span><span class="sxs-lookup"><span data-stu-id="8dc5a-128">To use a dimension in a filter expression, you need to specify a dimension member, which can be obtained using Get Dimension Members operation.</span></span>
  
 <span data-ttu-id="8dc5a-129">*度量*  -可用於「執行查詢」之要求負載的度量區段中的度量單位清單。</span><span class="sxs-lookup"><span data-stu-id="8dc5a-129">*Measurements*  - The list of measurements that may be used in Measurements section of a request payload for Run Query operation.</span></span>
  

