---
title: VideoClientEvent 表格
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
ms.assetid: e8ab963b-fe1d-45b3-b9bd-66a5f44c1629
description: 每個記錄在影片通話中包含一個端點的用戶端事件。 通常，一個呼叫有兩筆記錄，一個用於來電者，另一個用於呼叫者。
ms.openlocfilehash: bb4a9feca562bed7bdb0080e7f9181003952f5d4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821393"
---
# <a name="videoclientevent-table"></a><span data-ttu-id="667df-104">VideoClientEvent 表格</span><span class="sxs-lookup"><span data-stu-id="667df-104">VideoClientEvent table</span></span>
 
<span data-ttu-id="667df-105">每個記錄在影片通話中包含一個端點的用戶端事件。</span><span class="sxs-lookup"><span data-stu-id="667df-105">Each record contains client event for one endpoint in a video call.</span></span> <span data-ttu-id="667df-106">通常，一個呼叫有兩筆記錄，一個用於來電者，另一個用於呼叫者。</span><span class="sxs-lookup"><span data-stu-id="667df-106">Usually, one call has two records, one for caller and one for callee.</span></span>
  
|<span data-ttu-id="667df-107">**欄**</span><span class="sxs-lookup"><span data-stu-id="667df-107">**Column**</span></span>|<span data-ttu-id="667df-108">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="667df-108">**Data Type**</span></span>|<span data-ttu-id="667df-109">**索引鍵/索引**</span><span class="sxs-lookup"><span data-stu-id="667df-109">**Key/Index**</span></span>|<span data-ttu-id="667df-110">**詳細資料**</span><span class="sxs-lookup"><span data-stu-id="667df-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="667df-111">**ConferenceDateTime**</span><span class="sxs-lookup"><span data-stu-id="667df-111">**ConferenceDateTime**</span></span> <br/> |<span data-ttu-id="667df-112">datetime</span><span class="sxs-lookup"><span data-stu-id="667df-112">datetime</span></span>  <br/> |<span data-ttu-id="667df-113">主要</span><span class="sxs-lookup"><span data-stu-id="667df-113">Primary</span></span>  <br/> |<span data-ttu-id="667df-114">從 [MediaLine 表格](medialine-0.md)中參照。</span><span class="sxs-lookup"><span data-stu-id="667df-114">Referenced from the [MediaLine table](medialine-0.md).</span></span>  <br/> |
|<span data-ttu-id="667df-115">**SessionSeq**</span><span class="sxs-lookup"><span data-stu-id="667df-115">**SessionSeq**</span></span> <br/> |<span data-ttu-id="667df-116">int</span><span class="sxs-lookup"><span data-stu-id="667df-116">int</span></span>  <br/> |<span data-ttu-id="667df-117">主要</span><span class="sxs-lookup"><span data-stu-id="667df-117">Primary</span></span>  <br/> |<span data-ttu-id="667df-118">從 [MediaLine 表格](medialine-0.md)中參照。</span><span class="sxs-lookup"><span data-stu-id="667df-118">Referenced from the [MediaLine table](medialine-0.md).</span></span>  <br/> |
|<span data-ttu-id="667df-119">**MediaLineLabel**</span><span class="sxs-lookup"><span data-stu-id="667df-119">**MediaLineLabel**</span></span> <br/> |<span data-ttu-id="667df-120">Tinyint</span><span class="sxs-lookup"><span data-stu-id="667df-120">tinyint</span></span>  <br/> |<span data-ttu-id="667df-121">主要</span><span class="sxs-lookup"><span data-stu-id="667df-121">Primary</span></span>  <br/> |<span data-ttu-id="667df-122">從 [MediaLine 表格](medialine-0.md)中參照。</span><span class="sxs-lookup"><span data-stu-id="667df-122">Referenced from the [MediaLine table](medialine-0.md).</span></span>  <br/> |
|<span data-ttu-id="667df-123">**FromCaller**</span><span class="sxs-lookup"><span data-stu-id="667df-123">**FromCaller**</span></span> <br/> |<span data-ttu-id="667df-124">位</span><span class="sxs-lookup"><span data-stu-id="667df-124">bit</span></span>  <br/> |<span data-ttu-id="667df-125">主要</span><span class="sxs-lookup"><span data-stu-id="667df-125">Primary</span></span>  <br/> |<span data-ttu-id="667df-126">0：被呼叫者的資料</span><span class="sxs-lookup"><span data-stu-id="667df-126">0: Callee's data</span></span>  <br/> <span data-ttu-id="667df-127">1：來電者的資料</span><span class="sxs-lookup"><span data-stu-id="667df-127">1: Caller's data</span></span>  <br/> |
|<span data-ttu-id="667df-128">**NetworkBandwidthLowEventRatio**</span><span class="sxs-lookup"><span data-stu-id="667df-128">**NetworkBandwidthLowEventRatio**</span></span> <br/> || <br/> |<span data-ttu-id="667df-129">會話百分比 LowBandwidth 事件引發「不良」狀態。</span><span class="sxs-lookup"><span data-stu-id="667df-129">Percentage of session the LowBandwidth event was fired for 'Bad' state.</span></span> <span data-ttu-id="667df-130">可用的頻寬不足以取得可接受的語音體驗。</span><span class="sxs-lookup"><span data-stu-id="667df-130">The available bandwidth is insufficient for an acceptable voice experience.</span></span>  <br/> |
|<span data-ttu-id="667df-131">**NetworkReceiveQualityEventRatio**</span><span class="sxs-lookup"><span data-stu-id="667df-131">**NetworkReceiveQualityEventRatio**</span></span> <br/> || <br/> |<span data-ttu-id="667df-132">會話百分比已針對 ' 壞」狀態引發 ReceiveSendQuality 事件。</span><span class="sxs-lookup"><span data-stu-id="667df-132">Percentage of session the ReceiveSendQuality event was fired for 'Bad' state.</span></span>  <br/> <span data-ttu-id="667df-133">抖動或封包遺失方面的網路品質很嚴重，且會影響所接收的音訊品質。</span><span class="sxs-lookup"><span data-stu-id="667df-133">Network quality in terms of jitter or packet loss is severe and impacts the quality of audio being received.</span></span>  <br/> |
   

