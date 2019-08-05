---
title: 在商務用 Skype Server 中定義 E9-1-1 部署的範圍
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
ms.assetid: 2c572dfd-e901-471d-b5a0-18bc8d1d5328
description: 規劃商務用 Skype Server Enterprise Voice 中的 E9-1-1 部署所需的決策。
ms.openlocfilehash: 648713ce3474779a588d638e3e81272fbd62e2f0
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36187564"
---
# <a name="define-the-scope-of-the-e9-1-1-deployment-in-skype-for-business-server"></a><span data-ttu-id="5d722-103">在商務用 Skype Server 中定義 E9-1-1 部署的範圍</span><span class="sxs-lookup"><span data-stu-id="5d722-103">Define the scope of the E9-1-1 deployment in Skype for Business Server</span></span>

<span data-ttu-id="5d722-104">規劃商務用 Skype Server Enterprise Voice 中的 E9-1-1 部署所需的決策。</span><span class="sxs-lookup"><span data-stu-id="5d722-104">Decisions necessary for planning an E9-1-1 deployment in Skype for Business Server Enterprise Voice.</span></span>

<span data-ttu-id="5d722-105">在您設定 E9 的商務用 Skype-1-1 之前, 您必須先規劃 E9-1-1 部署。</span><span class="sxs-lookup"><span data-stu-id="5d722-105">Before you configure Skype for Business for E9-1-1, you need to plan your E9-1-1 deployment.</span></span> <span data-ttu-id="5d722-106">需要考慮的一些問題包括:</span><span class="sxs-lookup"><span data-stu-id="5d722-106">Some of the questions to consider include:</span></span>

 <span data-ttu-id="5d722-107">**貴組織的原則與 E9-1-1 的法律義務為何？**</span><span class="sxs-lookup"><span data-stu-id="5d722-107">**What are your organization's policy and legal obligations with regard to E9-1-1?**</span></span>

 <span data-ttu-id="5d722-108">E9-1-1-1-1-1-1 parlance) 中的 Pbx 法律需求 (在 E9-1-1 中稱為多行電話系統, 或 MLTS) 與狀態不同。</span><span class="sxs-lookup"><span data-stu-id="5d722-108">E9-1-1 legal requirements for PBXs (called Multi-line Telephone Systems, or MLTS, in E9-1-1 parlance) differ from state to state.</span></span> <span data-ttu-id="5d722-109">您應該向法律小組請教, 瞭解在您的相關地域中部署商務用 Skype 的義務。</span><span class="sxs-lookup"><span data-stu-id="5d722-109">You should consult with your legal team to understand the obligations that may apply to your deployment of Skype for Business in your relevant geographies.</span></span>

 <span data-ttu-id="5d722-110">**貴企業中需要為 E9 的哪些區域啟用-1-1？**</span><span class="sxs-lookup"><span data-stu-id="5d722-110">**What areas within your enterprise need to be enabled for E9-1-1?**</span></span>

 <span data-ttu-id="5d722-111">您可以為整個企業或選取的位置啟用 E9-1-1。</span><span class="sxs-lookup"><span data-stu-id="5d722-111">You can enable E9-1-1 for the entire enterprise or for selected locations.</span></span> <span data-ttu-id="5d722-112">例如, 您可能會在不同狀態的辦公室中有不同的 E9-1 需求, 或者您可能想要排除美國以外的網站</span><span class="sxs-lookup"><span data-stu-id="5d722-112">For example, you may have varying E9-1-1 requirements for offices in different states, or you may want to exclude sites outside the U.S.</span></span>

 <span data-ttu-id="5d722-113">**如何將 E9-1-1 部署到分支網站？**</span><span class="sxs-lookup"><span data-stu-id="5d722-113">**How will you deploy E9-1-1 to branch sites?**</span></span>

 <span data-ttu-id="5d722-114">語音復原是您在分支網站部署 E9-1-1 時, 必須瞭解的重要概念。</span><span class="sxs-lookup"><span data-stu-id="5d722-114">Voice resiliency is an important concept to understand when deploying E9-1-1 at a branch site.</span></span> <span data-ttu-id="5d722-115">如果您使用的是集中式電子 9-1-1 SIP trunks, 且發生 WAN 中斷, 則登入的用戶端可能無法從位置資訊服務取得位置, 或無法連線到緊急服務服務提供者。</span><span class="sxs-lookup"><span data-stu-id="5d722-115">If you have centralized E-9-1-1 SIP trunks and a WAN outage occurs, clients signing in may not be able to obtain a location from Location Information service or to connect to the emergency services service provider.</span></span> <span data-ttu-id="5d722-116">商務用 Skype 提供幾項策略, 可處理分支辦公室中的語音復原, 包括: 具備彈性資料網路、在每個分支部署 SIP 幹線, 或在中斷期間將緊急呼叫推出到本機閘道。</span><span class="sxs-lookup"><span data-stu-id="5d722-116">Skype for Business provides several strategies for handling voice resiliency in branch offices, including: having resilient data networks, deploying a SIP trunk at each branch, or pushing emergency calls out to the local gateway during outages.</span></span> <span data-ttu-id="5d722-117">如需詳細資訊, 請參閱[規劃分支網站語音復原](https://technet.microsoft.com/library/67713f57-3ded-4127-ac37-57d8099bf384.aspx)。</span><span class="sxs-lookup"><span data-stu-id="5d722-117">For details, see [Planning for Branch-Site Voice Resiliency](https://technet.microsoft.com/library/67713f57-3ded-4127-ac37-57d8099bf384.aspx).</span></span>

 <span data-ttu-id="5d722-118">**您是否要為在網路外部工作的使用者啟用 E9-1-1？**</span><span class="sxs-lookup"><span data-stu-id="5d722-118">**Will you enable E9-1-1 for users working outside the network?**</span></span>

 <span data-ttu-id="5d722-119">自動位置採集只適用于組織網路內部的客戶, 所以您的組織必須決定是否支援 E9-1-1-從商務用 Skype 用戶端, 而不是在內部部署進行的通話。</span><span class="sxs-lookup"><span data-stu-id="5d722-119">Automatic location acquisition is available only for clients located inside the organization's network, so your organization needs to decide whether it will support E9-1-1 calls made from Skype for Business clients while off-premises.</span></span> <span data-ttu-id="5d722-120">例如, 如果使用者是在家中或從客戶的網站工作, 您是否能讓他們放入緊急通話？</span><span class="sxs-lookup"><span data-stu-id="5d722-120">For example, will you enable users to place emergency calls if they are working from home or from a customer site?</span></span> <span data-ttu-id="5d722-121">如果用戶端位於商業網路之外, 則可將用戶端設定為提示使用者輸入位置。</span><span class="sxs-lookup"><span data-stu-id="5d722-121">If a client is located outside the enterprise network, the client can be configured to prompt the user for a location.</span></span> <span data-ttu-id="5d722-122">不過, 因為這些使用者提供的位置無法依據主要街道位址指南 (MSAG) prevalidated, 所以緊急服務服務提供者發送器必須在路由前確認與來電者 verbally 位置的有效性。公用安全應答點 (PSAP) 的呼叫。</span><span class="sxs-lookup"><span data-stu-id="5d722-122">However, because these user-provided locations cannot be prevalidated against the Master Street Address Guide (MSAG), the emergency services service provider dispatcher will need to confirm the validity of the location verbally with the caller before routing the call to the Public Safety Answering Point (PSAP).</span></span>

> [!NOTE]
> <span data-ttu-id="5d722-123">使用 VPN 連線到貴組織網路的使用者的商務用 Skype 用戶端可以挑選內部 IP 位址資訊, 但因為這些位址無法用來識別使用者的實際位置, 所以必須排除 VPN 子網。從位置資訊服務。</span><span class="sxs-lookup"><span data-stu-id="5d722-123">Skype for Business clients of users who connect to your organization's network by using VPN can pick up internal IP address information, but because these addresses cannot be used to identify the user's actual location, it is essential that VPN subnets are excluded from the Location Information service.</span></span>

 <span data-ttu-id="5d722-124">**您想要提供緊急呼叫路由至美國以外的網站嗎？**</span><span class="sxs-lookup"><span data-stu-id="5d722-124">**Do you want to provide emergency call routing to sites outside the U.S.?**</span></span>

 <span data-ttu-id="5d722-125">您可能會想要提供緊急路由至您公司不是由緊急服務服務提供者所提供的區域 (例如, 國際位置)。</span><span class="sxs-lookup"><span data-stu-id="5d722-125">You may want to provide emergency routing to areas of your company not served by an emergency services service provider (for example, international locations).</span></span> <span data-ttu-id="5d722-126">若要這樣做, 請建立新的網站, 然後將語音原則指派給參照 PSTN 使用狀況的網站, 以透過本機 PSTN 閘道路由通話。</span><span class="sxs-lookup"><span data-stu-id="5d722-126">To do this, create a new site, and then assign voice policies to the sites that refer to a PSTN usage that routes the call through the local PSTN gateway.</span></span>


