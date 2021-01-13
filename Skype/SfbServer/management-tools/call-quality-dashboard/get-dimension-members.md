---
title: 取得維度成員
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
ms.assetid: bd89bbf7-cb98-4cd8-bbfa-0484663d14db
description: 摘要：瞭解「取得維度成員的運作。 「取得維度成員」作業是「呼叫品質」儀表板之資料 API 的一部分。 通話品質儀表板是商務用 Skype 伺服器的工具。
ms.openlocfilehash: ffec3b02a3c876a003adb679a28b0e8f2edb91c2
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832633"
---
# <a name="get-dimension-members"></a><span data-ttu-id="5934c-105">取得維度成員</span><span class="sxs-lookup"><span data-stu-id="5934c-105">Get Dimension Members</span></span>
 
<span data-ttu-id="5934c-106">**摘要：** 深入瞭解「取得維度成員操作。</span><span class="sxs-lookup"><span data-stu-id="5934c-106">**Summary:** Learn about the Get Dimension Members operation.</span></span> <span data-ttu-id="5934c-107">「取得維度成員」作業是「呼叫品質」儀表板之資料 API 的一部分。</span><span class="sxs-lookup"><span data-stu-id="5934c-107">The Get Dimension Members operation is part of the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="5934c-108">通話品質儀表板是商務用 Skype 伺服器的工具。</span><span class="sxs-lookup"><span data-stu-id="5934c-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="5934c-109">「取得維度成員」作業是「呼叫品質」儀表板之資料 API 的一部分。</span><span class="sxs-lookup"><span data-stu-id="5934c-109">The Get Dimension Members operation is part of the Data API for Call Quality Dashboard.</span></span>
  
## <a name="get-dimension-members"></a><span data-ttu-id="5934c-110">取得維度成員</span><span class="sxs-lookup"><span data-stu-id="5934c-110">Get Dimension Members</span></span>

<span data-ttu-id="5934c-111">取得維度成員操作傳回特定維度的成員清單。</span><span class="sxs-lookup"><span data-stu-id="5934c-111">Get Dimension Members operation returns the list of members of a specific dimension.</span></span> <span data-ttu-id="5934c-112">它也可讓您篩選成員清單並取得子集，以降低線路傳輸成本。</span><span class="sxs-lookup"><span data-stu-id="5934c-112">It also give the ability to filter the member list and get a subset, to reduce the wire transfer cost.</span></span>
  

|<span data-ttu-id="5934c-113">**方法**</span><span class="sxs-lookup"><span data-stu-id="5934c-113">**Method**</span></span>|<span data-ttu-id="5934c-114">**要求 URI**</span><span class="sxs-lookup"><span data-stu-id="5934c-114">**Request URI**</span></span>|<span data-ttu-id="5934c-115">**HTTP 版本**</span><span class="sxs-lookup"><span data-stu-id="5934c-115">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="5934c-116">POST</span><span class="sxs-lookup"><span data-stu-id="5934c-116">POST</span></span>  <br/> |<span data-ttu-id="5934c-117">HTTPs:// \<portal\> /QoEDataService/DimensionMembers</span><span class="sxs-lookup"><span data-stu-id="5934c-117">https://\<portal\>/QoEDataService/DimensionMembers</span></span>  <br/> |<span data-ttu-id="5934c-118">HTTP/1。1</span><span class="sxs-lookup"><span data-stu-id="5934c-118">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="5934c-119">**URI 參數** -無。</span><span class="sxs-lookup"><span data-stu-id="5934c-119">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="5934c-120">**要求標頭** -沒有其他標頭。</span><span class="sxs-lookup"><span data-stu-id="5934c-120">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="5934c-121">**要求主體** -這包含我們想要成員的維度名稱。</span><span class="sxs-lookup"><span data-stu-id="5934c-121">**Request Body** - This contains the name of dimension we want the members for.</span></span> <span data-ttu-id="5934c-122">此外，傳回的成員人數上限，您可以指定一些篩選，以限制傳回的成員。</span><span class="sxs-lookup"><span data-stu-id="5934c-122">Also max number of members returned, beside you can specify some filtering to limit the returned members.</span></span>
  
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

 <span data-ttu-id="5934c-123">**回應** -回應包括 HTTP 狀態碼和一組回應標頭。</span><span class="sxs-lookup"><span data-stu-id="5934c-123">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="5934c-124">**狀態碼** -成功的作業會傳回狀態碼 200 (確定) 。</span><span class="sxs-lookup"><span data-stu-id="5934c-124">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="5934c-125">**回應標頭** -沒有其他標頭。</span><span class="sxs-lookup"><span data-stu-id="5934c-125">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="5934c-126">**回應** 內文-以下是 JSON 中的範例回應負載，以回應 "[StartDate] 的要求。[Month] "維度。</span><span class="sxs-lookup"><span data-stu-id="5934c-126">**Response Body** - Below is a sample response payload in JSON in response to a request for "[StartDate].[Month]" dimension.</span></span>
  
> [!NOTE]
> <span data-ttu-id="5934c-127">清單只會顯示一小部分的清單。</span><span class="sxs-lookup"><span data-stu-id="5934c-127">The list is only showing a small portion of the list.</span></span> 
  
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
