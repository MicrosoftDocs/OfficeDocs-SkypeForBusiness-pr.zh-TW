---
title: 在商務用 Skype 中規劃遠端呼叫控制
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 688a0328-1aa7-449f-b5f7-98c876112ed2
description: 遠端呼叫控制是舊版 Lync Server 中的功能，可讓使用者透過 Lync Server 控制其 PBX 電話。 在商務用 Skype Server 中，此功能已由「透過公司來電」取代。 在商務用 Skype Server 2015 的用戶端版本中，繼續進行遠端呼叫控制，用戶端將無法再進行設定，已將其移除供使用。
ms.openlocfilehash: 1ec6bb59b34505f17451be72baa44cdcc466c0d3
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51114609"
---
# <a name="plan-for-remote-call-control-in-skype-for-business"></a><span data-ttu-id="d70a1-105">在商務用 Skype 中規劃遠端呼叫控制</span><span class="sxs-lookup"><span data-stu-id="d70a1-105">Plan for remote call control in Skype for Business</span></span>
 
<span data-ttu-id="d70a1-106">遠端呼叫控制是舊版 Lync Server 中的功能，可讓使用者透過 Lync Server 控制其 PBX 電話。</span><span class="sxs-lookup"><span data-stu-id="d70a1-106">Remote call control was a feature in previous versions of Lync Server which enabled users to control their PBX phones with Lync Server.</span></span> <span data-ttu-id="d70a1-107">在商務用 Skype Server 中，此功能已由「透過公司來電」取代。</span><span class="sxs-lookup"><span data-stu-id="d70a1-107">In Skype for Business Server, this feature has been replaced with Call Via Work.</span></span>  <span data-ttu-id="d70a1-108">*在商務用 Skype Server 2015 的用戶端版本中，繼續進行遠端呼叫控制，用戶端將無法再進行設定，已將其移除供使用。*</span><span class="sxs-lookup"><span data-stu-id="d70a1-108">*In the client versions for Skype for Business Server 2015 and going forward, remote call control is no longer available to configure in the client and has been removed for use.*</span></span> 
  
 <span data-ttu-id="d70a1-109">遠端呼叫控制組織中執行 Lync Server 之前端伺服器的使用者，即使使用的是商務用 Skype 用戶端，仍然可以繼續使用遠端呼叫控制。</span><span class="sxs-lookup"><span data-stu-id="d70a1-109">Remote call control users in your organization who are homed on Front End Servers running Lync Server can continue to use remote call control, even if they are using a Skype for Business client.</span></span> <span data-ttu-id="d70a1-110">不過，對於位於商務用 Skype 伺服器上的任何使用者，都不支援遠端呼叫控制。</span><span class="sxs-lookup"><span data-stu-id="d70a1-110">However, for any users homed on Skype for Business Server, remote call control is not supported.</span></span> <span data-ttu-id="d70a1-111">請參閱下表的伺服器/用戶端組合，以及是否可以支援遠端呼叫控制或透過工作呼叫。</span><span class="sxs-lookup"><span data-stu-id="d70a1-111">See the following table for server/client combinations and whether they can support remote call control or Call via Work.</span></span>
  
