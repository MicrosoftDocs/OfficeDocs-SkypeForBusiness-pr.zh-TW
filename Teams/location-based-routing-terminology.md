---
title: 以位置為基礎的路由術語
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.date: 2/1/2019
ms.topic: conceptual
ms.reviewer: roykuntz
ms.service: msteams
audience: admin
search.appverid: MET150
description: 瞭解與以位置為基礎之路由的相關術語與概念，以進行直接路由。
localization_priority: Normal
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: e9c7a323bb252c254d7422c30251414742608529
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2019
ms.locfileid: "37572008"
---
# <a name="location-based-routing-terminology"></a><span data-ttu-id="e1589-103">以位置為基礎的路由術語</span><span class="sxs-lookup"><span data-stu-id="e1589-103">Location-Based Routing terminology</span></span>

> [!INCLUDE [Preview customer token](includes/preview-feature.md)] 

<span data-ttu-id="e1589-104">以下是在整個以位置為基礎的路由檔中使用的一些術語與概念。</span><span class="sxs-lookup"><span data-stu-id="e1589-104">Here are some terms and concepts that are used throughout the Location-Based Routing documentation.</span></span> <span data-ttu-id="e1589-105">建議您先熟悉這些條款與概念，然後再深入瞭解檔。</span><span class="sxs-lookup"><span data-stu-id="e1589-105">It's a good idea to be familiar with these terms and concepts before you get deeper into the documentation.</span></span>

