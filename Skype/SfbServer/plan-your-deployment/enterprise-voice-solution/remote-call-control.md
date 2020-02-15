---
title: 規劃商務用 Skype 中的遠端呼叫控制
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: 遠端呼叫控制已在舊版的 Lync Server 啟用使用者控制 PBX 電話與 Lync Server 的功能。 Skype for Business Server，此功能已取代呼叫透過工作。 中用於商務用 Skype Server 2015 及移轉寄、 遠端通話的用戶端版本控制不再是可在用戶端設定，並使用已移除。
ms.openlocfilehash: 788939c392b1d86d14590232c19979e664fa0c09
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/14/2020
ms.locfileid: "41982798"
---
# <a name="plan-for-remote-call-control-in-skype-for-business"></a><span data-ttu-id="cea4c-105">規劃商務用 Skype 中的遠端呼叫控制</span><span class="sxs-lookup"><span data-stu-id="cea4c-105">Plan for remote call control in Skype for Business</span></span>
 
<span data-ttu-id="cea4c-106">遠端呼叫控制已在舊版的 Lync Server 啟用使用者控制 PBX 電話與 Lync Server 的功能。</span><span class="sxs-lookup"><span data-stu-id="cea4c-106">Remote call control was a feature in previous versions of Lync Server which enabled users to control their PBX phones with Lync Server.</span></span> <span data-ttu-id="cea4c-107">Skype for Business Server，此功能已取代呼叫透過工作。</span><span class="sxs-lookup"><span data-stu-id="cea4c-107">In Skype for Business Server, this feature has been replaced with Call Via Work.</span></span>  <span data-ttu-id="cea4c-108">*中用於商務用 Skype Server 2015 及移轉寄、 遠端通話的用戶端版本控制不再是可在用戶端設定，並使用已移除。*</span><span class="sxs-lookup"><span data-stu-id="cea4c-108">*In the client versions for Skype for Business Server 2015 and going forward, remote call control is no longer available to configure in the client and has been removed for use.*</span></span> 
  
 <span data-ttu-id="cea4c-109">遠端呼叫控制您組織中的使用者位於前端伺服器執行 Lync Server 可以繼續使用遠端呼叫控制，即使它們使用 Skype 商務用戶端。</span><span class="sxs-lookup"><span data-stu-id="cea4c-109">Remote call control users in your organization who are homed on Front End Servers running Lync Server can continue to use remote call control, even if they are using a Skype for Business client.</span></span> <span data-ttu-id="cea4c-110">不過，任何使用者隸屬於 Skype for Business Server，如遠端呼叫控制不支援。</span><span class="sxs-lookup"><span data-stu-id="cea4c-110">However, for any users homed on Skype for Business Server, remote call control is not supported.</span></span> <span data-ttu-id="cea4c-111">請參閱下表中的伺服器/用戶端組合，以及是否可以支援遠端呼叫控制或通話從公司撥號。</span><span class="sxs-lookup"><span data-stu-id="cea4c-111">See the following table for server/client combinations and whether they can support remote call control or Call via Work.</span></span>
  
