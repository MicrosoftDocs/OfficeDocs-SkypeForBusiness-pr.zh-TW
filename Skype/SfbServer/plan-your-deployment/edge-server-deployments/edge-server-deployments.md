---
title: 在商務用 Skype Server 中規劃 Edge Server 部署
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
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 9cdc3e23-3f6a-4e4d-9e04-f038596b6700
description: 摘要：規劃商務用 Skype Server Edge 環境。 本主題將向您介紹 Edge 概念，讓您瞭解更深入的主題。
ms.openlocfilehash: 277e344448f5229d15addf965695f19ec2884649
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813803"
---
# <a name="plan-for-edge-server-deployments-in-skype-for-business-server"></a><span data-ttu-id="0f0e5-104">在商務用 Skype Server 中規劃 Edge Server 部署</span><span class="sxs-lookup"><span data-stu-id="0f0e5-104">Plan for Edge Server deployments in Skype for Business Server</span></span>
 
<span data-ttu-id="0f0e5-105">**摘要：** 規劃商務用 Skype Server Edge 環境。</span><span class="sxs-lookup"><span data-stu-id="0f0e5-105">**Summary:** Plan for your Skype for Business Server Edge environment.</span></span> <span data-ttu-id="0f0e5-106">本主題將向您介紹 Edge 概念，讓您瞭解更深入的主題。</span><span class="sxs-lookup"><span data-stu-id="0f0e5-106">This topic introduces you to Edge concepts and lets you get organized with our more in-depth topics.</span></span>
  
<span data-ttu-id="0f0e5-107">當您有在內部運作的商務用 Skype 伺服器環境時，您可能需要將 Edge Server 或 Edge 集區引入環境。</span><span class="sxs-lookup"><span data-stu-id="0f0e5-107">When you have a Skype for Business Server environment that's working well internally, the next step for you might be to introduce an Edge Server or an Edge pool to the environment.</span></span> <span data-ttu-id="0f0e5-108">如果您想讓商務用 Skype Server 所提供的服務供內部網路以外的人員使用，此角色會非常重要。</span><span class="sxs-lookup"><span data-stu-id="0f0e5-108">This role would be vital if you want the services provided by Skype for Business Server to be used by people who are outside your internal network.</span></span> <span data-ttu-id="0f0e5-109">這些可能包括：</span><span class="sxs-lookup"><span data-stu-id="0f0e5-109">These can potentially include:</span></span>
  
- <span data-ttu-id="0f0e5-110">遠端使用者：暫時或以不間斷的方式進行異地的員工。</span><span class="sxs-lookup"><span data-stu-id="0f0e5-110">Remote Users: Employees who are offsite, either temporarily or in an ongoing way.</span></span>
    
- <span data-ttu-id="0f0e5-111">同盟使用者：您的夥伴組織的員工。</span><span class="sxs-lookup"><span data-stu-id="0f0e5-111">Federated Users: Your partner organizations' employees.</span></span>
    
- <span data-ttu-id="0f0e5-112">行動使用者。</span><span class="sxs-lookup"><span data-stu-id="0f0e5-112">Mobile Users.</span></span>
    
- <span data-ttu-id="0f0e5-113">您想要邀請參加會議及簡報的潛在客戶、合作夥伴甚至匿名使用者。</span><span class="sxs-lookup"><span data-stu-id="0f0e5-113">Potential customers, partners and even anonymous users you want to invite to meetings and presentations.</span></span>
    
<span data-ttu-id="0f0e5-114">外部使用者存取權是指 Edge Server 所提供的內容，讓這一切都能做到。</span><span class="sxs-lookup"><span data-stu-id="0f0e5-114">External User Access, which is what Edge Servers provide, allow all this to happen.</span></span> <span data-ttu-id="0f0e5-115">您的內部使用者可以享用下列由商務用 Skype Server 部署所主控的服務：</span><span class="sxs-lookup"><span data-stu-id="0f0e5-115">Your internal users will be able to enjoy the following services that are hosted by your Skype for Business Server deployment:</span></span>
  
