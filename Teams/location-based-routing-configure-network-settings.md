---
title: 設定網路設定 - 位置式路由
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.reviewer: roykuntz
audience: admin
ms.service: msteams
search.appverid: MET150
description: 瞭解如何建立及設定網路區域、網站和子網，Location-Based直接路由的路由。
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: a7dd707a6066cfe9a8dfcbcc9b3ae36d450d1dd1
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49822943"
---
# <a name="configure-network-settings-for-location-based-routing"></a><span data-ttu-id="45fbb-103">設定依位置路由的網路設定</span><span class="sxs-lookup"><span data-stu-id="45fbb-103">Configure network settings for Location-Based Routing</span></span>

<span data-ttu-id="45fbb-104">如果您尚未這麼做，請參閱規劃直接路由Location-Based路由[](location-based-routing-plan.md)，以在設定路由的網路設定之前，先檢查Location-Based步驟。</span><span class="sxs-lookup"><span data-stu-id="45fbb-104">If you haven't already done so, read [Plan Location-Based Routing for Direct Routing](location-based-routing-plan.md) to review other steps you'll need to take before you configure network settings for Location-Based Routing.</span></span>

<span data-ttu-id="45fbb-105">本文將說明如何設定路由Location-Based設定。</span><span class="sxs-lookup"><span data-stu-id="45fbb-105">This article describes how to configure network settings for Location-Based Routing.</span></span> <span data-ttu-id="45fbb-106">在組織中電話系統直接路由之後，接下來的步驟是建立和設定網路區域、網路網站和網路子網。</span><span class="sxs-lookup"><span data-stu-id="45fbb-106">After you deploy Phone System Direct Routing in your organization, the next steps are to create and set up network regions, network sites, and network subnets.</span></span>

## <a name="define-network-regions"></a><span data-ttu-id="45fbb-107">定義網路區域</span><span class="sxs-lookup"><span data-stu-id="45fbb-107">Define network regions</span></span>

<span data-ttu-id="45fbb-108">網路區域包含網路網站集合，並跨多個地理區域互連網路的各個部分。</span><span class="sxs-lookup"><span data-stu-id="45fbb-108">A network region contains a collection of network sites and interconnects various parts of a network across multiple geographic areas.</span></span> <span data-ttu-id="45fbb-109">若要瞭解如何設定網路區域的步驟，請前往 管理網路拓撲以在[Teams。](manage-your-network-topology.md)</span><span class="sxs-lookup"><span data-stu-id="45fbb-109">For steps on how to configure network regions, go to [Manage your network topology for cloud features in Teams](manage-your-network-topology.md).</span></span>

## <a name="define-network-sites"></a><span data-ttu-id="45fbb-110">定義網路網站</span><span class="sxs-lookup"><span data-stu-id="45fbb-110">Define network sites</span></span>

<span data-ttu-id="45fbb-111">網路網站代表貴組織有實體場地的位置，例如辦公室、一組建築物或校園。</span><span class="sxs-lookup"><span data-stu-id="45fbb-111">A network site represents a location where your organization has a physical venue, such as an office, a set of buildings, or a campus.</span></span> <span data-ttu-id="45fbb-112">您必須將拓撲中的每個網路網站與網路區域建立關聯。</span><span class="sxs-lookup"><span data-stu-id="45fbb-112">You must associate each network site in your topology with a network region.</span></span> <span data-ttu-id="45fbb-113">若要瞭解如何設定網路網站的步驟，請參閱在 Teams 中管理雲端功能[的網路拓撲](manage-your-network-topology.md)。</span><span class="sxs-lookup"><span data-stu-id="45fbb-113">For steps on how to configure network sites, see [Manage your network topology for cloud features in Teams](manage-your-network-topology.md).</span></span>