|<span data-ttu-id="e1589-106">字詞</span><span class="sxs-lookup"><span data-stu-id="e1589-106">Term</span></span>  |<span data-ttu-id="e1589-107">說明</span><span class="sxs-lookup"><span data-stu-id="e1589-107">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="e1589-108">網路區域</span><span class="sxs-lookup"><span data-stu-id="e1589-108">Network regions</span></span>     | <span data-ttu-id="e1589-109">網路區域包含一個網路網站集合。</span><span class="sxs-lookup"><span data-stu-id="e1589-109">A network region contains a collection of network sites.</span></span> <span data-ttu-id="e1589-110">例如，如果您的組織有許多位於印度的網站，您可以選擇將 "印度" 指定為網路區域。</span><span class="sxs-lookup"><span data-stu-id="e1589-110">For example, if your organization has many sites located in India, you may choose to designate “India” as a network region.</span></span>        |
|<span data-ttu-id="e1589-111">網路網站</span><span class="sxs-lookup"><span data-stu-id="e1589-111">Network sites</span></span>    | <span data-ttu-id="e1589-112">網路網站代表貴組織有實體場所（例如辦公室、一組建築物或校園）的位置。</span><span class="sxs-lookup"><span data-stu-id="e1589-112">A network site represents a location where your organization has a physical venue, such as an office, a set of buildings, or a campus.</span></span> <span data-ttu-id="e1589-113">網路網站定義為 IP 子網的集合。</span><span class="sxs-lookup"><span data-stu-id="e1589-113">Network sites are defined as a collection of IP subnets.</span></span> <span data-ttu-id="e1589-114">針對位置路由的最佳做法是為每個具有唯一 PSTN 連線的位置建立一個單獨的網站。</span><span class="sxs-lookup"><span data-stu-id="e1589-114">A best practice for Location-Based Routing is to create a separate site for each location that has unique PSTN connectivity.</span></span>  <span data-ttu-id="e1589-115">每個網路網站都必須與一個網路區域建立關聯。</span><span class="sxs-lookup"><span data-stu-id="e1589-115">Each network site must be associated with a network region.</span></span> <span data-ttu-id="e1589-116">您可以建立可用於位置路由的網站，或是未啟用位置式路由的網站。</span><span class="sxs-lookup"><span data-stu-id="e1589-116">You can create a site that's enabled for Location-Based Routing or a site that's not enabled for Location-Based Routing.</span></span> <span data-ttu-id="e1589-117">例如，您可能會想要建立未啟用位置路由的網站，以允許啟用位置路由的使用者在漫遊到該網站時，進行 PSTN 呼叫。</span><span class="sxs-lookup"><span data-stu-id="e1589-117">For example, you may want to create a site that's not enabled for Location-Based Routing to allow users who are enabled for Location-Based Routing to make PSTN calls when they roam to that site.</span></span> <span data-ttu-id="e1589-118">請注意，網路網站也可以用來啟用和設定緊急通話。</span><span class="sxs-lookup"><span data-stu-id="e1589-118">Note that network sites may also be used to enable and configure emergency calling.</span></span>        |
|<span data-ttu-id="e1589-119">網路子網</span><span class="sxs-lookup"><span data-stu-id="e1589-119">Network subnets</span></span>     |<span data-ttu-id="e1589-120">在團隊端點可以連接至網路的位置上，IP 子網必須定義並關聯至已定義的網路，才能強制進行免付費略過。</span><span class="sxs-lookup"><span data-stu-id="e1589-120">IP subnets at the location where Teams endpoints can connect to the network must be defined and associated to a defined network to enforce toll bypass.</span></span> <span data-ttu-id="e1589-121">多個子網可能會與同一個網路網站建立關聯，但多個網站可能不會與同一個子網產生關聯。</span><span class="sxs-lookup"><span data-stu-id="e1589-121">Multiple subnets may be associated with the same network site, but multiple sites may not be associated with a same subnet.</span></span> <span data-ttu-id="e1589-122">這個子網的關聯功能可讓您以位置路由來找出端點，以判斷是否應該允許指定的 PSTN 通話。</span><span class="sxs-lookup"><span data-stu-id="e1589-122">This association of subnets enables Location-Based Routing to locate the endpoints geographically to determine whether a given PSTN call should be allowed.</span></span> <span data-ttu-id="e1589-123">支援 IPv6 和 IPv4 子網。</span><span class="sxs-lookup"><span data-stu-id="e1589-123">Both IPv6 and IPv4 subnets are supported.</span></span> <span data-ttu-id="e1589-124">決定團隊端點是否位於網站上時，以位置為基礎的路由會先檢查相符的 IPv6 位址。</span><span class="sxs-lookup"><span data-stu-id="e1589-124">When determining whether a Teams endpoint is located at a site, Location-Based Routing first checks for a matching IPv6 address.</span></span> <span data-ttu-id="e1589-125">如果 IPv6 位址不存在，則以位置為基礎的路由檢查 IPv4 位址。</span><span class="sxs-lookup"><span data-stu-id="e1589-125">If an IPv6 address isn't present, Location-Based Routing checks for an IPv4 address.</span></span> <br><br>
|<span data-ttu-id="e1589-126">受信任的外部 IP 位址</span><span class="sxs-lookup"><span data-stu-id="e1589-126">Trusted external IP addresses</span></span>    |<span data-ttu-id="e1589-127">[受信任的外部 IP 位址] 是商業網路的網際網路外部 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="e1589-127">Trusted external IP addresses are the Internet external IP addresses of the enterprise network.</span></span> <span data-ttu-id="e1589-128">在檢查特定網站相符前，他們會判斷使用者的端點是否在公司網路內。</span><span class="sxs-lookup"><span data-stu-id="e1589-128">They determine whether the user’s endpoint is inside the corporate network before checking for a specific site match.</span></span> <span data-ttu-id="e1589-129">如果使用者的外部 IP 與信任清單中定義的 IP 位址相符，則以位置為基礎的路由檢查，以判斷使用者端點所在的內部子網。</span><span class="sxs-lookup"><span data-stu-id="e1589-129">If the user’s external IP matches an IP address that's defined in the trusted list, Location-Based Routing checks to determine the internal subnet where the user’s endpoint is located.</span></span> <span data-ttu-id="e1589-130">如果使用者的外部 IP 位址與在信任清單中定義的任何 IP 位址都不相符，則會將端點分類為未知的位置，而對已啟用位置路由的使用者進行任何 PSTN 呼叫，都會遭到封鎖。</span><span class="sxs-lookup"><span data-stu-id="e1589-130">If the user’s external IP address doesn’t match any IP address that's defined in the trusted list, the endpoint is classified as being at an unknown location and any PSTN calls to or from a user who is enabled for Location-Based Routing are blocked.</span></span>          |

### <a name="related-topics"></a><span data-ttu-id="e1589-131">相關主題</span><span class="sxs-lookup"><span data-stu-id="e1589-131">Related topics</span></span>
- [<span data-ttu-id="e1589-132">規劃直接路由的以位置為基礎的路由</span><span class="sxs-lookup"><span data-stu-id="e1589-132">Plan Location-Based Routing for Direct Routing</span></span>](location-based-routing-plan.md)
- [<span data-ttu-id="e1589-133">設定以位置為基礎的路由的網路設定</span><span class="sxs-lookup"><span data-stu-id="e1589-133">Configure network settings for Location-Based Routing</span></span>](location-based-routing-configure-network-settings.md)
- [<span data-ttu-id="e1589-134">針對直接路由啟用以位置為基礎的路由</span><span class="sxs-lookup"><span data-stu-id="e1589-134">Enable Location-Based Routing for Direct Routing</span></span>](location-based-routing-enable.md)