||<span data-ttu-id="d70a1-112">**啟用 Skype 使用者介面的商務用 skype 用戶端**</span><span class="sxs-lookup"><span data-stu-id="d70a1-112">**Skype for Business Client With Skype UI enabled**</span></span>|<span data-ttu-id="d70a1-113">**已啟用 Lync 使用者的商務用 Skype 用戶端**</span><span class="sxs-lookup"><span data-stu-id="d70a1-113">**Skype for Business Client With Lync UI enabled**</span></span>|<span data-ttu-id="d70a1-114">**商務用 Skype 2016 用戶端**</span><span class="sxs-lookup"><span data-stu-id="d70a1-114">**Skype for Business 2016 Client**</span></span>|<span data-ttu-id="d70a1-115">**Lync 2013 用戶端**</span><span class="sxs-lookup"><span data-stu-id="d70a1-115">**Lync 2013 Client**</span></span>|<span data-ttu-id="d70a1-116">**Lync 2010 用戶端**</span><span class="sxs-lookup"><span data-stu-id="d70a1-116">**Lync 2010 Client**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
| <span data-ttu-id="d70a1-117">商務用 Skype Server</span><span class="sxs-lookup"><span data-stu-id="d70a1-117">Skype for Business Server</span></span> <br/> |<span data-ttu-id="d70a1-118">從公司通話</span><span class="sxs-lookup"><span data-stu-id="d70a1-118">Call via Work</span></span>  <br/> |<span data-ttu-id="d70a1-119">1</span><span class="sxs-lookup"><span data-stu-id="d70a1-119">1</span></span> <br/> |<span data-ttu-id="d70a1-120">從公司通話</span><span class="sxs-lookup"><span data-stu-id="d70a1-120">Call via Work</span></span>  <br/> |<span data-ttu-id="d70a1-121">1</span><span class="sxs-lookup"><span data-stu-id="d70a1-121">1</span></span> <br/> |<span data-ttu-id="d70a1-122">1</span><span class="sxs-lookup"><span data-stu-id="d70a1-122">1</span></span> <br/> |
| <span data-ttu-id="d70a1-123">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d70a1-123">Lync Server 2013</span></span> <br/> |<span data-ttu-id="d70a1-124">遠端呼叫控制</span><span class="sxs-lookup"><span data-stu-id="d70a1-124">Remote Call Control</span></span>  <br/> |<span data-ttu-id="d70a1-125">遠端呼叫控制</span><span class="sxs-lookup"><span data-stu-id="d70a1-125">Remote Call Control</span></span>  <br/> |<span data-ttu-id="d70a1-126">1</span><span class="sxs-lookup"><span data-stu-id="d70a1-126">1</span></span> <br/> |<span data-ttu-id="d70a1-127">遠端呼叫控制</span><span class="sxs-lookup"><span data-stu-id="d70a1-127">Remote Call Control</span></span>  <br/> |<span data-ttu-id="d70a1-128">遠端呼叫控制</span><span class="sxs-lookup"><span data-stu-id="d70a1-128">Remote Call Control</span></span>  <br/> |
| <span data-ttu-id="d70a1-129">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="d70a1-129">Lync Server 2010</span></span> <br/> |<span data-ttu-id="d70a1-130">遠端呼叫控制</span><span class="sxs-lookup"><span data-stu-id="d70a1-130">Remote Call Control</span></span>  <br/> |<span data-ttu-id="d70a1-131">遠端呼叫控制</span><span class="sxs-lookup"><span data-stu-id="d70a1-131">Remote Call Control</span></span>  <br/> |<span data-ttu-id="d70a1-132">1</span><span class="sxs-lookup"><span data-stu-id="d70a1-132">1</span></span> <br/> |<span data-ttu-id="d70a1-133">遠端呼叫控制</span><span class="sxs-lookup"><span data-stu-id="d70a1-133">Remote Call Control</span></span>  <br/> |<span data-ttu-id="d70a1-134">遠端呼叫控制</span><span class="sxs-lookup"><span data-stu-id="d70a1-134">Remote Call Control</span></span>  <br/> |
   
1. <span data-ttu-id="d70a1-135">這兩項功能都不受支援。</span><span class="sxs-lookup"><span data-stu-id="d70a1-135">Neither feature is supported.</span></span>
  
<span data-ttu-id="d70a1-136">如需詳細資訊，請參閱 Lync Server 2013 檔中的 [遠端呼叫控制](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-remote-call-control) 。</span><span class="sxs-lookup"><span data-stu-id="d70a1-136">For more information, see [Remote Call Control](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-remote-call-control) in the Lync Server 2013 documentation.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="d70a1-137">另請參閱</span><span class="sxs-lookup"><span data-stu-id="d70a1-137">See also</span></span>

[<span data-ttu-id="d70a1-138">透過商務用 Skype Server 中的工作規劃通話</span><span class="sxs-lookup"><span data-stu-id="d70a1-138">Plan for Call Via Work in Skype for Business Server</span></span>](call-via-work.md)
  
[<span data-ttu-id="d70a1-139">商務用 Skype 的桌面用戶端功能比較</span><span class="sxs-lookup"><span data-stu-id="d70a1-139">Desktop client feature comparison for Skype for Business</span></span>](../../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md)

[<span data-ttu-id="d70a1-140">進行商務用 Skype 通話，但使用您的 PBX 桌面電話進行音訊</span><span class="sxs-lookup"><span data-stu-id="d70a1-140">Make a Skype for Business call but use your PBX desk phone for audio</span></span>](https://support.office.com/article/Make-a-Skype-for-Business-call-but-use-your-PBX-desk-phone-for-audio-6a316c11-a05e-460c-b969-32ff0ad848e6)