<span data-ttu-id="45fbb-114">使用 [路由Location-Based最佳做法是為每個具有唯一 PSTN 連接的位置建立個別的網站。</span><span class="sxs-lookup"><span data-stu-id="45fbb-114">A best practice for Location-Based Routing is to create a separate site for each location that has unique PSTN connectivity.</span></span> <span data-ttu-id="45fbb-115">您可以建立為路由Location-Based啟用的網站，或未針對路由啟用Location-Based網站。</span><span class="sxs-lookup"><span data-stu-id="45fbb-115">You can create a site that's enabled for Location-Based Routing or a site that's not enabled for Location-Based Routing.</span></span> <span data-ttu-id="45fbb-116">例如，您可能會想要建立未針對 Location-Based 路由啟用的網站，讓已啟用 Location-Based 路由的使用者在漫遊到該網站時撥打 PSTN 通話。</span><span class="sxs-lookup"><span data-stu-id="45fbb-116">For example, you may want to create a site that's not enabled for Location-Based Routing to allow users who are enabled for Location-Based Routing to make PSTN calls when they roam to that site.</span></span>

## <a name="define-network-subnets"></a><span data-ttu-id="45fbb-117">定義網路子網</span><span class="sxs-lookup"><span data-stu-id="45fbb-117">Define network subnets</span></span>

<span data-ttu-id="45fbb-118">每個子網都必須與特定的網路網站相關聯。</span><span class="sxs-lookup"><span data-stu-id="45fbb-118">Each subnet must be associated with a specific network site.</span></span> <span data-ttu-id="45fbb-119">您可以將多個子網與同一個網路網站建立關聯，但無法將多個網站與同一個子網建立關聯。</span><span class="sxs-lookup"><span data-stu-id="45fbb-119">You can associate multiple subnets with the same network site but you can't associate multiple sites with the same subnet.</span></span> <span data-ttu-id="45fbb-120">若要瞭解如何設定網路子網的步驟，請前往 管理網路拓撲以在 Teams 中[管理雲端Teams。](manage-your-network-topology.md)</span><span class="sxs-lookup"><span data-stu-id="45fbb-120">For steps on how to configure network subnets, go to  [Manage your network topology for cloud features in Teams](manage-your-network-topology.md).</span></span>

<span data-ttu-id="45fbb-121">針對 Location-Based路由，必須定義可Teams端點可連至網路的 IP 子網，並與定義的網路建立關聯，才能強制執行免付費。</span><span class="sxs-lookup"><span data-stu-id="45fbb-121">For Location-Based Routing, IP subnets at the location where Teams endpoints can connect to the network must be defined and associated to a defined network to enforce toll bypass.</span></span> <span data-ttu-id="45fbb-122">這個子閘道聯Location-Based路由，以地理方式找出端點，以判斷是否應該允許特定 PSTN 通話。</span><span class="sxs-lookup"><span data-stu-id="45fbb-122">This association of subnets enables Location-Based Routing to locate the endpoints geographically to determine whether a given PSTN call should be allowed.</span></span> <span data-ttu-id="45fbb-123">支援 IPv6 和 IPv4 子網。</span><span class="sxs-lookup"><span data-stu-id="45fbb-123">Both IPv6 and IPv4 subnets are supported.</span></span> <span data-ttu-id="45fbb-124">當判斷Teams端點是否位於網站時，Location-Based路由會先檢查符合的 IPv6 位址。</span><span class="sxs-lookup"><span data-stu-id="45fbb-124">When determining whether a Teams endpoint is located at a site, Location-Based Routing first checks for a matching IPv6 address.</span></span> <span data-ttu-id="45fbb-125">如果沒有 IPv6 位址，請Location-Based路由檢查 IPv4 位址。</span><span class="sxs-lookup"><span data-stu-id="45fbb-125">If an IPv6 address isn't present, Location-Based Routing checks for an IPv4 address.</span></span>

## <a name="define-trusted-ip-addresses-external-subnets"></a><span data-ttu-id="45fbb-126">定義信任的 IP 位址 (外部子網) </span><span class="sxs-lookup"><span data-stu-id="45fbb-126">Define trusted IP addresses (external subnets)</span></span>

<span data-ttu-id="45fbb-127">信任的 IP 位址是商業網路的網際網路外部 IP 位址，用來判斷使用者的端點是否位於公司網路內。</span><span class="sxs-lookup"><span data-stu-id="45fbb-127">Trusted IP addresses are the internet external IP addresses of the enterprise network and are used to determine whether the user's endpoint is inside the corporate network.</span></span> <span data-ttu-id="45fbb-128">若要瞭解如何設定信任的 IP 位址的步驟，請前往 管理網路拓撲以在 Teams 中[管理雲端Teams。](manage-your-network-topology.md)</span><span class="sxs-lookup"><span data-stu-id="45fbb-128">For steps on how to configure trusted IP addresses, go to  [Manage your network topology for cloud features in Teams](manage-your-network-topology.md).</span></span>

<span data-ttu-id="45fbb-129">如果使用者的外部 IP 位址符合信任 IP 位址清單中的 IP 位址，Location-Based 路由會檢查以判斷使用者端點所在的內部子網。</span><span class="sxs-lookup"><span data-stu-id="45fbb-129">If the user's external IP address matches an IP address that's in the trusted IP address list, Location-Based Routing checks to determine the internal subnet where the user's endpoint is located.</span></span> <span data-ttu-id="45fbb-130">如果使用者的外部 IP 位址與信任 IP 位址清單中定義的任何 IP 位址不相符，端點會分類為位於未知位置，而且會封鎖與啟用 Location-Based 路由的使用者的任何 PSTN 通話。</span><span class="sxs-lookup"><span data-stu-id="45fbb-130">If the user's external IP address doesn't match any IP address that's defined in the trusted IP address list, the endpoint is classified as being at an unknown location and any PSTN calls to or from a user who is enabled for Location-Based Routing are blocked.</span></span>

## <a name="next-steps"></a><span data-ttu-id="45fbb-131">後續步驟</span><span class="sxs-lookup"><span data-stu-id="45fbb-131">Next steps</span></span>

<span data-ttu-id="45fbb-132">前往 啟用[直接Location-Based路由的路由。](location-based-routing-enable.md)</span><span class="sxs-lookup"><span data-stu-id="45fbb-132">Go to [Enable Location-Based Routing for Direct Routing](location-based-routing-enable.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="45fbb-133">相關主題</span><span class="sxs-lookup"><span data-stu-id="45fbb-133">Related topics</span></span>

- [<span data-ttu-id="45fbb-134">雲端語音功能的網路設定Teams</span><span class="sxs-lookup"><span data-stu-id="45fbb-134">Network settings for cloud voice features in Teams</span></span>](cloud-voice-network-settings.md)
