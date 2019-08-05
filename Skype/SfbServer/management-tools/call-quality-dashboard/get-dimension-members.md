---
title: 取得維度成員
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: bd89bbf7-cb98-4cd8-bbfa-0484663d14db
description: '摘要: 瞭解 [取得維度成員] 操作。 [取得維度成員] 作業是 [通話品質儀表板] 的資料 API 的一部分。 [通話品質儀表板] 是商務用 Skype Server 的工具。'
ms.openlocfilehash: c457e7f3b42aaeb11c35180bc4c1ae6ee42b914e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36186946"
---
# <a name="get-dimension-members"></a><span data-ttu-id="aca4e-105">取得維度成員</span><span class="sxs-lookup"><span data-stu-id="aca4e-105">Get Dimension Members</span></span>
 
<span data-ttu-id="aca4e-106">**摘要:** 瞭解取得維度成員的操作。</span><span class="sxs-lookup"><span data-stu-id="aca4e-106">**Summary:** Learn about the Get Dimension Members operation.</span></span> <span data-ttu-id="aca4e-107">[取得維度成員] 作業是 [通話品質儀表板] 的資料 API 的一部分。</span><span class="sxs-lookup"><span data-stu-id="aca4e-107">The Get Dimension Members operation is part of the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="aca4e-108">[通話品質儀表板] 是商務用 Skype Server 的工具。</span><span class="sxs-lookup"><span data-stu-id="aca4e-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="aca4e-109">[取得維度成員] 作業是 [通話品質儀表板] 的資料 API 的一部分。</span><span class="sxs-lookup"><span data-stu-id="aca4e-109">The Get Dimension Members operation is part of the Data API for Call Quality Dashboard.</span></span>
  
## <a name="get-dimension-members"></a><span data-ttu-id="aca4e-110">取得維度成員</span><span class="sxs-lookup"><span data-stu-id="aca4e-110">Get Dimension Members</span></span>

<span data-ttu-id="aca4e-111">[取得維度成員] 操作會傳回特定維度之成員的清單。</span><span class="sxs-lookup"><span data-stu-id="aca4e-111">Get Dimension Members operation returns the list of members of a specific dimension.</span></span> <span data-ttu-id="aca4e-112">它也提供篩選成員清單及取得子集的功能, 以減少線路傳輸成本。</span><span class="sxs-lookup"><span data-stu-id="aca4e-112">It also give the ability to filter the member list and get a subset, to reduce the wire transfer cost.</span></span>
  

|<span data-ttu-id="aca4e-113">**法**</span><span class="sxs-lookup"><span data-stu-id="aca4e-113">**Method**</span></span>|<span data-ttu-id="aca4e-114">**要求 URI**</span><span class="sxs-lookup"><span data-stu-id="aca4e-114">**Request URI**</span></span>|<span data-ttu-id="aca4e-115">**HTTP 版本**</span><span class="sxs-lookup"><span data-stu-id="aca4e-115">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="aca4e-116">發佈</span><span class="sxs-lookup"><span data-stu-id="aca4e-116">POST</span></span>  <br/> |<span data-ttu-id="aca4e-117">HTTPs://\<入口\>網站/QoEDataService/DimensionMembers</span><span class="sxs-lookup"><span data-stu-id="aca4e-117">https://\<portal\>/QoEDataService/DimensionMembers</span></span>  <br/> |<span data-ttu-id="aca4e-118">HTTP/1。1</span><span class="sxs-lookup"><span data-stu-id="aca4e-118">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="aca4e-119">**URI 參數**-無。</span><span class="sxs-lookup"><span data-stu-id="aca4e-119">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="aca4e-120">**要求標頭**-沒有其他標頭。</span><span class="sxs-lookup"><span data-stu-id="aca4e-120">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="aca4e-121">**要求主體**-這包含我們想要其成員的維度名稱。</span><span class="sxs-lookup"><span data-stu-id="aca4e-121">**Request Body** - This contains the name of dimension we want the members for.</span></span> <span data-ttu-id="aca4e-122">此外, 在傳回的成員數目上限, 您可以指定一些篩選來限制傳回的成員。</span><span class="sxs-lookup"><span data-stu-id="aca4e-122">Also max number of members returned, beside you can specify some filtering to limit the returned members.</span></span>
  
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

 <span data-ttu-id="aca4e-123">**回應**-回應包括 HTTP 狀態碼和一組回應標頭。</span><span class="sxs-lookup"><span data-stu-id="aca4e-123">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="aca4e-124">**狀態碼**-成功的操作會傳回狀態碼 200 (確定)。</span><span class="sxs-lookup"><span data-stu-id="aca4e-124">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="aca4e-125">**回應標題**-沒有其他標頭。</span><span class="sxs-lookup"><span data-stu-id="aca4e-125">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="aca4e-126">**回應主體**-以下是 JSON 中的範例回應載荷, 以回應「[開始日期] 的要求。[Month] "維度。</span><span class="sxs-lookup"><span data-stu-id="aca4e-126">**Response Body** - Below is a sample response payload in JSON in response to a request for "[StartDate].[Month]" dimension.</span></span>
  
> [!NOTE]
> <span data-ttu-id="aca4e-127">清單只會顯示清單的一小部分。</span><span class="sxs-lookup"><span data-stu-id="aca4e-127">The list is only showing a small portion of the list.</span></span> 
  
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
