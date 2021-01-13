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
description: 瞭解您必須針對直接路由及增強緊急服務的 Location-Based 路由進行設定的網路設定。
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
- m365initiative-voice
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 10547a99b0e63585ae39cc90a5b0cf573a9c94e3
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49834333"
---
# <a name="network-settings-for-cloud-voice-features-in-microsoft-teams"></a><span data-ttu-id="5b579-103">Microsoft 團隊中雲端語音功能的網路設定</span><span class="sxs-lookup"><span data-stu-id="5b579-103">Network settings for cloud voice features in Microsoft Teams</span></span>

<span data-ttu-id="5b579-104">瞭解網路區域、網路網站、網路子網和信任的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="5b579-104">Learn about network regions, network sites, network subnets, and trusted IP addresses.</span></span> <span data-ttu-id="5b579-105">這些條款與概念在整個雲端語音檔中都是用來進行 [直接路由](location-based-routing-plan.md) 和 [動態緊急通話](configure-dynamic-emergency-calling.md)的以位置為基礎的路由。</span><span class="sxs-lookup"><span data-stu-id="5b579-105">These terms and concepts are used throughout our cloud voice documentation for [Location-Based Routing for Direct Routing](location-based-routing-plan.md) and [dynamic emergency calling](configure-dynamic-emergency-calling.md).</span></span> <span data-ttu-id="5b579-106">如果您要在組織中部署這些雲端功能，您必須設定網路設定，以便與 Microsoft 團隊中的這些功能搭配使用。</span><span class="sxs-lookup"><span data-stu-id="5b579-106">If you're deploying these cloud features in your organization, you must configure network settings for use with these features in Microsoft Teams.</span></span>

<span data-ttu-id="5b579-107">本文提供 Location-Based 路由及動態緊急通話的一般網路設定的概覽。</span><span class="sxs-lookup"><span data-stu-id="5b579-107">This article gives you an overview of the network settings that are common to Location-Based Routing and dynamic emergency calling.</span></span> <span data-ttu-id="5b579-108">視您部署的雲端語音功能和功能而定，您可以設定部分或所有的設定。</span><span class="sxs-lookup"><span data-stu-id="5b579-108">Depending on the cloud voice feature and capability that you're deploying, you configure some or all these settings.</span></span> <span data-ttu-id="5b579-109">如需如何設定這些設定的步驟，請參閱在 [團隊中管理雲端功能的網路拓撲](manage-your-network-topology.md)。</span><span class="sxs-lookup"><span data-stu-id="5b579-109">For steps on how to configure these settings, see [Manage your network topology for cloud features in Teams](manage-your-network-topology.md).</span></span>

> [!NOTE]
> <span data-ttu-id="5b579-110">此功能的設定主題中記錄了網路設定的任何特定功能需求。</span><span class="sxs-lookup"><span data-stu-id="5b579-110">Any feature-specific requirements for network settings are documented in the configuration topics for that feature.</span></span>

## <a name="network-region"></a><span data-ttu-id="5b579-111">網路區域</span><span class="sxs-lookup"><span data-stu-id="5b579-111">Network region</span></span>

<span data-ttu-id="5b579-112">網路區域包含一個網路網站集合。</span><span class="sxs-lookup"><span data-stu-id="5b579-112">A network region contains a collection of network sites.</span></span> <span data-ttu-id="5b579-113">它跨多個地理區域相互互連網路的各個部分。</span><span class="sxs-lookup"><span data-stu-id="5b579-113">It interconnects various parts of a network across multiple geographic areas.</span></span> <span data-ttu-id="5b579-114">例如，如果您的組織有許多位於印度的網站，您可以選擇將 "印度" 指定為網路區域。</span><span class="sxs-lookup"><span data-stu-id="5b579-114">For example, if your organization has many sites located in India, you may choose to designate "India" as a network region.</span></span> <span data-ttu-id="5b579-115">每個網路網站都必須與一個網路區域建立關聯。</span><span class="sxs-lookup"><span data-stu-id="5b579-115">Each network site must be associated with a network region.</span></span>

<span data-ttu-id="5b579-116">Location-Based 路由以進行直接路由及增強的緊急服務，就能共用相同的網路區域。</span><span class="sxs-lookup"><span data-stu-id="5b579-116">The same network regions are shared by Location-Based Routing for Direct Routing and enhanced emergency services.</span></span> <span data-ttu-id="5b579-117">如果您已經為一個功能建立了網路區域，您就不需要為其他功能建立新的網路區域。</span><span class="sxs-lookup"><span data-stu-id="5b579-117">If you already created network regions for one feature, you don't have to create new network regions for the other feature.</span></span>

## <a name="network-site"></a><span data-ttu-id="5b579-118">網路網站</span><span class="sxs-lookup"><span data-stu-id="5b579-118">Network site</span></span>

<span data-ttu-id="5b579-119">網路網站代表貴組織有實體場所（例如辦公室、一組建築物或校園）的位置。</span><span class="sxs-lookup"><span data-stu-id="5b579-119">A network site represents a location where your organization has a physical venue, such as an office, a set of buildings, or a campus.</span></span> <span data-ttu-id="5b579-120">網路網站定義為 IP 子網的集合。</span><span class="sxs-lookup"><span data-stu-id="5b579-120">Network sites are defined as a collection of IP subnets.</span></span> <span data-ttu-id="5b579-121">每個網路網站都必須與一個網路區域建立關聯。</span><span class="sxs-lookup"><span data-stu-id="5b579-121">Each network site must be associated with a network region.</span></span>

