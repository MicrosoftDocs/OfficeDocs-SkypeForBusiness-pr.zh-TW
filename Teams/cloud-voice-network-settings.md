---
title: 雲端語音功能的網路設定
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: conceptual
ms.reviewer: roykuntz
ms.service: msteams
audience: admin
search.appverid: MET150
description: 瞭解您必須為直接路由和增強的緊急服務Location-Based路由所必須設定的網路設定。
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
- m365initiative-voice
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: e97ddf7f6b7410e83a5e2257d7df6ae2ad27cb7f
ms.sourcegitcommit: 5c68298474d1782e69bde8c0940be7150cb93f6e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/23/2021
ms.locfileid: "53096280"
---
# <a name="network-settings-for-cloud-voice-features-in-microsoft-teams"></a><span data-ttu-id="af521-103">雲端語音功能的網路設定Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="af521-103">Network settings for cloud voice features in Microsoft Teams</span></span>

<span data-ttu-id="af521-104">瞭解網路區域、網路網站、網路子網和受信任的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="af521-104">Learn about network regions, network sites, network subnets, and trusted IP addresses.</span></span> <span data-ttu-id="af521-105">這些條款和概念會用於我們的雲端語音檔，用於[](location-based-routing-plan.md)直接路由和[動態](configure-dynamic-emergency-calling.md)緊急電話的定位式路由。</span><span class="sxs-lookup"><span data-stu-id="af521-105">These terms and concepts are used throughout our cloud voice documentation for [Location-Based Routing for Direct Routing](location-based-routing-plan.md) and [dynamic emergency calling](configure-dynamic-emergency-calling.md).</span></span> <span data-ttu-id="af521-106">如果您要在組織中部署這些雲端功能，您必須設定網路設定，以在 Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="af521-106">If you're deploying these cloud features in your organization, you must configure network settings for use with these features in Microsoft Teams.</span></span>

<span data-ttu-id="af521-107">本文提供您常用的網路設定概觀，Location-Based路由和動態緊急電話。</span><span class="sxs-lookup"><span data-stu-id="af521-107">This article gives you an overview of the network settings that are common to Location-Based Routing and dynamic emergency calling.</span></span> <span data-ttu-id="af521-108">根據您部署的雲端語音功能，您可以設定部分或所有設定。</span><span class="sxs-lookup"><span data-stu-id="af521-108">Depending on the cloud voice feature and capability that you're deploying, you configure some or all these settings.</span></span> <span data-ttu-id="af521-109">若要瞭解如何設定這些設定的步驟，請參閱在 Teams 中管理雲端[功能的網路拓撲](manage-your-network-topology.md)。</span><span class="sxs-lookup"><span data-stu-id="af521-109">For steps on how to configure these settings, see [Manage your network topology for cloud features in Teams](manage-your-network-topology.md).</span></span>

> [!NOTE]
> <span data-ttu-id="af521-110">網路設定的任何特定功能需求會記錄在該功能的設定主題中。</span><span class="sxs-lookup"><span data-stu-id="af521-110">Any feature-specific requirements for network settings are documented in the configuration topics for that feature.</span></span>

## <a name="network-region"></a><span data-ttu-id="af521-111">網路區域</span><span class="sxs-lookup"><span data-stu-id="af521-111">Network region</span></span>

<span data-ttu-id="af521-112">網路區域包含網路網站的集合。</span><span class="sxs-lookup"><span data-stu-id="af521-112">A network region contains a collection of network sites.</span></span> <span data-ttu-id="af521-113">它可跨多個地理區域連接網路的各個部分。</span><span class="sxs-lookup"><span data-stu-id="af521-113">It interconnects various parts of a network across multiple geographic areas.</span></span> <span data-ttu-id="af521-114">例如，如果貴組織有許多位於印度的網站，您可以選擇將「印度」指定為網路區域。</span><span class="sxs-lookup"><span data-stu-id="af521-114">For example, if your organization has many sites located in India, you may choose to designate "India" as a network region.</span></span> <span data-ttu-id="af521-115">每個網路網站都必須與網路區域相關聯。</span><span class="sxs-lookup"><span data-stu-id="af521-115">Each network site must be associated with a network region.</span></span>

<span data-ttu-id="af521-116">相同的網路區域會由直接路由Location-Based路由和增強的緊急服務共用。</span><span class="sxs-lookup"><span data-stu-id="af521-116">The same network regions are shared by Location-Based Routing for Direct Routing and enhanced emergency services.</span></span> <span data-ttu-id="af521-117">如果您已經為一項功能建立網路區域，則不需要為另一項功能建立新網路區域。</span><span class="sxs-lookup"><span data-stu-id="af521-117">If you already created network regions for one feature, you don't have to create new network regions for the other feature.</span></span>

## <a name="network-site"></a><span data-ttu-id="af521-118">網路網站</span><span class="sxs-lookup"><span data-stu-id="af521-118">Network site</span></span>

<span data-ttu-id="af521-119">網路網站代表貴組織有實體場地的位置，例如辦公室、一組建築物或校園。</span><span class="sxs-lookup"><span data-stu-id="af521-119">A network site represents a location where your organization has a physical venue, such as an office, a set of buildings, or a campus.</span></span> <span data-ttu-id="af521-120">網路網站定義為 IP 子網的集合。</span><span class="sxs-lookup"><span data-stu-id="af521-120">Network sites are defined as a collection of IP subnets.</span></span> <span data-ttu-id="af521-121">每個網路網站都必須與網路區域相關聯。</span><span class="sxs-lookup"><span data-stu-id="af521-121">Each network site must be associated with a network region.</span></span>

