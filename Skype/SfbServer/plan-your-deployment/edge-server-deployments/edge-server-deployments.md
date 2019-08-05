---
title: 在商務用 Skype Server 中規劃 Edge 伺服器部署
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
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 9cdc3e23-3f6a-4e4d-9e04-f038596b6700
description: '摘要: 規劃商務用 Skype Server Edge 環境。 本主題將向您介紹邊緣概念, 並讓您以更深入的主題進行組織。'
ms.openlocfilehash: 536ab82ec6845c55a0ee067ad8c1a4f5d9b9e153
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36187813"
---
# <a name="plan-for-edge-server-deployments-in-skype-for-business-server"></a><span data-ttu-id="26c50-104">在商務用 Skype Server 中規劃 Edge 伺服器部署</span><span class="sxs-lookup"><span data-stu-id="26c50-104">Plan for Edge Server deployments in Skype for Business Server</span></span>
 
<span data-ttu-id="26c50-105">**摘要:** 規劃商務用 Skype Server Edge 環境。</span><span class="sxs-lookup"><span data-stu-id="26c50-105">**Summary:** Plan for your Skype for Business Server Edge environment.</span></span> <span data-ttu-id="26c50-106">本主題將向您介紹邊緣概念, 並讓您以更深入的主題進行組織。</span><span class="sxs-lookup"><span data-stu-id="26c50-106">This topic introduces you to Edge concepts and lets you get organized with our more in-depth topics.</span></span>
  
<span data-ttu-id="26c50-107">當您在內部使用商務用 Skype Server 環境時, 下一個步驟可能是將 Edge 伺服器或邊緣池引入環境。</span><span class="sxs-lookup"><span data-stu-id="26c50-107">When you have a Skype for Business Server environment that's working well internally, the next step for you might be to introduce an Edge Server or an Edge pool to the environment.</span></span> <span data-ttu-id="26c50-108">如果您想要將商務用 Skype 伺服器所提供的服務供內部網路以外的人員使用, 此角色將是至關重要的。</span><span class="sxs-lookup"><span data-stu-id="26c50-108">This role would be vital if you want the services provided by Skype for Business Server to be used by people who are outside your internal network.</span></span> <span data-ttu-id="26c50-109">這些可能包括:</span><span class="sxs-lookup"><span data-stu-id="26c50-109">These can potentially include:</span></span>
  
- <span data-ttu-id="26c50-110">遠端使用者: 暫時或以不間斷的方式進行非現場的員工。</span><span class="sxs-lookup"><span data-stu-id="26c50-110">Remote Users: Employees who are offsite, either temporarily or in an ongoing way.</span></span>
    
- <span data-ttu-id="26c50-111">聯盟使用者: 您的合作夥伴組織的員工。</span><span class="sxs-lookup"><span data-stu-id="26c50-111">Federated Users: Your partner organizations' employees.</span></span>
    
- <span data-ttu-id="26c50-112">行動使用者。</span><span class="sxs-lookup"><span data-stu-id="26c50-112">Mobile Users.</span></span>
    
- <span data-ttu-id="26c50-113">您想要邀請加入會議和簡報的潛在客戶、合作夥伴甚至匿名使用者。</span><span class="sxs-lookup"><span data-stu-id="26c50-113">Potential customers, partners and even anonymous users you want to invite to meetings and presentations.</span></span>
    
<span data-ttu-id="26c50-114">外部使用者存取權是指邊緣伺服器所提供的功能, 可讓所有這些都發生。</span><span class="sxs-lookup"><span data-stu-id="26c50-114">External User Access, which is what Edge Servers provide, allow all this to happen.</span></span> <span data-ttu-id="26c50-115">您的內部使用者將能享用由您的商務用 Skype Server 部署所託管的下列服務:</span><span class="sxs-lookup"><span data-stu-id="26c50-115">Your internal users will be able to enjoy the following services that are hosted by your Skype for Business Server deployment:</span></span>
  
- <span data-ttu-id="26c50-116">通訊的 IM 和目前狀態: 已授權的外部使用者可以在 IM 交談和會議中加入。</span><span class="sxs-lookup"><span data-stu-id="26c50-116">IM and presence for communication: Authorized external users can join in IM conversations and conferences.</span></span> <span data-ttu-id="26c50-117">他們可以取得其他使用者的目前狀態資訊 (也就是誰取得目前狀態資訊)。</span><span class="sxs-lookup"><span data-stu-id="26c50-117">They can get presence information for other users (who get their presence info too).</span></span> <span data-ttu-id="26c50-118">如果您使用的是公用 IM 提供者, 就不能執行多方會議, 那就是完全對等通訊。</span><span class="sxs-lookup"><span data-stu-id="26c50-118">You won't be able to do multiparty conferences if you're using a public IM provider, that's strictly peer-to-peer communication.</span></span> <span data-ttu-id="26c50-119">但支援 SIP 與 XMPP 通訊協定。</span><span class="sxs-lookup"><span data-stu-id="26c50-119">But both SIP and XMPP protocols are supported.</span></span>
    
