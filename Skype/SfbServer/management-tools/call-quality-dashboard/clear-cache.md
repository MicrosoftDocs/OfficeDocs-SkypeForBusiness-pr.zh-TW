---
title: 清除快取
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
ms.assetid: 08648b16-7a64-41d8-9577-5000a20fce46
description: 摘要：瞭解清除快取作業，此作業是「通話品質」儀表板的資料 API 的一部分。 通話品質儀表板是商務用 Skype 伺服器的工具。
ms.openlocfilehash: c9b966bb1e35a5a6255cd75ea6c685daaf220a09
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806413"
---
# <a name="clear-cache"></a><span data-ttu-id="2e8b2-104">清除快取</span><span class="sxs-lookup"><span data-stu-id="2e8b2-104">Clear Cache</span></span>
 
<span data-ttu-id="2e8b2-105">**摘要：** 深入瞭解「可供通話品質」儀表板之 [資料 API] 的 [清除快取] 作業。</span><span class="sxs-lookup"><span data-stu-id="2e8b2-105">**Summary:** Learn about the Clear Cache operation, which is part of the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="2e8b2-106">通話品質儀表板是商務用 Skype 伺服器的工具。</span><span class="sxs-lookup"><span data-stu-id="2e8b2-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="2e8b2-107">「清除快取」作業是「通話品質」儀表板之資料 API 的一部分。</span><span class="sxs-lookup"><span data-stu-id="2e8b2-107">The Clear Cache operation is part of the Data API for Call Quality Dashboard.</span></span>
  
## <a name="clear-cache"></a><span data-ttu-id="2e8b2-108">清除快取</span><span class="sxs-lookup"><span data-stu-id="2e8b2-108">Clear Cache</span></span>

<span data-ttu-id="2e8b2-109">清除快取作業會在伺服器上刪除查詢和資料的快取。</span><span class="sxs-lookup"><span data-stu-id="2e8b2-109">Clear Cache operation deletes the cache on server for queries and data.</span></span> <span data-ttu-id="2e8b2-110">這將會重設快取，我們會在新的要求之後，從 QoE Cube 取得新的資料。</span><span class="sxs-lookup"><span data-stu-id="2e8b2-110">This will reset the cache and we will get fresh data from QoE Cube afterward for new requests.</span></span>
  

|<span data-ttu-id="2e8b2-111">**方法**</span><span class="sxs-lookup"><span data-stu-id="2e8b2-111">**Method**</span></span>|<span data-ttu-id="2e8b2-112">**要求 URI**</span><span class="sxs-lookup"><span data-stu-id="2e8b2-112">**Request URI**</span></span>|<span data-ttu-id="2e8b2-113">**HTTP 版本**</span><span class="sxs-lookup"><span data-stu-id="2e8b2-113">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="2e8b2-114">POST</span><span class="sxs-lookup"><span data-stu-id="2e8b2-114">POST</span></span>  <br/> |<span data-ttu-id="2e8b2-115">HTTPs:// \<portal\> /QoEDataService/ClearCache</span><span class="sxs-lookup"><span data-stu-id="2e8b2-115">https://\<portal\>/QoEDataService/ClearCache</span></span>  <br/> |<span data-ttu-id="2e8b2-116">HTTP/1。1</span><span class="sxs-lookup"><span data-stu-id="2e8b2-116">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="2e8b2-117">**URI 參數** -無。</span><span class="sxs-lookup"><span data-stu-id="2e8b2-117">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="2e8b2-118">**要求標頭** -沒有其他標頭。</span><span class="sxs-lookup"><span data-stu-id="2e8b2-118">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="2e8b2-119">**要求正文** -無。</span><span class="sxs-lookup"><span data-stu-id="2e8b2-119">**Request Body** - None.</span></span>
  
 <span data-ttu-id="2e8b2-120">**回應** -回應包括 HTTP 狀態碼和一組回應標頭。</span><span class="sxs-lookup"><span data-stu-id="2e8b2-120">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="2e8b2-121">**狀態碼** -成功的作業會傳回狀態碼 200 (確定) 。</span><span class="sxs-lookup"><span data-stu-id="2e8b2-121">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="2e8b2-122">**回應標頭** -沒有其他標頭。</span><span class="sxs-lookup"><span data-stu-id="2e8b2-122">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="2e8b2-123">**回應主體** -無。</span><span class="sxs-lookup"><span data-stu-id="2e8b2-123">**Response Body** - None.</span></span>
  