||<span data-ttu-id="cea4c-112">**商務用戶端與 Skype UI 啟用商務用 Skype**</span><span class="sxs-lookup"><span data-stu-id="cea4c-112">**Skype for Business Client With Skype UI enabled**</span></span>|<span data-ttu-id="cea4c-113">**商務用戶端與 Lync UI 啟用商務用 Skype**</span><span class="sxs-lookup"><span data-stu-id="cea4c-113">**Skype for Business Client With Lync UI enabled**</span></span>|<span data-ttu-id="cea4c-114">**Skype 商務版 2016年用戶端**</span><span class="sxs-lookup"><span data-stu-id="cea4c-114">**Skype for Business 2016 Client**</span></span>|<span data-ttu-id="cea4c-115">**Lync 2013 用戶端**</span><span class="sxs-lookup"><span data-stu-id="cea4c-115">**Lync 2013 Client**</span></span>|<span data-ttu-id="cea4c-116">**Lync 2010 用戶端**</span><span class="sxs-lookup"><span data-stu-id="cea4c-116">**Lync 2010 Client**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
| <span data-ttu-id="cea4c-117">商務用 Skype Server</span><span class="sxs-lookup"><span data-stu-id="cea4c-117">Skype for Business Server</span></span> <br/> |<span data-ttu-id="cea4c-118">呼叫從公司撥號</span><span class="sxs-lookup"><span data-stu-id="cea4c-118">Call via Work</span></span>  <br/> |<span data-ttu-id="cea4c-119">1 </span><span class="sxs-lookup"><span data-stu-id="cea4c-119">1</span></span> <br/> |<span data-ttu-id="cea4c-120">呼叫從公司撥號</span><span class="sxs-lookup"><span data-stu-id="cea4c-120">Call via Work</span></span>  <br/> |<span data-ttu-id="cea4c-121">1 </span><span class="sxs-lookup"><span data-stu-id="cea4c-121">1</span></span> <br/> |<span data-ttu-id="cea4c-122">1 </span><span class="sxs-lookup"><span data-stu-id="cea4c-122">1</span></span> <br/> |
| <span data-ttu-id="cea4c-123">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cea4c-123">Lync Server 2013</span></span> <br/> |<span data-ttu-id="cea4c-124">遠端呼叫控制</span><span class="sxs-lookup"><span data-stu-id="cea4c-124">Remote Call Control</span></span>  <br/> |<span data-ttu-id="cea4c-125">遠端呼叫控制</span><span class="sxs-lookup"><span data-stu-id="cea4c-125">Remote Call Control</span></span>  <br/> |<span data-ttu-id="cea4c-126">1 </span><span class="sxs-lookup"><span data-stu-id="cea4c-126">1</span></span> <br/> |<span data-ttu-id="cea4c-127">遠端呼叫控制</span><span class="sxs-lookup"><span data-stu-id="cea4c-127">Remote Call Control</span></span>  <br/> |<span data-ttu-id="cea4c-128">遠端呼叫控制</span><span class="sxs-lookup"><span data-stu-id="cea4c-128">Remote Call Control</span></span>  <br/> |
| <span data-ttu-id="cea4c-129">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="cea4c-129">Lync Server 2010</span></span> <br/> |<span data-ttu-id="cea4c-130">遠端呼叫控制</span><span class="sxs-lookup"><span data-stu-id="cea4c-130">Remote Call Control</span></span>  <br/> |<span data-ttu-id="cea4c-131">遠端呼叫控制</span><span class="sxs-lookup"><span data-stu-id="cea4c-131">Remote Call Control</span></span>  <br/> |<span data-ttu-id="cea4c-132">1 </span><span class="sxs-lookup"><span data-stu-id="cea4c-132">1</span></span> <br/> |<span data-ttu-id="cea4c-133">遠端呼叫控制</span><span class="sxs-lookup"><span data-stu-id="cea4c-133">Remote Call Control</span></span>  <br/> |<span data-ttu-id="cea4c-134">遠端呼叫控制</span><span class="sxs-lookup"><span data-stu-id="cea4c-134">Remote Call Control</span></span>  <br/> |
   
1. <span data-ttu-id="cea4c-135">支援這兩個功能。</span><span class="sxs-lookup"><span data-stu-id="cea4c-135">Neither feature is supported.</span></span>
  
<span data-ttu-id="cea4c-136">如需詳細資訊，請參閱 Lync Server 2013 文件中的[Remote Call Control](https://go.microsoft.com/fwlink/p/?LinkId=530208) 。</span><span class="sxs-lookup"><span data-stu-id="cea4c-136">For more information, see [Remote Call Control](https://go.microsoft.com/fwlink/p/?LinkId=530208) in the Lync Server 2013 documentation.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="cea4c-137">另請參閱</span><span class="sxs-lookup"><span data-stu-id="cea4c-137">See also</span></span>

[<span data-ttu-id="cea4c-138">計劃工時以 Skype for Business Server 透過呼叫</span><span class="sxs-lookup"><span data-stu-id="cea4c-138">Plan for Call Via Work in Skype for Business Server</span></span>](call-via-work.md)
  
[<span data-ttu-id="cea4c-139">商務用 skype 桌面用戶端功能比較</span><span class="sxs-lookup"><span data-stu-id="cea4c-139">Desktop client feature comparison for Skype for Business</span></span>](../../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md)

[<span data-ttu-id="cea4c-140">請 Skype for Business 通話，但您 PBX 桌上電話用於音訊</span><span class="sxs-lookup"><span data-stu-id="cea4c-140">Make a Skype for Business call but use your PBX desk phone for audio</span></span>](https://support.office.com/article/Make-a-Skype-for-Business-call-but-use-your-PBX-desk-phone-for-audio-6a316c11-a05e-460c-b969-32ff0ad848e6)

