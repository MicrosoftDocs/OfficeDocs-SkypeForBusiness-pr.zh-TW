---
title: 在商務用 Skype 中規劃遠端通話控制
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 688a0328-1aa7-449f-b5f7-98c876112ed2
description: '[遠端通話控制] 是舊版 Lync Server 中的功能, 可讓使用者使用 Lync Server 控制其 PBX 手機。 在商務用 Skype Server 中, 此功能已由 [透過工作通話] 取代。 在商務用 Skype Server 2015 的用戶端版本中, 繼續進行, 用戶端的遠端通話控制已不再提供, 且已移除供使用。'
ms.openlocfilehash: e98bcbd7e1feb91b31994d2ece2770c911547882
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36187573"
---
# <a name="plan-for-remote-call-control-in-skype-for-business"></a><span data-ttu-id="b1dc2-105">在商務用 Skype 中規劃遠端通話控制</span><span class="sxs-lookup"><span data-stu-id="b1dc2-105">Plan for remote call control in Skype for Business</span></span>
 
<span data-ttu-id="b1dc2-106">[遠端通話控制] 是舊版 Lync Server 中的功能, 可讓使用者使用 Lync Server 控制其 PBX 手機。</span><span class="sxs-lookup"><span data-stu-id="b1dc2-106">Remote call control was a feature in previous versions of Lync Server which enabled users to control their PBX phones with Lync Server.</span></span> <span data-ttu-id="b1dc2-107">在商務用 Skype Server 中, 此功能已由 [透過工作通話] 取代。</span><span class="sxs-lookup"><span data-stu-id="b1dc2-107">In Skype for Business Server, this feature has been replaced with Call Via Work.</span></span>  <span data-ttu-id="b1dc2-108">*在商務用 Skype Server 2015 的用戶端版本中, 繼續進行, 用戶端的遠端通話控制已不再提供, 且已移除供使用。*</span><span class="sxs-lookup"><span data-stu-id="b1dc2-108">*In the client versions for Skype for Business Server 2015 and going forward, remote call control is no longer available to configure in the client and has been removed for use.*</span></span> 
  
 <span data-ttu-id="b1dc2-109">如果您組織中的遠端通話控制使用者是駐留在執行 Lync Server 的前端伺服器上, 即使他們使用的是商務用 Skype 用戶端, 也可以繼續使用遠端通話控制。</span><span class="sxs-lookup"><span data-stu-id="b1dc2-109">Remote call control users in your organization who are homed on Front End Servers running Lync Server can continue to use remote call control, even if they are using a Skype for Business client.</span></span> <span data-ttu-id="b1dc2-110">不過, 任何駐留在商務用 Skype Server 上的使用者, 都不支援遠端通話控制。</span><span class="sxs-lookup"><span data-stu-id="b1dc2-110">However, for any users homed on Skype for Business Server, remote call control is not supported.</span></span> <span data-ttu-id="b1dc2-111">請參閱下表以取得伺服器/用戶端組合, 以及他們是否能支援遠端通話控制或透過工作通話。</span><span class="sxs-lookup"><span data-stu-id="b1dc2-111">See the following table for server/client combinations and whether they can support remote call control or Call via Work.</span></span>
  
