---
title: TraceRoute 表格
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b9493cef-6ece-4f13-bf68-dbf132aab4f4
description: TraceRoute 表格包含來自呼叫的路由資訊。 此表格已引進 Microsoft Lync Server 2013。
ms.openlocfilehash: 7ecad93cca80a9b7cea73f64158b3c0008a1d6e7
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831318"
---
# <a name="traceroute-table"></a><span data-ttu-id="9fa48-104">TraceRoute 表格</span><span class="sxs-lookup"><span data-stu-id="9fa48-104">TraceRoute table</span></span>
 
<span data-ttu-id="9fa48-105">TraceRoute 表格包含來自呼叫的路由資訊。</span><span class="sxs-lookup"><span data-stu-id="9fa48-105">The TraceRoute table contains routing information from calls.</span></span> <span data-ttu-id="9fa48-106">此表格已引進 Microsoft Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="9fa48-106">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="9fa48-107">**欄**</span><span class="sxs-lookup"><span data-stu-id="9fa48-107">**Column**</span></span>|<span data-ttu-id="9fa48-108">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="9fa48-108">**Data Type**</span></span>|<span data-ttu-id="9fa48-109">**索引鍵/索引**</span><span class="sxs-lookup"><span data-stu-id="9fa48-109">**Key/Index**</span></span>|<span data-ttu-id="9fa48-110">**詳細資料**</span><span class="sxs-lookup"><span data-stu-id="9fa48-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="9fa48-111">**ConferenceDateTime**</span><span class="sxs-lookup"><span data-stu-id="9fa48-111">**ConferenceDateTime**</span></span> <br/> |<span data-ttu-id="9fa48-112">datetime</span><span class="sxs-lookup"><span data-stu-id="9fa48-112">datetime</span></span>  <br/> |<span data-ttu-id="9fa48-113">主要，外部</span><span class="sxs-lookup"><span data-stu-id="9fa48-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="9fa48-114">通話的開始日期與時間。</span><span class="sxs-lookup"><span data-stu-id="9fa48-114">Date and time that the call began.</span></span>  <br/> |
|<span data-ttu-id="9fa48-115">**SessionSeq**</span><span class="sxs-lookup"><span data-stu-id="9fa48-115">**SessionSeq**</span></span> <br/> |<span data-ttu-id="9fa48-116">int</span><span class="sxs-lookup"><span data-stu-id="9fa48-116">int</span></span>  <br/> |<span data-ttu-id="9fa48-117">主要、外部</span><span class="sxs-lookup"><span data-stu-id="9fa48-117">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="9fa48-118">唯一識別碼，用來區分可能在相同日期和同一時間開始的多個通話。</span><span class="sxs-lookup"><span data-stu-id="9fa48-118">Unique identifier used to distinguish between multiple calls that might have begun on the same date and at the same time.</span></span>  <br/> |
|<span data-ttu-id="9fa48-119">**MediaLineLabel**</span><span class="sxs-lookup"><span data-stu-id="9fa48-119">**MediaLineLabel**</span></span> <br/> |<span data-ttu-id="9fa48-120">Tinyint</span><span class="sxs-lookup"><span data-stu-id="9fa48-120">tinyint</span></span>  <br/> |<span data-ttu-id="9fa48-121">主要，外部</span><span class="sxs-lookup"><span data-stu-id="9fa48-121">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="9fa48-122">代表通話中使用的影片線條類型。</span><span class="sxs-lookup"><span data-stu-id="9fa48-122">Represents the type of video line used in the call.</span></span> <span data-ttu-id="9fa48-123">允許的值為：</span><span class="sxs-lookup"><span data-stu-id="9fa48-123">Allowed values are:</span></span>  <br/> <span data-ttu-id="9fa48-124">0-音訊</span><span class="sxs-lookup"><span data-stu-id="9fa48-124">0 - Audio</span></span>  <br/> <span data-ttu-id="9fa48-125">1-影片</span><span class="sxs-lookup"><span data-stu-id="9fa48-125">1 - Video</span></span>  <br/> <span data-ttu-id="9fa48-126">2-全景影片</span><span class="sxs-lookup"><span data-stu-id="9fa48-126">2 - Panoramic video</span></span>  <br/> <span data-ttu-id="9fa48-127">3-應用程式/桌面共用</span><span class="sxs-lookup"><span data-stu-id="9fa48-127">3 - Application/Desktop sharing</span></span>  <br/> |
|<span data-ttu-id="9fa48-128">**FromCaller**</span><span class="sxs-lookup"><span data-stu-id="9fa48-128">**FromCaller**</span></span> <br/> |<span data-ttu-id="9fa48-129">位</span><span class="sxs-lookup"><span data-stu-id="9fa48-129">bit</span></span>  <br/> |<span data-ttu-id="9fa48-130">主要</span><span class="sxs-lookup"><span data-stu-id="9fa48-130">Primary</span></span>  <br/> |<span data-ttu-id="9fa48-131">撥出電話的端點。</span><span class="sxs-lookup"><span data-stu-id="9fa48-131">Endpoint that placed the call.</span></span>  <br/> |
|<span data-ttu-id="9fa48-132">**跳**</span><span class="sxs-lookup"><span data-stu-id="9fa48-132">**Hop**</span></span> <br/> |<span data-ttu-id="9fa48-133">int</span><span class="sxs-lookup"><span data-stu-id="9fa48-133">int</span></span>  <br/> ||<span data-ttu-id="9fa48-134">網路躍點/</span><span class="sxs-lookup"><span data-stu-id="9fa48-134">Network hop/</span></span>  <br/> |
|<span data-ttu-id="9fa48-135">**IPAddressKey**</span><span class="sxs-lookup"><span data-stu-id="9fa48-135">**IPAddressKey**</span></span> <br/> |<span data-ttu-id="9fa48-136">int</span><span class="sxs-lookup"><span data-stu-id="9fa48-136">int</span></span>  <br/> |<span data-ttu-id="9fa48-137">Foreign</span><span class="sxs-lookup"><span data-stu-id="9fa48-137">Foreign</span></span>  <br/> |<span data-ttu-id="9fa48-138">IP 位址的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="9fa48-138">Unique identifier for the IP address.</span></span> <span data-ttu-id="9fa48-139">IP 位址資訊會儲存在 [IPAddress 表格](ipaddress.md)中。</span><span class="sxs-lookup"><span data-stu-id="9fa48-139">IP address information is stored in the [IPAddress table](ipaddress.md).</span></span>  <br/> |
|<span data-ttu-id="9fa48-140">**Rtt**</span><span class="sxs-lookup"><span data-stu-id="9fa48-140">**RTT**</span></span> <br/> |<span data-ttu-id="9fa48-141">int</span><span class="sxs-lookup"><span data-stu-id="9fa48-141">int</span></span>  <br/> ||<span data-ttu-id="9fa48-142">往返時間。</span><span class="sxs-lookup"><span data-stu-id="9fa48-142">Roundtrip time.</span></span> <span data-ttu-id="9fa48-143">「往返時間」會測量語音資料包到達目的地所需的時間長度，然後傳回收到的通知。</span><span class="sxs-lookup"><span data-stu-id="9fa48-143">The roundtrip time measures the amount of time it takes for a voice packet to reach its destination and then send back notification that it was received.</span></span>  <br/> |
   