- <span data-ttu-id="0f0e5-116">通訊的 IM 和目前狀態：已授權的外部使用者可以加入 IM 交談和會議。</span><span class="sxs-lookup"><span data-stu-id="0f0e5-116">IM and presence for communication: Authorized external users can join in IM conversations and conferences.</span></span> <span data-ttu-id="0f0e5-117">使用者可以取得目前狀態資訊) 其他使用者 (的狀態資訊。</span><span class="sxs-lookup"><span data-stu-id="0f0e5-117">They can get presence information for other users (who get their presence info too).</span></span> <span data-ttu-id="0f0e5-118">如果您是使用公用 IM 提供者（即「完全對等」通訊），將無法執行多方會議。</span><span class="sxs-lookup"><span data-stu-id="0f0e5-118">You won't be able to do multiparty conferences if you're using a public IM provider, that's strictly peer-to-peer communication.</span></span> <span data-ttu-id="0f0e5-119">但同時支援 SIP 和 XMPP 通訊協定。</span><span class="sxs-lookup"><span data-stu-id="0f0e5-119">But both SIP and XMPP protocols are supported.</span></span>
    
- <span data-ttu-id="0f0e5-120">音訊/視頻 (A/V) 會議：已授權的外部使用者可以加入您的商務用 Skype Server 音訊和視訊會議。</span><span class="sxs-lookup"><span data-stu-id="0f0e5-120">Audio/video (A/V) conferencing: Authorized external users can participate in your Skype for Business Server audio and video conferences.</span></span>
    
- <span data-ttu-id="0f0e5-121">Web 會議：您授權的外部使用者可以參與商務用 Skype 會議。</span><span class="sxs-lookup"><span data-stu-id="0f0e5-121">Web conferencing: Your authorized external users can participate in your Skype for Business conferences.</span></span> <span data-ttu-id="0f0e5-122">如果您願意，也可以為遠端使用者、同盟使用者和匿名使用者啟用參與。</span><span class="sxs-lookup"><span data-stu-id="0f0e5-122">You can also enable participation for remote users, federated users, and anonymous users if you'd like.</span></span> <span data-ttu-id="0f0e5-123">公用 IM 使用者無法參與會議。</span><span class="sxs-lookup"><span data-stu-id="0f0e5-123">Public IM users can't participate in conferences.</span></span> <span data-ttu-id="0f0e5-124">還有一些選項可讓這些使用者參與應用程式和桌面共用，甚至可充當會議召集人或簡報者。</span><span class="sxs-lookup"><span data-stu-id="0f0e5-124">There are also options to let these users participate in application and desktop sharing, and even act as meeting organizers or presenters.</span></span>
    
<span data-ttu-id="0f0e5-125">支援行動裝置存取，其為企業語音。</span><span class="sxs-lookup"><span data-stu-id="0f0e5-125">Mobile device access is supported, as is Enterprise Voice.</span></span> <span data-ttu-id="0f0e5-126">如果您想要授與外部使用者的許可權，甚至匿名使用者也可以邀請外部使用者加入這些會議。</span><span class="sxs-lookup"><span data-stu-id="0f0e5-126">You can invite external users to those meetings you wish them to attend, even anonymous users, if you want to give permissions to them.</span></span>
  
<span data-ttu-id="0f0e5-127">如果這聽起來像是您的組織需要的專案，則規劃 Edge 環境將會是部署它的一個重要説明。</span><span class="sxs-lookup"><span data-stu-id="0f0e5-127">If this sounds like something your organization needs, then planning for an Edge environment's going to be a big help in deploying it.</span></span> <span data-ttu-id="0f0e5-128">為了進一步閱讀，我們有下列主題。</span><span class="sxs-lookup"><span data-stu-id="0f0e5-128">For further reading, we have the topics listed below.</span></span>

> [!NOTE]
> <span data-ttu-id="0f0e5-129">XMPP 閘道和 proxy 可用於商務用 Skype Server 2015，但在商務用 Skype Server 2019 中已不再支援。</span><span class="sxs-lookup"><span data-stu-id="0f0e5-129">XMPP Gateways and proxies are available in Skype for Business Server 2015 but are no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="0f0e5-130">如需詳細資訊，請參閱 [遷移 XMPP 同盟](../../../SfBServer2019/migration/migrating-xmpp-federation.md) 。</span><span class="sxs-lookup"><span data-stu-id="0f0e5-130">See [Migrating XMPP federation](../../../SfBServer2019/migration/migrating-xmpp-federation.md) for more information.</span></span> 
  
## <a name="planning-topics"></a><span data-ttu-id="0f0e5-131">規劃主題：</span><span class="sxs-lookup"><span data-stu-id="0f0e5-131">Planning topics:</span></span>

<span data-ttu-id="0f0e5-132">規劃文章包括：</span><span class="sxs-lookup"><span data-stu-id="0f0e5-132">The planning articles are:</span></span>
  
- [<span data-ttu-id="0f0e5-133">商務用 Skype Server 中的 Edge Server 系統需求2015</span><span class="sxs-lookup"><span data-stu-id="0f0e5-133">Edge Server system requirements in Skype for Business Server 2015</span></span>](system-requirements.md)
    
- [<span data-ttu-id="0f0e5-134">商務用 Skype 2015 Server 中的 Edge Server 環境需求</span><span class="sxs-lookup"><span data-stu-id="0f0e5-134">Edge Server environmental requirements in Skype for Business Server 2015</span></span>](edge-environmental-requirements.md)
    
- [<span data-ttu-id="0f0e5-135">商務用 Skype 2015 Server 中的 Edge Server 案例</span><span class="sxs-lookup"><span data-stu-id="0f0e5-135">Edge Server scenarios in Skype for Business Server 2015</span></span>](scenarios.md)
    

