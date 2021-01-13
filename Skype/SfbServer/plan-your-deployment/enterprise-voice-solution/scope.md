---
title: 在商務用 Skype Server 中定義 E9-1-1 部署的範圍
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
ms.assetid: 2c572dfd-e901-471d-b5a0-18bc8d1d5328
description: 在商務用 Skype Server Enterprise Voice 中規劃 E9-1-1 部署的必要決策。
ms.openlocfilehash: bec80e94c5bc2044359875f7c56f92a1348464c9
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813423"
---
# <a name="define-the-scope-of-the-e9-1-1-deployment-in-skype-for-business-server"></a><span data-ttu-id="4351d-103">在商務用 Skype Server 中定義 E9-1-1 部署的範圍</span><span class="sxs-lookup"><span data-stu-id="4351d-103">Define the scope of the E9-1-1 deployment in Skype for Business Server</span></span>

<span data-ttu-id="4351d-104">在商務用 Skype Server Enterprise Voice 中規劃 E9-1-1 部署的必要決策。</span><span class="sxs-lookup"><span data-stu-id="4351d-104">Decisions necessary for planning an E9-1-1 deployment in Skype for Business Server Enterprise Voice.</span></span>

<span data-ttu-id="4351d-105">在您設定 E9-1-1 的商務用 Skype 之前，您必須規劃 E9-1-1 部署。</span><span class="sxs-lookup"><span data-stu-id="4351d-105">Before you configure Skype for Business for E9-1-1, you need to plan your E9-1-1 deployment.</span></span> <span data-ttu-id="4351d-106">應考量的問題包括：</span><span class="sxs-lookup"><span data-stu-id="4351d-106">Some of the questions to consider include:</span></span>

 <span data-ttu-id="4351d-107">**您的組織的原則和法律義務關於 E9-1-1？**</span><span class="sxs-lookup"><span data-stu-id="4351d-107">**What are your organization's policy and legal obligations with regard to E9-1-1?**</span></span>

 <span data-ttu-id="4351d-108">E9-1-1 對於 PBX (以 E9-1-1 的說法稱為多線電話系統，或 MLTS) 的法律要求會因為各州而有所不同。</span><span class="sxs-lookup"><span data-stu-id="4351d-108">E9-1-1 legal requirements for PBXs (called Multi-line Telephone Systems, or MLTS, in E9-1-1 parlance) differ from state to state.</span></span> <span data-ttu-id="4351d-109">您應該向法律小組請教，瞭解可能對您的相關地理區域中的商務用 Skype 部署所套用的義務。</span><span class="sxs-lookup"><span data-stu-id="4351d-109">You should consult with your legal team to understand the obligations that may apply to your deployment of Skype for Business in your relevant geographies.</span></span>

 <span data-ttu-id="4351d-110">**您的企業中有哪些領域需要啟用 E9-1-1？**</span><span class="sxs-lookup"><span data-stu-id="4351d-110">**What areas within your enterprise need to be enabled for E9-1-1?**</span></span>

 <span data-ttu-id="4351d-p103">您可以為整個企業或為選取的位置啟用 E9-1-1。例如，對於位於不同州的辦公室，您可能有不同的 E9-1-1 需求，或者您可能想要排除美國境外的網站。</span><span class="sxs-lookup"><span data-stu-id="4351d-p103">You can enable E9-1-1 for the entire enterprise or for selected locations. For example, you may have varying E9-1-1 requirements for offices in different states, or you may want to exclude sites outside the U.S.</span></span>

 <span data-ttu-id="4351d-113">**您要如何將 E9-1-1 部署至分支網站？**</span><span class="sxs-lookup"><span data-stu-id="4351d-113">**How will you deploy E9-1-1 to branch sites?**</span></span>

 <span data-ttu-id="4351d-114">在分支網站部署 E9-1-1 時，語音恢復能力是必須要了解的重要概念。</span><span class="sxs-lookup"><span data-stu-id="4351d-114">Voice resiliency is an important concept to understand when deploying E9-1-1 at a branch site.</span></span> <span data-ttu-id="4351d-115">如果您已集中式電子 9-1-1 SIP 主幹，且發生 WAN 中斷，則登入的用戶端可能無法從位置資訊服務取得位置，或無法連線至緊急服務服務提供者。</span><span class="sxs-lookup"><span data-stu-id="4351d-115">If you have centralized E-9-1-1 SIP trunks and a WAN outage occurs, clients signing in may not be able to obtain a location from Location Information service or to connect to the emergency services service provider.</span></span> <span data-ttu-id="4351d-116">商務用 Skype 提供數個策略，用來處理分支辦公室中的語音彈性，包括：具有可恢復的資料網路、在每個分支部署 SIP 主幹，或在中斷期間將緊急呼叫推出至本機閘道。</span><span class="sxs-lookup"><span data-stu-id="4351d-116">Skype for Business provides several strategies for handling voice resiliency in branch offices, including: having resilient data networks, deploying a SIP trunk at each branch, or pushing emergency calls out to the local gateway during outages.</span></span> <span data-ttu-id="4351d-117">如需詳細資訊，請參閱＜[Planning for Branch-Site Voice Resiliency](https://technet.microsoft.com/library/67713f57-3ded-4127-ac37-57d8099bf384.aspx)＞。</span><span class="sxs-lookup"><span data-stu-id="4351d-117">For details, see [Planning for Branch-Site Voice Resiliency](https://technet.microsoft.com/library/67713f57-3ded-4127-ac37-57d8099bf384.aspx).</span></span>

 <span data-ttu-id="4351d-118">**您是否會為在網路以外工作的使用者啟用 E9-1-1？**</span><span class="sxs-lookup"><span data-stu-id="4351d-118">**Will you enable E9-1-1 for users working outside the network?**</span></span>

 <span data-ttu-id="4351d-119">自動位置採集只適用于組織網路內部的用戶端，因此您的組織必須決定是否要在脫離內部部署時，支援從商務用 Skype 用戶端撥打的 E9-1-1 通話。</span><span class="sxs-lookup"><span data-stu-id="4351d-119">Automatic location acquisition is available only for clients located inside the organization's network, so your organization needs to decide whether it will support E9-1-1 calls made from Skype for Business clients while off-premises.</span></span> <span data-ttu-id="4351d-120">例如，若使用者是在家裡工作，或是在客戶網站上，您是否要允許該使用者撥打緊急通話？</span><span class="sxs-lookup"><span data-stu-id="4351d-120">For example, will you enable users to place emergency calls if they are working from home or from a customer site?</span></span> <span data-ttu-id="4351d-121">若用戶端位於企業網路之外，可設定用戶端提示使用者告知其位置。</span><span class="sxs-lookup"><span data-stu-id="4351d-121">If a client is located outside the enterprise network, the client can be configured to prompt the user for a location.</span></span> <span data-ttu-id="4351d-122">不過根據主要街道地址指南 (MSAG)，這些使用者提供的位置無法預先加以驗證，緊急服務的服務提供者發送方需要以口頭與來電者確定此位置的有效性，才能將電話路由至公共安全勤務中心 (PSAP)。</span><span class="sxs-lookup"><span data-stu-id="4351d-122">However, because these user-provided locations cannot be prevalidated against the Master Street Address Guide (MSAG), the emergency services service provider dispatcher will need to confirm the validity of the location verbally with the caller before routing the call to the Public Safety Answering Point (PSAP).</span></span>

> [!NOTE]
> <span data-ttu-id="4351d-123">使用 VPN 連線到貴組織網路之使用者的商務用 Skype 用戶端可以挑選內部 IP 位址資訊，但因為這些位址不能用來識別使用者的實際位置，所以從位置資訊服務排除 VPN 子網是必要的。</span><span class="sxs-lookup"><span data-stu-id="4351d-123">Skype for Business clients of users who connect to your organization's network by using VPN can pick up internal IP address information, but because these addresses cannot be used to identify the user's actual location, it is essential that VPN subnets are excluded from the Location Information service.</span></span>

 <span data-ttu-id="4351d-124">**您是否要提供路由至美國以外網站的緊急電話？**</span><span class="sxs-lookup"><span data-stu-id="4351d-124">**Do you want to provide emergency call routing to sites outside the U.S.?**</span></span>

 <span data-ttu-id="4351d-p106">您可以為公司中不受緊急服務的服務提供者所涵蓋的區域 (例如駐外地點) 提供緊急路由。若要這麼做，請建立新網站，然後為其指派語音原則，並讓此語音原則參照透過本機 PSTN 閘道路由電話的 PSTN 使用方式。</span><span class="sxs-lookup"><span data-stu-id="4351d-p106">You may want to provide emergency routing to areas of your company not served by an emergency services service provider (for example, international locations). To do this, create a new site, and then assign voice policies to the sites that refer to a PSTN usage that routes the call through the local PSTN gateway.</span></span>