||<span data-ttu-id="b1dc2-112">**已啟用 Skype UI 的商務用 skype 用戶端**</span><span class="sxs-lookup"><span data-stu-id="b1dc2-112">**Skype for Business Client With Skype UI enabled**</span></span>|<span data-ttu-id="b1dc2-113">**已啟用 Lync UI 的商務用 Skype 用戶端**</span><span class="sxs-lookup"><span data-stu-id="b1dc2-113">**Skype for Business Client With Lync UI enabled**</span></span>|<span data-ttu-id="b1dc2-114">**商務用 Skype 2016 用戶端**</span><span class="sxs-lookup"><span data-stu-id="b1dc2-114">**Skype for Business 2016 Client**</span></span>|<span data-ttu-id="b1dc2-115">**Lync 2013 用戶端**</span><span class="sxs-lookup"><span data-stu-id="b1dc2-115">**Lync 2013 Client**</span></span>|<span data-ttu-id="b1dc2-116">**Lync 2010 用戶端**</span><span class="sxs-lookup"><span data-stu-id="b1dc2-116">**Lync 2010 Client**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
| <span data-ttu-id="b1dc2-117">商務用 Skype 伺服器</span><span class="sxs-lookup"><span data-stu-id="b1dc2-117">Skype for Business Server</span></span> <br/> |<span data-ttu-id="b1dc2-118">透過公司通話</span><span class="sxs-lookup"><span data-stu-id="b1dc2-118">Call via Work</span></span>  <br/> |<span data-ttu-id="b1dc2-119">sr-1</span><span class="sxs-lookup"><span data-stu-id="b1dc2-119">1</span></span> <br/> |<span data-ttu-id="b1dc2-120">透過公司通話</span><span class="sxs-lookup"><span data-stu-id="b1dc2-120">Call via Work</span></span>  <br/> |<span data-ttu-id="b1dc2-121">sr-1</span><span class="sxs-lookup"><span data-stu-id="b1dc2-121">1</span></span> <br/> |<span data-ttu-id="b1dc2-122">sr-1</span><span class="sxs-lookup"><span data-stu-id="b1dc2-122">1</span></span> <br/> |
| <span data-ttu-id="b1dc2-123">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b1dc2-123">Lync Server 2013</span></span> <br/> |<span data-ttu-id="b1dc2-124">遠端通話控制</span><span class="sxs-lookup"><span data-stu-id="b1dc2-124">Remote Call Control</span></span>  <br/> |<span data-ttu-id="b1dc2-125">遠端通話控制</span><span class="sxs-lookup"><span data-stu-id="b1dc2-125">Remote Call Control</span></span>  <br/> |<span data-ttu-id="b1dc2-126">sr-1</span><span class="sxs-lookup"><span data-stu-id="b1dc2-126">1</span></span> <br/> |<span data-ttu-id="b1dc2-127">遠端通話控制</span><span class="sxs-lookup"><span data-stu-id="b1dc2-127">Remote Call Control</span></span>  <br/> |<span data-ttu-id="b1dc2-128">遠端通話控制</span><span class="sxs-lookup"><span data-stu-id="b1dc2-128">Remote Call Control</span></span>  <br/> |
| <span data-ttu-id="b1dc2-129">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="b1dc2-129">Lync Server 2010</span></span> <br/> |<span data-ttu-id="b1dc2-130">遠端通話控制</span><span class="sxs-lookup"><span data-stu-id="b1dc2-130">Remote Call Control</span></span>  <br/> |<span data-ttu-id="b1dc2-131">遠端通話控制</span><span class="sxs-lookup"><span data-stu-id="b1dc2-131">Remote Call Control</span></span>  <br/> |<span data-ttu-id="b1dc2-132">sr-1</span><span class="sxs-lookup"><span data-stu-id="b1dc2-132">1</span></span> <br/> |<span data-ttu-id="b1dc2-133">遠端通話控制</span><span class="sxs-lookup"><span data-stu-id="b1dc2-133">Remote Call Control</span></span>  <br/> |<span data-ttu-id="b1dc2-134">遠端通話控制</span><span class="sxs-lookup"><span data-stu-id="b1dc2-134">Remote Call Control</span></span>  <br/> |
   
1. <span data-ttu-id="b1dc2-135">這兩個功能都不受支援。</span><span class="sxs-lookup"><span data-stu-id="b1dc2-135">Neither feature is supported.</span></span>
  
<span data-ttu-id="b1dc2-136">如需詳細資訊, 請參閱 Lync Server 2013 檔中的[遠端通話控制](https://go.microsoft.com/fwlink/p/?LinkId=530208)。</span><span class="sxs-lookup"><span data-stu-id="b1dc2-136">For more information, see [Remote Call Control](https://go.microsoft.com/fwlink/p/?LinkId=530208) in the Lync Server 2013 documentation.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="b1dc2-137">另請參閱</span><span class="sxs-lookup"><span data-stu-id="b1dc2-137">See also</span></span>

[<span data-ttu-id="b1dc2-138">透過商務用 Skype Server 中的工作規劃通話</span><span class="sxs-lookup"><span data-stu-id="b1dc2-138">Plan for Call Via Work in Skype for Business Server</span></span>](call-via-work.md)
  
[<span data-ttu-id="b1dc2-139">商務用 Skype 的桌面用戶端功能比較</span><span class="sxs-lookup"><span data-stu-id="b1dc2-139">Desktop client feature comparison for Skype for Business</span></span>](../../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md)

[<span data-ttu-id="b1dc2-140">撥打商務用 Skype 電話, 但使用您的 PBX 電話進行音訊</span><span class="sxs-lookup"><span data-stu-id="b1dc2-140">Make a Skype for Business call but use your PBX desk phone for audio</span></span>](https://support.office.com/en-us/article/Make-a-Skype-for-Business-call-but-use-your-PBX-desk-phone-for-audio-6a316c11-a05e-460c-b969-32ff0ad848e6)