<span data-ttu-id="5b579-122">您也可以使用網路網站來啟用和設定緊急通話。</span><span class="sxs-lookup"><span data-stu-id="5b579-122">You can also use network sites to enable and configure emergency calling.</span></span>

## <a name="network-subnet"></a><span data-ttu-id="5b579-123">網路子網上</span><span class="sxs-lookup"><span data-stu-id="5b579-123">Network subnet</span></span>

<span data-ttu-id="5b579-124">每個子網都必須與特定的網路網站相關聯。</span><span class="sxs-lookup"><span data-stu-id="5b579-124">Each subnet must be associated with a specific network site.</span></span> <span data-ttu-id="5b579-125">用戶端的位置是根據網路子網和相關的網路網站來決定。</span><span class="sxs-lookup"><span data-stu-id="5b579-125">A client's location is determined based on the network subnet and the associated network site.</span></span> <span data-ttu-id="5b579-126">您可以將多個子網與同一個網路網站建立關聯，但無法將多個網站與同一個子網建立關聯。</span><span class="sxs-lookup"><span data-stu-id="5b579-126">You can associate multiple subnets with the same network site but you can't associate multiple sites with the same subnet.</span></span>

<span data-ttu-id="5b579-127">子網資訊可用來決定啟動新的會話時，端點所在的網路網站。</span><span class="sxs-lookup"><span data-stu-id="5b579-127">Subnet information is used to determine the network site on which an endpoint is located when a new session is initiated.</span></span> <span data-ttu-id="5b579-128">當會話中每一方的位置已知時，雲端語音功能可以套用該資訊來決定如何處理撥號設定或路由。</span><span class="sxs-lookup"><span data-stu-id="5b579-128">When the location of each party in a session is known, the cloud voice feature can apply that information to determine how to handle call setup or routing.</span></span>

<span data-ttu-id="5b579-129">針對每個網路網站，請與您的網路系統管理員合作，以判斷指派給每個網路網站的 IP 子網。</span><span class="sxs-lookup"><span data-stu-id="5b579-129">For each network site, work with your network admin to determine which IP subnets are assigned to each network site.</span></span> <span data-ttu-id="5b579-130">例如，您可以將下列 IP 子網指派給北美地區的紐約網站： 172.29.80.0/23、157.57.216.0/25、172.29.91.0/23、172.29.81.0/24。</span><span class="sxs-lookup"><span data-stu-id="5b579-130">For example, the New York site in the North America region can be assigned the following IP subnets: 172.29.80.0/23, 157.57.216.0/25, 172.29.91.0/23, 172.29.81.0/24.</span></span> <span data-ttu-id="5b579-131">如果王俊元是在底特律中使用，請前往紐約 office 進行訓練，然後開啟他的電腦並聯機到網路上，他的電腦將會取得 IP 位址，在為紐約所指派的四個範圍其中之一，例如172.29.80.103。</span><span class="sxs-lookup"><span data-stu-id="5b579-131">If Bob, who usually works in Detroit, travels to the New York office for training, turns on his computer and connects to the network, his computer will get an IP address in one of the four ranges that are allocated for New York, for example, 172.29.80.103.</span></span>

## <a name="trusted-ip-address"></a><span data-ttu-id="5b579-132">信任的 IP 位址</span><span class="sxs-lookup"><span data-stu-id="5b579-132">Trusted IP address</span></span>

<span data-ttu-id="5b579-133">[信任的 IP 位址] 是商業網路的網際網路外部 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="5b579-133">Trusted IP addresses are the internet external IP addresses of the enterprise network.</span></span> <span data-ttu-id="5b579-134">在檢查特定網站相符前，他們會判斷使用者的端點是否在公司網路內。</span><span class="sxs-lookup"><span data-stu-id="5b579-134">They determine whether the user's endpoint is inside the corporate network before checking for a specific site match.</span></span>

<span data-ttu-id="5b579-135">如果使用者的外部 IP 位址與 [信任的 IP 位址] 清單中的 IP 位址相符，雲端語音功能會進行檢查，以判斷使用者端點所在的內部子網。</span><span class="sxs-lookup"><span data-stu-id="5b579-135">If the user's external IP address matches an IP address that's in the trusted IP address list, the cloud voice feature checks to determine the internal subnet where the user's endpoint is located.</span></span> <span data-ttu-id="5b579-136">您可以針對 IPv4 或 IPv6 IP 位址進行相符，並視傳送至網路設定的 IP 資料包格式而定。</span><span class="sxs-lookup"><span data-stu-id="5b579-136">A match can be made against either IPv4 or IPv6 IP addresses and is dependent upon the format of the IP packet sent to the network settings.</span></span> <span data-ttu-id="5b579-137"> (如果公用 IP 位址同時具有 IPv4 與 IPv6，您必須將兩者都新增為信任的 IP 位址。 ) </span><span class="sxs-lookup"><span data-stu-id="5b579-137">(If a public IP address has both IPv4 and IPv6, you must add both as trusted IP addresses.)</span></span>

<span data-ttu-id="5b579-138">如果使用者的外部 IP 位址與 [信任的 IP 位址] 清單中的 IP 位址不相符，該端點會分類為未知位置。</span><span class="sxs-lookup"><span data-stu-id="5b579-138">If the user's external IP address doesn't match an IP address that's in the trusted IP address list, the endpoint is classified as being at an unknown location.</span></span>