- <span data-ttu-id="26c50-120">音訊/視頻 (A/V) 會議: 獲授權的外部使用者可以參與商務用 Skype Server 音訊與視訊會議。</span><span class="sxs-lookup"><span data-stu-id="26c50-120">Audio/video (A/V) conferencing: Authorized external users can participate in your Skype for Business Server audio and video conferences.</span></span>
    
- <span data-ttu-id="26c50-121">網路會議: 您的授權外部使用者可以參與您的商務用 Skype 會議。</span><span class="sxs-lookup"><span data-stu-id="26c50-121">Web conferencing: Your authorized external users can participate in your Skype for Business conferences.</span></span> <span data-ttu-id="26c50-122">如果您想要的話, 也可以為遠端使用者、同盟使用者及匿名使用者啟用參與。</span><span class="sxs-lookup"><span data-stu-id="26c50-122">You can also enable participation for remote users, federated users, and anonymous users if you'd like.</span></span> <span data-ttu-id="26c50-123">公用 IM 使用者無法參與會議。</span><span class="sxs-lookup"><span data-stu-id="26c50-123">Public IM users can't participate in conferences.</span></span> <span data-ttu-id="26c50-124">您也可以選擇讓這些使用者參與應用程式和桌面共用, 甚至充當會議召集人或簡報者。</span><span class="sxs-lookup"><span data-stu-id="26c50-124">There are also options to let these users participate in application and desktop sharing, and even act as meeting organizers or presenters.</span></span>
    
<span data-ttu-id="26c50-125">支援行動裝置存取, 就像企業版語音一樣。</span><span class="sxs-lookup"><span data-stu-id="26c50-125">Mobile device access is supported, as is Enterprise Voice.</span></span> <span data-ttu-id="26c50-126">您可以邀請外部使用者參加您想要他們加入的會議, 甚至是匿名使用者 (如果您想要賦予他們許可權)。</span><span class="sxs-lookup"><span data-stu-id="26c50-126">You can invite external users to those meetings you wish them to attend, even anonymous users, if you want to give permissions to them.</span></span>
  
<span data-ttu-id="26c50-127">如果這聽起來像是您組織所需的專案, 則規劃 Edge 環境將是部署它的一個大協助。</span><span class="sxs-lookup"><span data-stu-id="26c50-127">If this sounds like something your organization needs, then planning for an Edge environment's going to be a big help in deploying it.</span></span> <span data-ttu-id="26c50-128">如需進一步閱讀, 我們有下列主題。</span><span class="sxs-lookup"><span data-stu-id="26c50-128">For further reading, we have the topics listed below.</span></span>

> [!NOTE]
> <span data-ttu-id="26c50-129">XMPP 閘道和 proxy 可在商務用 Skype Server 2015 中使用, 但商務用 Skype Server 2019 已不再支援。</span><span class="sxs-lookup"><span data-stu-id="26c50-129">XMPP Gateways and proxies are available in Skype for Business Server 2015 but are no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="26c50-130">如需詳細資訊, 請參閱[遷移 XMPP 同盟](../../../SfBServer2019/migration/migrating-xmpp-federation.md)。</span><span class="sxs-lookup"><span data-stu-id="26c50-130">See [Migrating XMPP federation](../../../SfBServer2019/migration/migrating-xmpp-federation.md) for more information.</span></span> 
  
## <a name="planning-topics"></a><span data-ttu-id="26c50-131">規劃主題:</span><span class="sxs-lookup"><span data-stu-id="26c50-131">Planning topics:</span></span>

<span data-ttu-id="26c50-132">規劃文章包括:</span><span class="sxs-lookup"><span data-stu-id="26c50-132">The planning articles are:</span></span>
  
- [<span data-ttu-id="26c50-133">商務用 Skype Server 2015 中的 Edge 伺服器系統需求</span><span class="sxs-lookup"><span data-stu-id="26c50-133">Edge Server system requirements in Skype for Business Server 2015</span></span>](system-requirements.md)
    
- [<span data-ttu-id="26c50-134">商務用 Skype Server 2015 中的邊緣伺服器環境需求</span><span class="sxs-lookup"><span data-stu-id="26c50-134">Edge Server environmental requirements in Skype for Business Server 2015</span></span>](edge-environmental-requirements.md)
    
- [<span data-ttu-id="26c50-135">商務用 Skype Server 2015 中的邊緣伺服器案例</span><span class="sxs-lookup"><span data-stu-id="26c50-135">Edge Server scenarios in Skype for Business Server 2015</span></span>](scenarios.md)
    

