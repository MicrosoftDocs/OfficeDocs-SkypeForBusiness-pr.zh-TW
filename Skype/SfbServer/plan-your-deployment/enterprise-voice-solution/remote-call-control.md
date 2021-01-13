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
ms.openlocfilehash: b48eeed656f5889d08fe892da7d7a6896f8a11c3
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813513"
---
# <a name="plan-for-remote-call-control-in-skype-for-business"></a><span data-ttu-id="15a00-105">在商務用 Skype 中規劃遠端呼叫控制</span><span class="sxs-lookup"><span data-stu-id="15a00-105">Plan for remote call control in Skype for Business</span></span>
 
<span data-ttu-id="15a00-106">遠端呼叫控制是舊版 Lync Server 中的功能，可讓使用者透過 Lync Server 控制其 PBX 電話。</span><span class="sxs-lookup"><span data-stu-id="15a00-106">Remote call control was a feature in previous versions of Lync Server which enabled users to control their PBX phones with Lync Server.</span></span> <span data-ttu-id="15a00-107">在商務用 Skype Server 中，此功能已由「透過公司來電」取代。</span><span class="sxs-lookup"><span data-stu-id="15a00-107">In Skype for Business Server, this feature has been replaced with Call Via Work.</span></span>  <span data-ttu-id="15a00-108">*在商務用 Skype Server 2015 的用戶端版本中，繼續進行遠端呼叫控制，用戶端將無法再進行設定，已將其移除供使用。*</span><span class="sxs-lookup"><span data-stu-id="15a00-108">*In the client versions for Skype for Business Server 2015 and going forward, remote call control is no longer available to configure in the client and has been removed for use.*</span></span> 
  
 <span data-ttu-id="15a00-109">遠端呼叫控制組織中執行 Lync Server 之前端伺服器的使用者，即使使用的是商務用 Skype 用戶端，仍然可以繼續使用遠端呼叫控制。</span><span class="sxs-lookup"><span data-stu-id="15a00-109">Remote call control users in your organization who are homed on Front End Servers running Lync Server can continue to use remote call control, even if they are using a Skype for Business client.</span></span> <span data-ttu-id="15a00-110">不過，對於位於商務用 Skype 伺服器上的任何使用者，都不支援遠端呼叫控制。</span><span class="sxs-lookup"><span data-stu-id="15a00-110">However, for any users homed on Skype for Business Server, remote call control is not supported.</span></span> <span data-ttu-id="15a00-111">請參閱下表的伺服器/用戶端組合，以及是否可以支援遠端呼叫控制或透過工作呼叫。</span><span class="sxs-lookup"><span data-stu-id="15a00-111">See the following table for server/client combinations and whether they can support remote call control or Call via Work.</span></span>
  
