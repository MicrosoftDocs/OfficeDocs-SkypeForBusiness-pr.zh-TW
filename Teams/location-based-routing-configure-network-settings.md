---
title: 設定依位置路由的網路設定
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.reviewer: roykuntz
audience: admin
ms.service: msteams
search.appverid: MET150
description: 瞭解如何針對直接路由建立及設定以位置為基礎的路由的網路區域、網站和子網。
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: bfa81c0d5856ba97b60f3183ff282bef8c911fda
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41836563"
---
# <a name="configure-network-settings-for-location-based-routing"></a><span data-ttu-id="1a390-103">設定依位置路由的網路設定</span><span class="sxs-lookup"><span data-stu-id="1a390-103">Configure network settings for Location-Based Routing</span></span>

> [!INCLUDE [Preview customer token](includes/preview-feature.md)]

<span data-ttu-id="1a390-104">如果您尚未這麼做，請參閱[直接路由的 [規劃位置] 路由](location-based-routing-plan.md)，以查看在設定位置式路由的網路設定之前，您必須採取的其他步驟。</span><span class="sxs-lookup"><span data-stu-id="1a390-104">If you haven't already done so, read [Plan Location-Based Routing for Direct Routing](location-based-routing-plan.md) to review other steps you'll need to take before you configure network settings for Location-Based Routing.</span></span>

<span data-ttu-id="1a390-105">本文說明如何設定以位置為基礎的路由的網路設定。</span><span class="sxs-lookup"><span data-stu-id="1a390-105">This article describes how to configure network settings for Location-Based Routing.</span></span> <span data-ttu-id="1a390-106">在貴組織中部署手機系統直接路由之後，接下來的步驟是建立及設定網路區域、網路網站和網路子網。</span><span class="sxs-lookup"><span data-stu-id="1a390-106">After you deploy Phone System Direct Routing in your organization, the next steps are to create and set up network regions, network sites, and network subnets.</span></span>

## <a name="define-network-regions"></a><span data-ttu-id="1a390-107">定義網路區域</span><span class="sxs-lookup"><span data-stu-id="1a390-107">Define network regions</span></span>

<span data-ttu-id="1a390-108">網路區域包含網路網站的集合，以及跨多個地理區域互連網路的各個部分。</span><span class="sxs-lookup"><span data-stu-id="1a390-108">A network region contains a collection of network sites and interconnects various parts of a network across multiple geographic areas.</span></span> <span data-ttu-id="1a390-109">如需如何設定網路區域的步驟，請移至[管理團隊中雲端功能的網路拓撲](manage-your-network-topology.md)。</span><span class="sxs-lookup"><span data-stu-id="1a390-109">For steps on how to configure network regions, go to [Manage your network topology for cloud features in Teams](manage-your-network-topology.md).</span></span>

## <a name="define-network-sites"></a><span data-ttu-id="1a390-110">定義網路網站</span><span class="sxs-lookup"><span data-stu-id="1a390-110">Define network sites</span></span>

<span data-ttu-id="1a390-111">網路網站代表貴組織有實體場所（例如辦公室、一組建築物或校園）的位置。</span><span class="sxs-lookup"><span data-stu-id="1a390-111">A network site represents a location where your organization has a physical venue, such as an office, a set of buildings, or a campus.</span></span> <span data-ttu-id="1a390-112">您必須將拓撲中的每個網路網站與網路區域建立關聯。</span><span class="sxs-lookup"><span data-stu-id="1a390-112">You must associate each network site in your topology with a network region.</span></span> <span data-ttu-id="1a390-113">如需如何設定網路網站的步驟，請參閱[在團隊中管理雲端功能的網路拓撲](manage-your-network-topology.md)。</span><span class="sxs-lookup"><span data-stu-id="1a390-113">For steps on how to configure network sites, see [Manage your network topology for cloud features in Teams](manage-your-network-topology.md).</span></span>

<span data-ttu-id="1a390-114">針對位置路由的最佳做法是為每個具有唯一 PSTN 連線的位置建立一個單獨的網站。</span><span class="sxs-lookup"><span data-stu-id="1a390-114">A best practice for Location-Based Routing is to create a separate site for each location that has unique PSTN connectivity.</span></span> <span data-ttu-id="1a390-115">您可以建立可用於位置路由的網站，或是未啟用位置式路由的網站。</span><span class="sxs-lookup"><span data-stu-id="1a390-115">You can create a site that's enabled for Location-Based Routing or a site that's not enabled for Location-Based Routing.</span></span> <span data-ttu-id="1a390-116">例如，您可能會想要建立未啟用位置路由的網站，以允許啟用位置路由的使用者在漫遊到該網站時，進行 PSTN 呼叫。</span><span class="sxs-lookup"><span data-stu-id="1a390-116">For example, you may want to create a site that's not enabled for Location-Based Routing to allow users who are enabled for Location-Based Routing to make PSTN calls when they roam to that site.</span></span>

## <a name="define-network-subnets"></a><span data-ttu-id="1a390-117">定義網路子網</span><span class="sxs-lookup"><span data-stu-id="1a390-117">Define network subnets</span></span>

