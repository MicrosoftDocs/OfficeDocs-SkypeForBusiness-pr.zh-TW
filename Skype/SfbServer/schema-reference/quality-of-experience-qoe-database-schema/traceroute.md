---
title: TraceRoute 資料表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b9493cef-6ece-4f13-bf68-dbf132aab4f4
description: TraceRoute 表格包含來自呼叫的路由資訊。 此表格是在 Microsoft Lync Server 2013 中推出。
ms.openlocfilehash: 323f8160e7543c2fa08bebe9d1805355469acfd9
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36192629"
---
# <a name="traceroute-table"></a><span data-ttu-id="0cdb6-104">TraceRoute 資料表</span><span class="sxs-lookup"><span data-stu-id="0cdb6-104">TraceRoute table</span></span>
 
<span data-ttu-id="0cdb6-105">TraceRoute 表格包含來自呼叫的路由資訊。</span><span class="sxs-lookup"><span data-stu-id="0cdb6-105">The TraceRoute table contains routing information from calls.</span></span> <span data-ttu-id="0cdb6-106">此表格是在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="0cdb6-106">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="0cdb6-107">**左欄**</span><span class="sxs-lookup"><span data-stu-id="0cdb6-107">**Column**</span></span>|<span data-ttu-id="0cdb6-108">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="0cdb6-108">**Data Type**</span></span>|<span data-ttu-id="0cdb6-109">**索引鍵/索引**</span><span class="sxs-lookup"><span data-stu-id="0cdb6-109">**Key/Index**</span></span>|<span data-ttu-id="0cdb6-110">**詳細資料**</span><span class="sxs-lookup"><span data-stu-id="0cdb6-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="0cdb6-111">**ConferenceDateTime**</span><span class="sxs-lookup"><span data-stu-id="0cdb6-111">**ConferenceDateTime**</span></span> <br/> |<span data-ttu-id="0cdb6-112">datetime</span><span class="sxs-lookup"><span data-stu-id="0cdb6-112">datetime</span></span>  <br/> |<span data-ttu-id="0cdb6-113">主要、外部</span><span class="sxs-lookup"><span data-stu-id="0cdb6-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="0cdb6-114">通話的開始日期和時間。</span><span class="sxs-lookup"><span data-stu-id="0cdb6-114">Date and time that the call began.</span></span>  <br/> |
|<span data-ttu-id="0cdb6-115">**SessionSeq**</span><span class="sxs-lookup"><span data-stu-id="0cdb6-115">**SessionSeq**</span></span> <br/> |<span data-ttu-id="0cdb6-116">int</span><span class="sxs-lookup"><span data-stu-id="0cdb6-116">int</span></span>  <br/> |<span data-ttu-id="0cdb6-117">主要、外部</span><span class="sxs-lookup"><span data-stu-id="0cdb6-117">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="0cdb6-118">唯一識別碼, 用來區分可能已在相同日期和同一時間開始的多個通話。</span><span class="sxs-lookup"><span data-stu-id="0cdb6-118">Unique identifier used to distinguish between multiple calls that might have begun on the same date and at the same time.</span></span>  <br/> |
|<span data-ttu-id="0cdb6-119">**MediaLineLabel**</span><span class="sxs-lookup"><span data-stu-id="0cdb6-119">**MediaLineLabel**</span></span> <br/> |<span data-ttu-id="0cdb6-120">Tinyint</span><span class="sxs-lookup"><span data-stu-id="0cdb6-120">tinyint</span></span>  <br/> |<span data-ttu-id="0cdb6-121">主要、外部</span><span class="sxs-lookup"><span data-stu-id="0cdb6-121">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="0cdb6-122">代表通話中使用的影片線條類型。</span><span class="sxs-lookup"><span data-stu-id="0cdb6-122">Represents the type of video line used in the call.</span></span> <span data-ttu-id="0cdb6-123">允許的值為：</span><span class="sxs-lookup"><span data-stu-id="0cdb6-123">Allowed values are:</span></span>  <br/> <span data-ttu-id="0cdb6-124">0-音訊</span><span class="sxs-lookup"><span data-stu-id="0cdb6-124">0 - Audio</span></span>  <br/> <span data-ttu-id="0cdb6-125">1-影片</span><span class="sxs-lookup"><span data-stu-id="0cdb6-125">1 - Video</span></span>  <br/> <span data-ttu-id="0cdb6-126">2-全景影片</span><span class="sxs-lookup"><span data-stu-id="0cdb6-126">2 - Panoramic video</span></span>  <br/> <span data-ttu-id="0cdb6-127">3-應用程式/桌面共用</span><span class="sxs-lookup"><span data-stu-id="0cdb6-127">3 - Application/Desktop sharing</span></span>  <br/> |
|<span data-ttu-id="0cdb6-128">**FromCaller**</span><span class="sxs-lookup"><span data-stu-id="0cdb6-128">**FromCaller**</span></span> <br/> |<span data-ttu-id="0cdb6-129">稍微</span><span class="sxs-lookup"><span data-stu-id="0cdb6-129">bit</span></span>  <br/> |<span data-ttu-id="0cdb6-130">首選</span><span class="sxs-lookup"><span data-stu-id="0cdb6-130">Primary</span></span>  <br/> |<span data-ttu-id="0cdb6-131">放置通話的端點。</span><span class="sxs-lookup"><span data-stu-id="0cdb6-131">Endpoint that placed the call.</span></span>  <br/> |
|<span data-ttu-id="0cdb6-132">**中繼站**</span><span class="sxs-lookup"><span data-stu-id="0cdb6-132">**Hop**</span></span> <br/> |<span data-ttu-id="0cdb6-133">int</span><span class="sxs-lookup"><span data-stu-id="0cdb6-133">int</span></span>  <br/> ||<span data-ttu-id="0cdb6-134">Network hop/</span><span class="sxs-lookup"><span data-stu-id="0cdb6-134">Network hop/</span></span>  <br/> |
|<span data-ttu-id="0cdb6-135">**IPAddressKey**</span><span class="sxs-lookup"><span data-stu-id="0cdb6-135">**IPAddressKey**</span></span> <br/> |<span data-ttu-id="0cdb6-136">int</span><span class="sxs-lookup"><span data-stu-id="0cdb6-136">int</span></span>  <br/> |<span data-ttu-id="0cdb6-137">外</span><span class="sxs-lookup"><span data-stu-id="0cdb6-137">Foreign</span></span>  <br/> |<span data-ttu-id="0cdb6-138">IP 位址的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="0cdb6-138">Unique identifier for the IP address.</span></span> <span data-ttu-id="0cdb6-139">IP 位址資訊會儲存在 [ [IPAddress] 資料表](ipaddress.md)中。</span><span class="sxs-lookup"><span data-stu-id="0cdb6-139">IP address information is stored in the [IPAddress table](ipaddress.md).</span></span>  <br/> |
|<span data-ttu-id="0cdb6-140">**RTT**</span><span class="sxs-lookup"><span data-stu-id="0cdb6-140">**RTT**</span></span> <br/> |<span data-ttu-id="0cdb6-141">int</span><span class="sxs-lookup"><span data-stu-id="0cdb6-141">int</span></span>  <br/> ||<span data-ttu-id="0cdb6-142">往返時間。</span><span class="sxs-lookup"><span data-stu-id="0cdb6-142">Roundtrip time.</span></span> <span data-ttu-id="0cdb6-143">往返時間會測量語音資料包達到目的地所需的時間長度, 然後傳回接收的通知。</span><span class="sxs-lookup"><span data-stu-id="0cdb6-143">The roundtrip time measures the amount of time it takes for a voice packet to reach its destination and then send back notification that it was received.</span></span>  <br/> |
   