||<span data-ttu-id="15a00-112">**啟用 Skype 使用者介面的商務用 skype 用戶端**</span><span class="sxs-lookup"><span data-stu-id="15a00-112">**Skype for Business Client With Skype UI enabled**</span></span>|<span data-ttu-id="15a00-113">**已啟用 Lync 使用者的商務用 Skype 用戶端**</span><span class="sxs-lookup"><span data-stu-id="15a00-113">**Skype for Business Client With Lync UI enabled**</span></span>|<span data-ttu-id="15a00-114">**商務用 Skype 2016 用戶端**</span><span class="sxs-lookup"><span data-stu-id="15a00-114">**Skype for Business 2016 Client**</span></span>|<span data-ttu-id="15a00-115">**Lync 2013 用戶端**</span><span class="sxs-lookup"><span data-stu-id="15a00-115">**Lync 2013 Client**</span></span>|<span data-ttu-id="15a00-116">**Lync 2010 用戶端**</span><span class="sxs-lookup"><span data-stu-id="15a00-116">**Lync 2010 Client**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
| <span data-ttu-id="15a00-117">商務用 Skype Server</span><span class="sxs-lookup"><span data-stu-id="15a00-117">Skype for Business Server</span></span> <br/> |<span data-ttu-id="15a00-118">從公司通話</span><span class="sxs-lookup"><span data-stu-id="15a00-118">Call via Work</span></span>  <br/> |<span data-ttu-id="15a00-119">1 </span><span class="sxs-lookup"><span data-stu-id="15a00-119">1</span></span> <br/> |<span data-ttu-id="15a00-120">從公司通話</span><span class="sxs-lookup"><span data-stu-id="15a00-120">Call via Work</span></span>  <br/> |<span data-ttu-id="15a00-121">1 </span><span class="sxs-lookup"><span data-stu-id="15a00-121">1</span></span> <br/> |<span data-ttu-id="15a00-122">1 </span><span class="sxs-lookup"><span data-stu-id="15a00-122">1</span></span> <br/> |
| <span data-ttu-id="15a00-123">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="15a00-123">Lync Server 2013</span></span> <br/> |<span data-ttu-id="15a00-124">遠端呼叫控制</span><span class="sxs-lookup"><span data-stu-id="15a00-124">Remote Call Control</span></span>  <br/> |<span data-ttu-id="15a00-125">遠端呼叫控制</span><span class="sxs-lookup"><span data-stu-id="15a00-125">Remote Call Control</span></span>  <br/> |<span data-ttu-id="15a00-126">1 </span><span class="sxs-lookup"><span data-stu-id="15a00-126">1</span></span> <br/> |<span data-ttu-id="15a00-127">遠端呼叫控制</span><span class="sxs-lookup"><span data-stu-id="15a00-127">Remote Call Control</span></span>  <br/> |<span data-ttu-id="15a00-128">遠端呼叫控制</span><span class="sxs-lookup"><span data-stu-id="15a00-128">Remote Call Control</span></span>  <br/> |
| <span data-ttu-id="15a00-129">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="15a00-129">Lync Server 2010</span></span> <br/> |<span data-ttu-id="15a00-130">遠端呼叫控制</span><span class="sxs-lookup"><span data-stu-id="15a00-130">Remote Call Control</span></span>  <br/> |<span data-ttu-id="15a00-131">遠端呼叫控制</span><span class="sxs-lookup"><span data-stu-id="15a00-131">Remote Call Control</span></span>  <br/> |<span data-ttu-id="15a00-132">1 </span><span class="sxs-lookup"><span data-stu-id="15a00-132">1</span></span> <br/> |<span data-ttu-id="15a00-133">遠端呼叫控制</span><span class="sxs-lookup"><span data-stu-id="15a00-133">Remote Call Control</span></span>  <br/> |<span data-ttu-id="15a00-134">遠端呼叫控制</span><span class="sxs-lookup"><span data-stu-id="15a00-134">Remote Call Control</span></span>  <br/> |
   
1. <span data-ttu-id="15a00-135">這兩項功能都不受支援。</span><span class="sxs-lookup"><span data-stu-id="15a00-135">Neither feature is supported.</span></span>
  
<span data-ttu-id="15a00-136">如需詳細資訊，請參閱 Lync Server 2013 檔中的 [遠端呼叫控制](https://go.microsoft.com/fwlink/p/?LinkId=530208) 。</span><span class="sxs-lookup"><span data-stu-id="15a00-136">For more information, see [Remote Call Control](https://go.microsoft.com/fwlink/p/?LinkId=530208) in the Lync Server 2013 documentation.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="15a00-137">另請參閱</span><span class="sxs-lookup"><span data-stu-id="15a00-137">See also</span></span>

[<span data-ttu-id="15a00-138">透過商務用 Skype Server 中的工作規劃通話</span><span class="sxs-lookup"><span data-stu-id="15a00-138">Plan for Call Via Work in Skype for Business Server</span></span>](call-via-work.md)
  
[<span data-ttu-id="15a00-139">商務用 Skype 的桌面用戶端功能比較</span><span class="sxs-lookup"><span data-stu-id="15a00-139">Desktop client feature comparison for Skype for Business</span></span>](../../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md)

[<span data-ttu-id="15a00-140">進行商務用 Skype 通話，但使用您的 PBX 桌面電話進行音訊</span><span class="sxs-lookup"><span data-stu-id="15a00-140">Make a Skype for Business call but use your PBX desk phone for audio</span></span>](https://support.office.com/article/Make-a-Skype-for-Business-call-but-use-your-PBX-desk-phone-for-audio-6a316c11-a05e-460c-b969-32ff0ad848e6)

