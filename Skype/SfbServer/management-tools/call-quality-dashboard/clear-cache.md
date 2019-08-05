---
title: 清除快取
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 08648b16-7a64-41d8-9577-5000a20fce46
description: '摘要: 瞭解 [清除快取] 作業, 該作業是 [通話品質儀表板] 的資料 API 的一部分。 [通話品質儀表板] 是商務用 Skype Server 的工具。'
ms.openlocfilehash: 38648e1a910f93a30bd6da8807321acad0330e62
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36186982"
---
# <a name="clear-cache"></a><span data-ttu-id="6323a-104">清除快取</span><span class="sxs-lookup"><span data-stu-id="6323a-104">Clear Cache</span></span>
 
<span data-ttu-id="6323a-105">**摘要:** 瞭解 [清除快取] 作業, 該作業是 [通話品質儀表板] 的資料 API 的一部分。</span><span class="sxs-lookup"><span data-stu-id="6323a-105">**Summary:** Learn about the Clear Cache operation, which is part of the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="6323a-106">[通話品質儀表板] 是商務用 Skype Server 的工具。</span><span class="sxs-lookup"><span data-stu-id="6323a-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="6323a-107">[清除快取] 作業是 [通話品質儀表板] 的資料 API 的一部分。</span><span class="sxs-lookup"><span data-stu-id="6323a-107">The Clear Cache operation is part of the Data API for Call Quality Dashboard.</span></span>
  
## <a name="clear-cache"></a><span data-ttu-id="6323a-108">清除快取</span><span class="sxs-lookup"><span data-stu-id="6323a-108">Clear Cache</span></span>

<span data-ttu-id="6323a-109">[清除快取] 操作會刪除查詢和資料在伺服器上的快取。</span><span class="sxs-lookup"><span data-stu-id="6323a-109">Clear Cache operation deletes the cache on server for queries and data.</span></span> <span data-ttu-id="6323a-110">這將會重設快取, 然後從 QoE Cube 取得新的資料, 之後就會出現新的要求。</span><span class="sxs-lookup"><span data-stu-id="6323a-110">This will reset the cache and we will get fresh data from QoE Cube afterward for new requests.</span></span>
  

|<span data-ttu-id="6323a-111">**法**</span><span class="sxs-lookup"><span data-stu-id="6323a-111">**Method**</span></span>|<span data-ttu-id="6323a-112">**要求 URI**</span><span class="sxs-lookup"><span data-stu-id="6323a-112">**Request URI**</span></span>|<span data-ttu-id="6323a-113">**HTTP 版本**</span><span class="sxs-lookup"><span data-stu-id="6323a-113">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="6323a-114">發佈</span><span class="sxs-lookup"><span data-stu-id="6323a-114">POST</span></span>  <br/> |<span data-ttu-id="6323a-115">HTTPs://\<入口\>網站/QoEDataService/ClearCache</span><span class="sxs-lookup"><span data-stu-id="6323a-115">https://\<portal\>/QoEDataService/ClearCache</span></span>  <br/> |<span data-ttu-id="6323a-116">HTTP/1。1</span><span class="sxs-lookup"><span data-stu-id="6323a-116">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="6323a-117">**URI 參數**-無。</span><span class="sxs-lookup"><span data-stu-id="6323a-117">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="6323a-118">**要求標頭**-沒有其他標頭。</span><span class="sxs-lookup"><span data-stu-id="6323a-118">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="6323a-119">**要求主體**-無。</span><span class="sxs-lookup"><span data-stu-id="6323a-119">**Request Body** - None.</span></span>
  
 <span data-ttu-id="6323a-120">**回應**-回應包括 HTTP 狀態碼和一組回應標頭。</span><span class="sxs-lookup"><span data-stu-id="6323a-120">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="6323a-121">**狀態碼**-成功的操作會傳回狀態碼 200 (確定)。</span><span class="sxs-lookup"><span data-stu-id="6323a-121">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="6323a-122">**回應標題**-沒有其他標頭。</span><span class="sxs-lookup"><span data-stu-id="6323a-122">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="6323a-123">**回應主體**-無。</span><span class="sxs-lookup"><span data-stu-id="6323a-123">**Response Body** - None.</span></span>
  

