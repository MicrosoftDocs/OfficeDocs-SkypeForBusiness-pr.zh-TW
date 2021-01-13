---
title: 商務用 Skype Server 2019 中已被取代的功能
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: overview
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: 摘要：這些功能已從商務用 Skype Server 2019 中移除。
ms.openlocfilehash: 5c5914493d7e2f4da4fd72d6acf7ff2b979d8e88
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49808723"
---
# <a name="whats-deprecated-from-skype-for-business-server-2019"></a><span data-ttu-id="4234a-103">商務用 Skype Server 2019 中已被取代的功能</span><span class="sxs-lookup"><span data-stu-id="4234a-103">What's deprecated from Skype for Business Server 2019</span></span>

<span data-ttu-id="4234a-104">深入瞭解商務用 Skype Server 2019 中已被取代的功能。</span><span class="sxs-lookup"><span data-stu-id="4234a-104">Learn about the features and functionality that are deprecated in Skype for Business Server 2019.</span></span> <span data-ttu-id="4234a-105">如需商務用 Skype Server 2019 中新功能的相關資訊，請參閱 [商務用 Skype server 2019](whats-new.md)。</span><span class="sxs-lookup"><span data-stu-id="4234a-105">For information about new features in Skype for Business Server 2019, see [What's in Skype for Business Server 2019](whats-new.md).</span></span>

<span data-ttu-id="4234a-106">商務用 Skype Server 2019 中包含一些已加重的功能，與舊版產品的相容性。</span><span class="sxs-lookup"><span data-stu-id="4234a-106">Some de-emphasized features are included in Skype for Business Server 2019 for compatibility with previous product versions.</span></span>

## <a name="features-deprecated-in-skype-for-business-server-2019"></a><span data-ttu-id="4234a-107">商務用 Skype Server 2019 中已被取代的功能</span><span class="sxs-lookup"><span data-stu-id="4234a-107">Features deprecated in Skype for Business Server 2019</span></span> 

    The following features and functionality have been deprecated in Skype for Business Server 2019.

### <a name="xmpp-gateways-for-skype-for-business-server"></a><span data-ttu-id="4234a-108">商務用 Skype Server 的 XMPP 閘道</span><span class="sxs-lookup"><span data-stu-id="4234a-108">XMPP Gateways for Skype for Business Server</span></span>

<span data-ttu-id="4234a-109">商務用 Skype Server 2015 及其前置任務可讓您設定可延伸的訊息和顯示狀態通訊協定 (XMPP Edge Server 上的) proxy，以及前端伺服器或前端集區上的 XMPP 閘道。</span><span class="sxs-lookup"><span data-stu-id="4234a-109">Skype for Business Server 2015 and its predecessors allowed you to configure an Extensible Messaging and Presence Protocol (XMPP) proxy on the Edge Server and an XMPP Gateway on the Front End Server or Front End pool.</span></span> <span data-ttu-id="4234a-110">商務用 Skype Server 2019 已不再提供此功能。</span><span class="sxs-lookup"><span data-stu-id="4234a-110">This functionality is no longer available in Skype for Business Server 2019.</span></span>

### <a name="persistent-chat-for-skype-for-business-server"></a><span data-ttu-id="4234a-111">商務用 Skype Server 的持續聊天</span><span class="sxs-lookup"><span data-stu-id="4234a-111">Persistent Chat for Skype for Business Server</span></span>

<span data-ttu-id="4234a-112">Persistent Chat Server 是一種選用角色，可讓您組織中的多位使用者參與隨時間持續的聊天室交談。</span><span class="sxs-lookup"><span data-stu-id="4234a-112">Persistent Chat Server is an optional role that lets multiple users in your organization participate in chat room conversations that persist over time.</span></span> <span data-ttu-id="4234a-113">無法使用商務用 Skype Server 2019 部署持續性聊天。</span><span class="sxs-lookup"><span data-stu-id="4234a-113">Persistent chat can't be deployed with Skype for Business Server 2019.</span></span> <span data-ttu-id="4234a-114">此伺服器角色會從拓撲產生器和程式碼中移除。</span><span class="sxs-lookup"><span data-stu-id="4234a-114">This server role is removed from Topology Builder, as well as from the code.</span></span> 

<span data-ttu-id="4234a-115">小組中提供相同的功能。</span><span class="sxs-lookup"><span data-stu-id="4234a-115">The same functionality is available in Teams.</span></span> <span data-ttu-id="4234a-116">如需詳細資訊，請參閱 [Microsoft 團隊升級快速](/microsoftteams/upgrade-start-here)入門。</span><span class="sxs-lookup"><span data-stu-id="4234a-116">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span>

### <a name="sql-mirroring-for-skype-for-business-server"></a><span data-ttu-id="4234a-117">商務用 Skype Server 的 SQL 鏡像</span><span class="sxs-lookup"><span data-stu-id="4234a-117">SQL Mirroring for Skype for Business Server</span></span>

<span data-ttu-id="4234a-118">無法使用商務用 Skype Server 2019 部署 SQL 鏡像。</span><span class="sxs-lookup"><span data-stu-id="4234a-118">SQL Mirroring can't be deployed with Skype for Business Server 2019.</span></span> <span data-ttu-id="4234a-119">仍支援其他提供高可用性和嚴重損壞修復的選項，因此您應從這些選項中加以選擇。</span><span class="sxs-lookup"><span data-stu-id="4234a-119">Other options for providing High Availability and Disaster Recovery are still supported and you should choose from among them.</span></span> <span data-ttu-id="4234a-120">請參閱 [規劃商務用 Skype Server 中的高可用性和嚴重損壞修復](../SfbServer/plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md) ，以查看選項。</span><span class="sxs-lookup"><span data-stu-id="4234a-120">See [Plan for high availability and disaster recovery in Skype for Business Server](../SfbServer/plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md) to review the options.</span></span>

### <a name="in-place-upgrades"></a><span data-ttu-id="4234a-121">就地升級</span><span class="sxs-lookup"><span data-stu-id="4234a-121">In-place upgrades</span></span> 

<span data-ttu-id="4234a-122">您可以在商務用 Skype 2015 Server 中取得就地升級，但在商務用 Skype Server 2019 中已不再支援就地升級。</span><span class="sxs-lookup"><span data-stu-id="4234a-122">In-place upgrades were available in Skype for Business Server 2015 but are no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="4234a-123">支援並排升級和 coexistance，請參閱 [遷移至商務用 Skype Server 2019](migration/migration-to-skype-for-business-server-2019.md) 以取得詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="4234a-123">Side by side upgrade and coexistance is supported, see [Migration to Skype for Business Server 2019](migration/migration-to-skype-for-business-server-2019.md) for more information.</span></span>

### <a name="mobility-service-mcx"></a><span data-ttu-id="4234a-124">行動服務 (Mcx) </span><span class="sxs-lookup"><span data-stu-id="4234a-124">Mobility Service (Mcx)</span></span>

<span data-ttu-id="4234a-125">商務用 Skype Server 2019 不再提供舊版行動用戶端所使用的行動服務支援。</span><span class="sxs-lookup"><span data-stu-id="4234a-125">Mobility Service support used by legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="4234a-126">這是先前在商務用 Skype Server 2015 中宣佈的宣告。</span><span class="sxs-lookup"><span data-stu-id="4234a-126">This was previously announced in Skype for Business Server 2015.</span></span>

<span data-ttu-id="4234a-127">所有目前的商務用 Skype mobile 用戶端都已經使用整合通訊網頁 API (UCWA) 以支援立即訊息 (IM) 、目前狀態及連絡人。</span><span class="sxs-lookup"><span data-stu-id="4234a-127">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="4234a-128">具有使用 Mcx 之舊版用戶端的使用者，必須升級至目前的用戶端。</span><span class="sxs-lookup"><span data-stu-id="4234a-128">Users with legacy clients using Mcx will need to upgrade to a current client.</span></span>

<span data-ttu-id="4234a-129">如需詳細資訊，請參閱為商務用 Skype 進行[商務用 Skype Server 和行動](../SfbServer/plan-your-deployment/mobility.md)[用戶端功能比較](../SfbServer/plan-your-deployment/clients-and-devices/mobile-feature-comparison.md)的計畫。</span><span class="sxs-lookup"><span data-stu-id="4234a-129">For more details, see [Plan for Mobility for Skype for Business Server](../SfbServer/plan-your-deployment/mobility.md) and [Mobile client feature comparison for Skype for Business](../SfbServer/plan-your-deployment/clients-and-devices/mobile-feature-comparison.md).</span></span>

## <a name="tools"></a><span data-ttu-id="4234a-130">工具</span><span class="sxs-lookup"><span data-stu-id="4234a-130">Tools</span></span>

<span data-ttu-id="4234a-131">下列工具在初次發行商務用 Skype Server 2019 時不可使用：</span><span class="sxs-lookup"><span data-stu-id="4234a-131">The following tools will not be available for use at the initial release of Skype for Business Server 2019:</span></span>

- <span data-ttu-id="4234a-132">商務用 Skype Server 容量規劃電腦</span><span class="sxs-lookup"><span data-stu-id="4234a-132">Skype for Business Server Capacity Planning Calculator</span></span>
- <span data-ttu-id="4234a-133">商務用 Skype Server 調試工具</span><span class="sxs-lookup"><span data-stu-id="4234a-133">Skype for Business Server Debugging Tools</span></span>
- <span data-ttu-id="4234a-134">商務用 Skype 伺服器資源套件工具 (將會移除某些工具) </span><span class="sxs-lookup"><span data-stu-id="4234a-134">Skype for Business Server Resource Kit Tools (some tools will be removed)</span></span>
    - <span data-ttu-id="4234a-135">呼叫 Call parkometer</span><span class="sxs-lookup"><span data-stu-id="4234a-135">Call Parkometer</span></span>
    - <span data-ttu-id="4234a-136">查閱使用者主控台</span><span class="sxs-lookup"><span data-stu-id="4234a-136">Lookup user console</span></span>
    - <span data-ttu-id="4234a-137">未指派號碼宣告遷移</span><span class="sxs-lookup"><span data-stu-id="4234a-137">Unassigned number Announcement Migration</span></span>

<span data-ttu-id="4234a-138">商務用 Skype Server 2019 不支援下列工具：</span><span class="sxs-lookup"><span data-stu-id="4234a-138">The following tools are not supported with Skype for Business Server 2019:</span></span>

- <span data-ttu-id="4234a-139">通話品質方法 (，但未呼叫品質儀表板) </span><span class="sxs-lookup"><span data-stu-id="4234a-139">Call Quality Methodology (but not Call Quality Dashboard)</span></span>
- <span data-ttu-id="4234a-140">Microsoft 通話品質方法計分卡，v 1。5</span><span class="sxs-lookup"><span data-stu-id="4234a-140">Microsoft Call Quality Methodology Scorecard, v1.5</span></span>
- <span data-ttu-id="4234a-141">商務用 Skype Server 2015 規劃工具</span><span class="sxs-lookup"><span data-stu-id="4234a-141">Skype for Business Server 2015 Planning Tool</span></span>
- <span data-ttu-id="4234a-142">商務用 Skype Server 2015 應力和效能工具</span><span class="sxs-lookup"><span data-stu-id="4234a-142">Skype for Business Server 2015 Stress and Performance Tool</span></span>

### <a name="see-also"></a><span data-ttu-id="4234a-143">另請參閱</span><span class="sxs-lookup"><span data-stu-id="4234a-143">See also</span></span>

[<span data-ttu-id="4234a-144">商務用 Skype Server 2019 的新功能</span><span class="sxs-lookup"><span data-stu-id="4234a-144">What's new in Skype for Business Server 2019</span></span>](whats-new.md)

[<span data-ttu-id="4234a-145">移轉 XMPP 同盟</span><span class="sxs-lookup"><span data-stu-id="4234a-145">Migrating XMPP federation</span></span>](migration/migrating-xmpp-federation.md)
