---
title: VideoClientEvent 表格
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e8ab963b-fe1d-45b3-b9bd-66a5f44c1629
description: 每個記錄都包含視頻通話中某個端點的用戶端事件。 通常, 一個通話有兩筆記錄, 一個用於呼叫者, 另一個用於被叫方。
ms.openlocfilehash: b8e93206ea30622baa82adcec5ee9a80235521c5
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36192613"
---
# <a name="videoclientevent-table"></a><span data-ttu-id="0118f-104">VideoClientEvent 表格</span><span class="sxs-lookup"><span data-stu-id="0118f-104">VideoClientEvent table</span></span>
 
<span data-ttu-id="0118f-105">每個記錄都包含視頻通話中某個端點的用戶端事件。</span><span class="sxs-lookup"><span data-stu-id="0118f-105">Each record contains client event for one endpoint in a video call.</span></span> <span data-ttu-id="0118f-106">通常, 一個通話有兩筆記錄, 一個用於呼叫者, 另一個用於被叫方。</span><span class="sxs-lookup"><span data-stu-id="0118f-106">Usually, one call has two records, one for caller and one for callee.</span></span>
  
|<span data-ttu-id="0118f-107">**左欄**</span><span class="sxs-lookup"><span data-stu-id="0118f-107">**Column**</span></span>|<span data-ttu-id="0118f-108">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="0118f-108">**Data Type**</span></span>|<span data-ttu-id="0118f-109">**索引鍵/索引**</span><span class="sxs-lookup"><span data-stu-id="0118f-109">**Key/Index**</span></span>|<span data-ttu-id="0118f-110">**詳細資料**</span><span class="sxs-lookup"><span data-stu-id="0118f-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="0118f-111">**ConferenceDateTime**</span><span class="sxs-lookup"><span data-stu-id="0118f-111">**ConferenceDateTime**</span></span> <br/> |<span data-ttu-id="0118f-112">datetime</span><span class="sxs-lookup"><span data-stu-id="0118f-112">datetime</span></span>  <br/> |<span data-ttu-id="0118f-113">首選</span><span class="sxs-lookup"><span data-stu-id="0118f-113">Primary</span></span>  <br/> |<span data-ttu-id="0118f-114">從[MediaLine 資料表](medialine-0.md)中參照。</span><span class="sxs-lookup"><span data-stu-id="0118f-114">Referenced from the [MediaLine table](medialine-0.md).</span></span>  <br/> |
|<span data-ttu-id="0118f-115">**SessionSeq**</span><span class="sxs-lookup"><span data-stu-id="0118f-115">**SessionSeq**</span></span> <br/> |<span data-ttu-id="0118f-116">int</span><span class="sxs-lookup"><span data-stu-id="0118f-116">int</span></span>  <br/> |<span data-ttu-id="0118f-117">首選</span><span class="sxs-lookup"><span data-stu-id="0118f-117">Primary</span></span>  <br/> |<span data-ttu-id="0118f-118">從[MediaLine 資料表](medialine-0.md)中參照。</span><span class="sxs-lookup"><span data-stu-id="0118f-118">Referenced from the [MediaLine table](medialine-0.md).</span></span>  <br/> |
|<span data-ttu-id="0118f-119">**MediaLineLabel**</span><span class="sxs-lookup"><span data-stu-id="0118f-119">**MediaLineLabel**</span></span> <br/> |<span data-ttu-id="0118f-120">Tinyint</span><span class="sxs-lookup"><span data-stu-id="0118f-120">tinyint</span></span>  <br/> |<span data-ttu-id="0118f-121">首選</span><span class="sxs-lookup"><span data-stu-id="0118f-121">Primary</span></span>  <br/> |<span data-ttu-id="0118f-122">從[MediaLine 資料表](medialine-0.md)中參照。</span><span class="sxs-lookup"><span data-stu-id="0118f-122">Referenced from the [MediaLine table](medialine-0.md).</span></span>  <br/> |
|<span data-ttu-id="0118f-123">**FromCaller**</span><span class="sxs-lookup"><span data-stu-id="0118f-123">**FromCaller**</span></span> <br/> |<span data-ttu-id="0118f-124">稍微</span><span class="sxs-lookup"><span data-stu-id="0118f-124">bit</span></span>  <br/> |<span data-ttu-id="0118f-125">首選</span><span class="sxs-lookup"><span data-stu-id="0118f-125">Primary</span></span>  <br/> |<span data-ttu-id="0118f-126">0: 被方程式的資料</span><span class="sxs-lookup"><span data-stu-id="0118f-126">0: Callee's data</span></span>  <br/> <span data-ttu-id="0118f-127">1: 來電者的資料</span><span class="sxs-lookup"><span data-stu-id="0118f-127">1: Caller's data</span></span>  <br/> |
|<span data-ttu-id="0118f-128">**NetworkBandwidthLowEventRatio**</span><span class="sxs-lookup"><span data-stu-id="0118f-128">**NetworkBandwidthLowEventRatio**</span></span> <br/> || <br/> |<span data-ttu-id="0118f-129">會話針對「錯誤」狀態觸發 LowBandwidth 事件的百分比。</span><span class="sxs-lookup"><span data-stu-id="0118f-129">Percentage of session the LowBandwidth event was fired for 'Bad' state.</span></span> <span data-ttu-id="0118f-130">可用的頻寬不足以取得可接受的語音體驗。</span><span class="sxs-lookup"><span data-stu-id="0118f-130">The available bandwidth is insufficient for an acceptable voice experience.</span></span>  <br/> |
|<span data-ttu-id="0118f-131">**NetworkReceiveQualityEventRatio**</span><span class="sxs-lookup"><span data-stu-id="0118f-131">**NetworkReceiveQualityEventRatio**</span></span> <br/> || <br/> |<span data-ttu-id="0118f-132">會話針對「錯誤」狀態觸發 ReceiveSendQuality 事件的百分比。</span><span class="sxs-lookup"><span data-stu-id="0118f-132">Percentage of session the ReceiveSendQuality event was fired for 'Bad' state.</span></span>  <br/> <span data-ttu-id="0118f-133">在抖動或資料包遺失方面的網路品質很嚴重, 而且會影響接收的音訊品質。</span><span class="sxs-lookup"><span data-stu-id="0118f-133">Network quality in terms of jitter or packet loss is severe and impacts the quality of audio being received.</span></span>  <br/> |
   

