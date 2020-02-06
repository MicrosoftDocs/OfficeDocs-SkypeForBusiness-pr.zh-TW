---
title: 商務用 Skype Server 2019 已棄用的專案
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
audience: ITPro
ms.topic: overview
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: 摘要：這些功能已從商務用 Skype Server 2019 中移除。
ms.openlocfilehash: f77ccecd0ab963c0707a7b1dc1d24083ed0c3729
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813981"
---
# <a name="whats-deprecated-from-skype-for-business-server-2019"></a><span data-ttu-id="3b597-103">商務用 Skype Server 2019 已棄用的專案</span><span class="sxs-lookup"><span data-stu-id="3b597-103">What's deprecated from Skype for Business Server 2019</span></span>

<span data-ttu-id="3b597-104">瞭解商務用 Skype Server 2019 中已過時的功能和功能。</span><span class="sxs-lookup"><span data-stu-id="3b597-104">Learn about the features and functionality that are deprecated in Skype for Business Server 2019.</span></span> <span data-ttu-id="3b597-105">如需商務用 Skype Server 2019 中新功能的相關資訊，請參閱[商務用 Skype server 2019 中的內容](whats-new.md)。</span><span class="sxs-lookup"><span data-stu-id="3b597-105">For information about new features in Skype for Business Server 2019, see [What's in Skype for Business Server 2019](whats-new.md).</span></span>

<span data-ttu-id="3b597-106">在商務用 Skype Server 2019 中，有一些更強調的功能，可與舊版產品相容。</span><span class="sxs-lookup"><span data-stu-id="3b597-106">Some de-emphasized features are included in Skype for Business Server 2019 for compatibility with previous product versions.</span></span>

## <a name="features-deprecated-in-skype-for-business-server-2019"></a><span data-ttu-id="3b597-107">商務用 Skype Server 2019 中已棄用的功能</span><span class="sxs-lookup"><span data-stu-id="3b597-107">Features deprecated in Skype for Business Server 2019</span></span> 

    The following features and functionality have been deprecated in Skype for Business Server 2019.

### <a name="xmpp-gateways-for-skype-for-business-server"></a><span data-ttu-id="3b597-108">商務用 Skype Server 的 XMPP 閘道</span><span class="sxs-lookup"><span data-stu-id="3b597-108">XMPP Gateways for Skype for Business Server</span></span>

<span data-ttu-id="3b597-109">商務用 Skype Server 2015 及其前置任務允許您在 Edge 伺服器上設定可擴展的訊息和目前狀態通訊協定（XMPP） proxy，以及前端伺服器或頂層端池中的 XMPP 閘道。</span><span class="sxs-lookup"><span data-stu-id="3b597-109">Skype for Business Server 2015 and its predecessors allowed you to configure an Extensible Messaging and Presence Protocol (XMPP) proxy on the Edge Server and an XMPP Gateway on the Front End Server or Front End pool.</span></span> <span data-ttu-id="3b597-110">商務用 Skype Server 2019 已不再提供此功能。</span><span class="sxs-lookup"><span data-stu-id="3b597-110">This functionality is no longer available in Skype for Business Server 2019.</span></span>

### <a name="persistent-chat-for-skype-for-business-server"></a><span data-ttu-id="3b597-111">商務用 Skype Server 的持續聊天</span><span class="sxs-lookup"><span data-stu-id="3b597-111">Persistent Chat for Skype for Business Server</span></span>

<span data-ttu-id="3b597-112">持續聊天伺服器是一個可讓貴組織中的多位使用者參與在一段時間內保留的聊天室交談的選擇性角色。</span><span class="sxs-lookup"><span data-stu-id="3b597-112">Persistent Chat Server is an optional role that lets multiple users in your organization participate in chat room conversations that persist over time.</span></span> <span data-ttu-id="3b597-113">無法使用商務用 Skype Server 2019 來部署持續聊天。</span><span class="sxs-lookup"><span data-stu-id="3b597-113">Persistent chat can't be deployed with Skype for Business Server 2019.</span></span> <span data-ttu-id="3b597-114">此伺服器角色已從拓撲建立器以及程式碼中移除。</span><span class="sxs-lookup"><span data-stu-id="3b597-114">This server role is removed from Topology Builder, as well as from the code.</span></span> 

<span data-ttu-id="3b597-115">團隊中提供了相同的功能。</span><span class="sxs-lookup"><span data-stu-id="3b597-115">The same functionality is available in Teams.</span></span> <span data-ttu-id="3b597-116">如需詳細資訊，請參閱[Microsoft 團隊升級快速](/microsoftteams/upgrade-start-here)入門。</span><span class="sxs-lookup"><span data-stu-id="3b597-116">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span>

### <a name="sql-mirroring-for-skype-for-business-server"></a><span data-ttu-id="3b597-117">商務用 Skype Server 的 SQL 鏡像</span><span class="sxs-lookup"><span data-stu-id="3b597-117">SQL Mirroring for Skype for Business Server</span></span>

<span data-ttu-id="3b597-118">無法使用商務用 Skype Server 2019 來部署 SQL 鏡像。</span><span class="sxs-lookup"><span data-stu-id="3b597-118">SQL Mirroring can't be deployed with Skype for Business Server 2019.</span></span> <span data-ttu-id="3b597-119">提供高可用性和災害復原的其他選項仍受到支援，而且您應該在其中加以選擇。</span><span class="sxs-lookup"><span data-stu-id="3b597-119">Other options for providing High Availability and Disaster Recovery are still supported and you should choose from among them.</span></span> <span data-ttu-id="3b597-120">請參閱[在商務用 Skype 伺服器中的高可用性和災難復原方案](../SfbServer/plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)，以查看選項。</span><span class="sxs-lookup"><span data-stu-id="3b597-120">See [Plan for high availability and disaster recovery in Skype for Business Server](../SfbServer/plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md) to review the options.</span></span>

### <a name="in-place-upgrades"></a><span data-ttu-id="3b597-121">就地升級</span><span class="sxs-lookup"><span data-stu-id="3b597-121">In-place upgrades</span></span> 

<span data-ttu-id="3b597-122">商務用 Skype Server 2015 提供就地升級，但商務用 Skype Server 2019 已不再支援。</span><span class="sxs-lookup"><span data-stu-id="3b597-122">In-place upgrades were available in Skype for Business Server 2015 but are no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="3b597-123">並行升級及 coexistance 是受支援的，請參閱[遷移至商務用 Skype Server 2019](migration/migration-to-skype-for-business-server-2019.md)以取得詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="3b597-123">Side by side upgrade and coexistance is supported, see [Migration to Skype for Business Server 2019](migration/migration-to-skype-for-business-server-2019.md) for more information.</span></span>

### <a name="mobility-service-mcx"></a><span data-ttu-id="3b597-124">行動服務（Mcx）</span><span class="sxs-lookup"><span data-stu-id="3b597-124">Mobility Service (Mcx)</span></span>

<span data-ttu-id="3b597-125">舊版行動用戶端使用的行動服務支援已不再提供給商務用 Skype Server 2019。</span><span class="sxs-lookup"><span data-stu-id="3b597-125">Mobility Service support used by legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="3b597-126">這是先前在商務用 Skype Server 2015 中宣告的。</span><span class="sxs-lookup"><span data-stu-id="3b597-126">This was previously announced in Skype for Business Server 2015.</span></span>

<span data-ttu-id="3b597-127">所有目前的商務用 Skype 行動用戶端都已使用整合通訊 Web API （UCWA）來支援立即訊息（IM）、目前狀態和連絡人。</span><span class="sxs-lookup"><span data-stu-id="3b597-127">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="3b597-128">使用 Mcx 的舊版用戶端的使用者將需要升級至目前的用戶端。</span><span class="sxs-lookup"><span data-stu-id="3b597-128">Users with legacy clients using Mcx will need to upgrade to a current client.</span></span>

<span data-ttu-id="3b597-129">如需詳細資訊，請參閱針對商務用 Skype 的[商務用 Skype Server 及行動](../SfbServer/plan-your-deployment/mobility.md)[用戶端功能比較](../SfbServer/plan-your-deployment/clients-and-devices/mobile-feature-comparison.md)規劃。</span><span class="sxs-lookup"><span data-stu-id="3b597-129">For more details, see [Plan for Mobility for Skype for Business Server](../SfbServer/plan-your-deployment/mobility.md) and [Mobile client feature comparison for Skype for Business](../SfbServer/plan-your-deployment/clients-and-devices/mobile-feature-comparison.md).</span></span>

## <a name="tools"></a><span data-ttu-id="3b597-130">工具箱</span><span class="sxs-lookup"><span data-stu-id="3b597-130">Tools</span></span>

<span data-ttu-id="3b597-131">在商務用 Skype Server 2019 初次發行時，將無法使用下列工具：</span><span class="sxs-lookup"><span data-stu-id="3b597-131">The following tools will not be available for use at the initial release of Skype for Business Server 2019:</span></span>

- <span data-ttu-id="3b597-132">商務用 Skype Server 容量規劃計算機</span><span class="sxs-lookup"><span data-stu-id="3b597-132">Skype for Business Server Capacity Planning Calculator</span></span>
- <span data-ttu-id="3b597-133">商務用 Skype Server 調試工具</span><span class="sxs-lookup"><span data-stu-id="3b597-133">Skype for Business Server Debugging Tools</span></span>
- <span data-ttu-id="3b597-134">商務用 Skype Server 資源套件工具（某些工具將會被移除）</span><span class="sxs-lookup"><span data-stu-id="3b597-134">Skype for Business Server Resource Kit Tools (some tools will be removed)</span></span>
    - <span data-ttu-id="3b597-135">呼叫 Parkometer</span><span class="sxs-lookup"><span data-stu-id="3b597-135">Call Parkometer</span></span>
    - <span data-ttu-id="3b597-136">查閱使用者主控台</span><span class="sxs-lookup"><span data-stu-id="3b597-136">Lookup user console</span></span>
    - <span data-ttu-id="3b597-137">取消指派的號碼宣告遷移</span><span class="sxs-lookup"><span data-stu-id="3b597-137">Unassigned number Announcement Migration</span></span>

<span data-ttu-id="3b597-138">商務用 Skype Server 2019 不支援下列工具：</span><span class="sxs-lookup"><span data-stu-id="3b597-138">The following tools are not supported with Skype for Business Server 2019:</span></span>

- <span data-ttu-id="3b597-139">通話品質方法（但不是通話品質儀表板）</span><span class="sxs-lookup"><span data-stu-id="3b597-139">Call Quality Methodology (but not Call Quality Dashboard)</span></span>
- <span data-ttu-id="3b597-140">Microsoft 通話品質方法計分卡，v 1。5</span><span class="sxs-lookup"><span data-stu-id="3b597-140">Microsoft Call Quality Methodology Scorecard, v1.5</span></span>
- <span data-ttu-id="3b597-141">使用規劃工具設計 Lync Server 2013 的拓撲</span><span class="sxs-lookup"><span data-stu-id="3b597-141">Skype for Business Server 2015 Planning Tool</span></span>
- <span data-ttu-id="3b597-142">商務用 Skype Server 2015 應力與效能工具</span><span class="sxs-lookup"><span data-stu-id="3b597-142">Skype for Business Server 2015 Stress and Performance Tool</span></span>

### <a name="see-also"></a><span data-ttu-id="3b597-143">另請參閱</span><span class="sxs-lookup"><span data-stu-id="3b597-143">See also</span></span>

[<span data-ttu-id="3b597-144">商務用 Skype Server 2019 的新功能</span><span class="sxs-lookup"><span data-stu-id="3b597-144">What's new in Skype for Business Server 2019</span></span>](whats-new.md)

[<span data-ttu-id="3b597-145">移轉 XMPP 同盟</span><span class="sxs-lookup"><span data-stu-id="3b597-145">Migrating XMPP federation</span></span>](migration/migrating-xmpp-federation.md)