<span data-ttu-id="1a390-118">每個子網都必須與特定的網路網站相關聯。</span><span class="sxs-lookup"><span data-stu-id="1a390-118">Each subnet must be associated with a specific network site.</span></span> <span data-ttu-id="1a390-119">您可以將多個子網與同一個網路網站建立關聯，但無法將多個網站與同一個子網建立關聯。</span><span class="sxs-lookup"><span data-stu-id="1a390-119">You can associate multiple subnets with the same network site but you can't associate multiple sites with the same subnet.</span></span> <span data-ttu-id="1a390-120">如需如何設定網路子網的步驟，請移至[管理團隊中雲端功能的網路拓撲](manage-your-network-topology.md)。</span><span class="sxs-lookup"><span data-stu-id="1a390-120">For steps on how to configure network subnets, go to  [Manage your network topology for cloud features in Teams](manage-your-network-topology.md).</span></span>

<span data-ttu-id="1a390-121">對於以位置為基礎的路由，小組端點可以連接至網路的位置上的 IP 子網必須定義並與已定義的網路建立關聯，才能強制進行免付費旁路。</span><span class="sxs-lookup"><span data-stu-id="1a390-121">For Location-Based Routing, IP subnets at the location where Teams endpoints can connect to the network must be defined and associated to a defined network to enforce toll bypass.</span></span> <span data-ttu-id="1a390-122">這個子網的關聯功能可讓您以位置路由來找出端點，以判斷是否應該允許指定的 PSTN 通話。</span><span class="sxs-lookup"><span data-stu-id="1a390-122">This association of subnets enables Location-Based Routing to locate the endpoints geographically to determine whether a given PSTN call should be allowed.</span></span> <span data-ttu-id="1a390-123">支援 IPv6 和 IPv4 子網。</span><span class="sxs-lookup"><span data-stu-id="1a390-123">Both IPv6 and IPv4 subnets are supported.</span></span> <span data-ttu-id="1a390-124">決定團隊端點是否位於網站上時，以位置為基礎的路由會先檢查相符的 IPv6 位址。</span><span class="sxs-lookup"><span data-stu-id="1a390-124">When determining whether a Teams endpoint is located at a site, Location-Based Routing first checks for a matching IPv6 address.</span></span> <span data-ttu-id="1a390-125">如果 IPv6 位址不存在，則以位置為基礎的路由檢查 IPv4 位址。</span><span class="sxs-lookup"><span data-stu-id="1a390-125">If an IPv6 address isn't present, Location-Based Routing checks for an IPv4 address.</span></span>

## <a name="define-trusted-ip-addresses-external-subnets"></a><span data-ttu-id="1a390-126">定義信任的 IP 位址（外部子網）</span><span class="sxs-lookup"><span data-stu-id="1a390-126">Define trusted IP addresses (external subnets)</span></span>

<span data-ttu-id="1a390-127">[信任的 IP 位址] 是商業網路的網際網路外部 IP 位址，用來判斷使用者的端點是否在商業網路內。</span><span class="sxs-lookup"><span data-stu-id="1a390-127">Trusted IP addresses are the internet external IP addresses of the enterprise network and are used to determine whether the user's endpoint is inside the corporate network.</span></span> <span data-ttu-id="1a390-128">如需如何設定信任的 IP 位址的步驟，請移至[管理團隊中雲端功能的網路拓撲](manage-your-network-topology.md)。</span><span class="sxs-lookup"><span data-stu-id="1a390-128">For steps on how to configure trusted IP addresses, go to  [Manage your network topology for cloud features in Teams](manage-your-network-topology.md).</span></span>

<span data-ttu-id="1a390-129">如果使用者的外部 IP 位址與 [信任的 IP 位址] 清單中的 IP 位址相符，則以位置為基礎的路由檢查，以判斷使用者端點所在的內部子網。</span><span class="sxs-lookup"><span data-stu-id="1a390-129">If the user’s external IP address matches an IP address that's in the trusted IP address list, Location-Based Routing checks to determine the internal subnet where the user’s endpoint is located.</span></span> <span data-ttu-id="1a390-130">如果使用者的外部 IP 位址與 [信任的 IP 位址] 清單中定義的任何 IP 位址都不相符，則會將端點分類為 [未知位置]，而且會封鎖對已啟用位置路由的使用者的任何 PSTN 呼叫。</span><span class="sxs-lookup"><span data-stu-id="1a390-130">If the user’s external IP address doesn’t match any IP address that's defined in the trusted IP address list, the endpoint is classified as being at an unknown location and any PSTN calls to or from a user who is enabled for Location-Based Routing are blocked.</span></span>

## <a name="next-steps"></a><span data-ttu-id="1a390-131">後續步驟</span><span class="sxs-lookup"><span data-stu-id="1a390-131">Next steps</span></span>

<span data-ttu-id="1a390-132">移至 [[啟用直接路由的以位置為基礎的路由](location-based-routing-enable.md)]。</span><span class="sxs-lookup"><span data-stu-id="1a390-132">Go to [Enable Location-Based Routing for Direct Routing](location-based-routing-enable.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="1a390-133">相關主題</span><span class="sxs-lookup"><span data-stu-id="1a390-133">Related topics</span></span>

- [<span data-ttu-id="1a390-134">小組中雲端語音功能的網路設定</span><span class="sxs-lookup"><span data-stu-id="1a390-134">Network settings for cloud voice features in Teams</span></span>](cloud-voice-network-settings.md)