<span data-ttu-id="af521-122">您也可以使用網路網站啟用及設定緊急通話。</span><span class="sxs-lookup"><span data-stu-id="af521-122">You can also use network sites to enable and configure emergency calling.</span></span>

## <a name="network-subnet"></a><span data-ttu-id="af521-123">網路子網</span><span class="sxs-lookup"><span data-stu-id="af521-123">Network subnet</span></span>

<span data-ttu-id="af521-124">每個子網都必須與特定的網路網站相關聯。</span><span class="sxs-lookup"><span data-stu-id="af521-124">Each subnet must be associated with a specific network site.</span></span> <span data-ttu-id="af521-125">用戶端的位置是根據網路子網和相關網路網站所決定。</span><span class="sxs-lookup"><span data-stu-id="af521-125">A client's location is determined based on the network subnet and the associated network site.</span></span> <span data-ttu-id="af521-126">您可以將多個子網與同一個網路網站建立關聯，但無法將多個網站與同一個子網建立關聯。</span><span class="sxs-lookup"><span data-stu-id="af521-126">You can associate multiple subnets with the same network site but you can't associate multiple sites with the same subnet.</span></span>

<span data-ttu-id="af521-127">子網資訊會用來判斷啟動新會話時端點所在的網路網站。</span><span class="sxs-lookup"><span data-stu-id="af521-127">Subnet information is used to determine the network site on which an endpoint is located when a new session is initiated.</span></span> <span data-ttu-id="af521-128">當會話內每一方的位置為已知時，雲端語音功能可以運用該資訊來決定如何處理通話設定或路由。</span><span class="sxs-lookup"><span data-stu-id="af521-128">When the location of each party in a session is known, the cloud voice feature can apply that information to determine how to handle call setup or routing.</span></span>

<span data-ttu-id="af521-129">針對每個網路網站，請與您的網路系統管理員合作，決定指派給每個網路網站的 IP 子網。</span><span class="sxs-lookup"><span data-stu-id="af521-129">For each network site, work with your network admin to determine which IP subnets are assigned to each network site.</span></span> <span data-ttu-id="af521-130">例如，北美地區的紐約網站可以指派下列 IP 子網：172.29.80.0/23、157.57.216.0/25、172.29.91.0/23、172.29.81.0/24。</span><span class="sxs-lookup"><span data-stu-id="af521-130">For example, the New York site in the North America region can be assigned the following IP subnets: 172.29.80.0/23, 157.57.216.0/25, 172.29.91.0/23, 172.29.81.0/24.</span></span> <span data-ttu-id="af521-131">如果一般在密地安地亞工作的 Bob 前往紐約辦公室接受訓練，開啟電腦並連接到網路，他的電腦會取得配置給紐約之四個範圍之一的 IP 位址，例如 172.29.80.103。</span><span class="sxs-lookup"><span data-stu-id="af521-131">If Bob, who usually works in Detroit, travels to the New York office for training, turns on his computer and connects to the network, his computer will get an IP address in one of the four ranges that are allocated for New York, for example, 172.29.80.103.</span></span>

## <a name="trusted-ip-address"></a><span data-ttu-id="af521-132">信任的 IP 位址</span><span class="sxs-lookup"><span data-stu-id="af521-132">Trusted IP address</span></span>

<span data-ttu-id="af521-133">信任的 IP 位址是商業網路的網際網路外部 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="af521-133">Trusted IP addresses are the internet external IP addresses of the enterprise network.</span></span> <span data-ttu-id="af521-134">他們先判斷使用者的端點是否位於公司網路內，然後再檢查特定網站相符專案。</span><span class="sxs-lookup"><span data-stu-id="af521-134">They determine whether the user's endpoint is inside the corporate network before checking for a specific site match.</span></span>

<span data-ttu-id="af521-135">如果使用者的外部 IP 位址符合信任 IP 位址清單中的 IP 位址，雲端語音功能會檢查以判斷使用者端點所在的內部子網。</span><span class="sxs-lookup"><span data-stu-id="af521-135">If the user's external IP address matches an IP address that's in the trusted IP address list, the cloud voice feature checks to determine the internal subnet where the user's endpoint is located.</span></span> <span data-ttu-id="af521-136">您可以根據 IPv4 或 IPv6 IP 位址進行比對，並視要送往網路設定之 IP 封包的格式而定。</span><span class="sxs-lookup"><span data-stu-id="af521-136">A match can be made against either IPv4 or IPv6 IP addresses and is dependent upon the format of the IP packet sent to the network settings.</span></span> <span data-ttu-id="af521-137"> (如果公用 IP 位址同時有 IPv4 和 IPv6，您必須同時將兩者新增為信任的 IP 位址。) </span><span class="sxs-lookup"><span data-stu-id="af521-137">(If a public IP address has both IPv4 and IPv6, you must add both as trusted IP addresses.)</span></span>

<span data-ttu-id="af521-138">如果使用者的外部 IP 位址與信任 IP 位址清單中的 IP 位址不相符，端點會分類為位於未知位置。</span><span class="sxs-lookup"><span data-stu-id="af521-138">If the user's external IP address doesn't match an IP address that's in the trusted IP address list, the endpoint is classified as being at an unknown location.</span></span>

> [!Important]
> <span data-ttu-id="af521-139">雲端 Proxy 服務部署不支援網路設定設定檢查，這些部署會修改來自Teams IP 位址。</span><span class="sxs-lookup"><span data-stu-id="af521-139">Network configuration setting lookups are not supported with cloud proxy service deployments that modify the source IP addresses from Teams clients.</span></span>
