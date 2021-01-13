---
title: 在商務用 Skype Server 中規劃 Enterprise Voice
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
ms.assetid: fd8d5867-0ac9-47f8-94f0-1c3ee5e25575
description: 商務用 Skype Server 中的企業語音規劃基礎知識，包括網站、地區、網站間的網路連結，以及評估語音使用流量。
ms.openlocfilehash: 8f10eed8dfcfa7a8878b673ab76fd4d1fd40cc29
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825673"
---
# <a name="plan-for-enterprise-voice-in-skype-for-business-server"></a><span data-ttu-id="b5d95-103">在商務用 Skype Server 中規劃 Enterprise Voice</span><span class="sxs-lookup"><span data-stu-id="b5d95-103">Plan for Enterprise Voice in Skype for Business Server</span></span>
 
<span data-ttu-id="b5d95-104">商務用 Skype Server 中的企業語音規劃基礎知識，包括網站、地區、網站間的網路連結，以及評估語音使用流量。</span><span class="sxs-lookup"><span data-stu-id="b5d95-104">Enterprise Voice planning basics in Skype for Business Server, including sites, regions, network links between sites, and estimating voice usage traffic.</span></span>
  
<span data-ttu-id="b5d95-105">Enterprise Voice 的部署程式取決於您現有的拓撲、基礎結構，以及您想要支援的 Enterprise Voice 功能。</span><span class="sxs-lookup"><span data-stu-id="b5d95-105">The deployment process for Enterprise Voice depends on your existing topology, infrastructure, and the Enterprise Voice functionality that you want to support.</span></span> <span data-ttu-id="b5d95-106">必要的程式取決於您選擇的功能，但是還有其他的規劃考慮，您必須以高層次進行。</span><span class="sxs-lookup"><span data-stu-id="b5d95-106">The required procedures will depend on what features you choose, but there are other planning considerations that you must make at a high level.</span></span>
  
<span data-ttu-id="b5d95-107">一般來說，請考慮您要部署的網站類型和數目、每個網站的通話量、每個網站的網路連結類型、連接網站的網路連結類型、您是否想要為每個網站提供冗余及容錯移轉語音功能，以及是否要使用現有的 PBX 裝置。</span><span class="sxs-lookup"><span data-stu-id="b5d95-107">In general, consider the type and number of sites that you want to deploy and their geographical locations, the call volume at each site, the types of network links that connect sites, whether you want to provide redundancy and failover for voice functionality for each site, and whether you want to use existing PBX equipment.</span></span> <span data-ttu-id="b5d95-108">在規劃商務用 Skype 伺服器做為整體時，您應該考慮下列一些事項（如高可用性）。</span><span class="sxs-lookup"><span data-stu-id="b5d95-108">There are certain considerations, such as high availability, that you should consider when you plan for Skype for Business Server as a whole.</span></span> <span data-ttu-id="b5d95-109">您會視需要在本節的主題中討論這些考慮。</span><span class="sxs-lookup"><span data-stu-id="b5d95-109">These considerations are discussed in topics throughout this section, as needed.</span></span>
  
## <a name="sites-and-regions"></a><span data-ttu-id="b5d95-110">網站與地區</span><span class="sxs-lookup"><span data-stu-id="b5d95-110">Sites and regions</span></span>

<span data-ttu-id="b5d95-111">首先，識別您的拓撲中的網站，您將在其中部署企業語音和這些網站所屬的網路地區。</span><span class="sxs-lookup"><span data-stu-id="b5d95-111">First, identify the sites in your topology where you will deploy Enterprise Voice and the network regions to which those sites belong.</span></span> <span data-ttu-id="b5d95-112">明確而言，請考量您要如何為各個網站提供公用交換電話網路 (PSTN) 連線。</span><span class="sxs-lookup"><span data-stu-id="b5d95-112">In particular, consider how you will provide public switched telephone network (PSTN) connectivity to each site.</span></span> <span data-ttu-id="b5d95-113">就管理性與物流的考量而言，這些網站的所屬地區可能會是決定性因素。</span><span class="sxs-lookup"><span data-stu-id="b5d95-113">For manageability and logistical reasons, the regions to which these sites belong can be a deciding factor.</span></span> <span data-ttu-id="b5d95-114">決定要在本機部署閘道的位置，Survivable 分支裝置 (Sba) 部署所在的位置，以及您可以在本機或在中央網站) 設定 SIP 主幹 ( (ITSP) 。</span><span class="sxs-lookup"><span data-stu-id="b5d95-114">Decide where gateways will be deployed locally, where Survivable Branch Appliances (SBAs) will be deployed, and where you can configure SIP trunks (either locally or at the central site) to an Internet telephony service provider (ITSP).</span></span>
  
## <a name="network-links-between-sites"></a><span data-ttu-id="b5d95-115">網站間的網路連結</span><span class="sxs-lookup"><span data-stu-id="b5d95-115">Network links between sites</span></span>

<span data-ttu-id="b5d95-116">您也需要考慮您期望在中央網站與其分支網站之間之網路連結的頻寬使用量。</span><span class="sxs-lookup"><span data-stu-id="b5d95-116">You also need to consider the bandwidth usage that you expect on the network links between your central site and its branch sites.</span></span> <span data-ttu-id="b5d95-117">如果您有或想要在網站之間部署彈性的 WAN 連結，建議您在每個分支網站上部署閘道，以提供本機直接向內撥號 (已) 使用者在這些網站上終止。</span><span class="sxs-lookup"><span data-stu-id="b5d95-117">If you have, or plan to deploy, resilient WAN links between sites, we recommend that you deploy a gateway at each branch site to provide local direct inward dial (DID) termination for users at those sites.</span></span> <span data-ttu-id="b5d95-118">如果您有彈性的 WAN 連結，但 WAN 連結的頻寬可能受限，請為該連結設定通話許可控制。</span><span class="sxs-lookup"><span data-stu-id="b5d95-118">If you have resilient WAN links, but the bandwidth on a WAN link is likely to be constrained, configure call admission control for that link.</span></span> <span data-ttu-id="b5d95-119">如果您沒有可恢復的 WAN 連結，請在分支網站上裝載低於1000的使用者，而且沒有本機訓練有素的商務用 Skype 伺服器管理員，我們建議您在分支網站上部署 Survivable 分支裝置。</span><span class="sxs-lookup"><span data-stu-id="b5d95-119">If you do not have resilient WAN links, host fewer than 1000 users at your branch site, and do not have local trained Skype for Business Server administrators available, we recommend that you deploy a Survivable Branch Appliance at the branch site.</span></span> <span data-ttu-id="b5d95-120">如果您在分支網站上主持1000和5000使用者、缺乏彈性的 WAN 連線，且有訓練有素的商務用 Skype 伺服器管理員，建議您在分支網站上使用小型閘道部署 Survivable 分支伺服器。</span><span class="sxs-lookup"><span data-stu-id="b5d95-120">If you host between 1000 and 5000 users at your branch site, lack a resilient WAN connection, and have trained Skype for Business Server administrators available, we recommend that you deploy a Survivable Branch Server with a small gateway at the branch site.</span></span> <span data-ttu-id="b5d95-121">如果您有支援媒體旁路的閘道對等，也請考慮對受限的連結啟用媒體旁路。</span><span class="sxs-lookup"><span data-stu-id="b5d95-121">Consider also enabling media bypass on constrained links if you have a gateway peer that supports media bypass.</span></span>
  
## <a name="estimating-voice-usage-and-traffic"></a><span data-ttu-id="b5d95-122">評估語音使用方式和流量</span><span class="sxs-lookup"><span data-stu-id="b5d95-122">Estimating voice usage and traffic</span></span>

<span data-ttu-id="b5d95-123">Microsoft Lync Server 2013，規劃工具使用下列度量，評估每個網站的使用者流量，以及支援該流量所需的埠數目。</span><span class="sxs-lookup"><span data-stu-id="b5d95-123">The Microsoft Lync Server 2013, Planning Tool uses the following metric to estimate user traffic at each site and the number of ports that are required to support that traffic.</span></span>
  
> <span data-ttu-id="b5d95-124">針對 **輕型流量** (每位使用者每小時一個 PSTN 通話)，估計每個連接埠 15 位使用者。</span><span class="sxs-lookup"><span data-stu-id="b5d95-124">For **Light traffic** (one PSTN call per user per hour), figure 15 users per port.</span></span>
> 
> <span data-ttu-id="b5d95-125">針對 **中型流量** (每位使用者每小時兩個 PSTN 通話)，估計每個連接埠 10 位使用者。</span><span class="sxs-lookup"><span data-stu-id="b5d95-125">For **Medium traffic** (2 PSTN calls per user per hour), figure 10 users per port.</span></span>
> 
> <span data-ttu-id="b5d95-126">針對 **重型流量** (每位使用者每小時三個以上的 PSTN 通話)，估計每個連接埠 5 位使用者。</span><span class="sxs-lookup"><span data-stu-id="b5d95-126">For **Heavy traffic** (3 or more PSTN per user calls per hour), figure 5 users per port.</span></span>
    
<span data-ttu-id="b5d95-127">接下來的埠數目會決定所需的轉送伺服器和閘道數目。</span><span class="sxs-lookup"><span data-stu-id="b5d95-127">The number of ports in turn determines the number of Mediation Servers and gateways that will be required.</span></span> <span data-ttu-id="b5d95-128">公用交換電話網路 (PSTN) 閘道，大多數的組織都會考慮從兩個埠的大小部署至多達960埠的範圍。</span><span class="sxs-lookup"><span data-stu-id="b5d95-128">The public switched telephone network (PSTN) gateways that most organizations consider deploying range in size from 2 ports to as many as 960 ports.</span></span> <span data-ttu-id="b5d95-129"> (甚至會有較大的閘道，但是主要是由電話語音服務提供者使用。 ) </span><span class="sxs-lookup"><span data-stu-id="b5d95-129">(There are even larger gateways, but these are used mainly by telephony service providers.)</span></span>
  
<span data-ttu-id="b5d95-p106">例如，有 10,000 位使用者及中型流量的組織需要 1000 個連接埠。需要的閘道數目會等於閘道總容量所決定的必要連接埠總數。</span><span class="sxs-lookup"><span data-stu-id="b5d95-p106">For example, an organization with 10,000 users and medium traffic would require 1000 ports. The number of gateways required would equal the total number of ports required as determined by the total capacity of the gateways.</span></span>
  
## <a name="components-features-and-options-of-enterprise-voice"></a><span data-ttu-id="b5d95-132">Enterprise Voice 的元件、功能及選項</span><span class="sxs-lookup"><span data-stu-id="b5d95-132">Components, features, and options of Enterprise Voice</span></span>

<span data-ttu-id="b5d95-133">如需規劃企業語音部署的詳細資訊，請參閱下列各節。</span><span class="sxs-lookup"><span data-stu-id="b5d95-133">See the following sections for more information on planning your Enterprise Voice deployment.</span></span>
  
- [<span data-ttu-id="b5d95-134">商務用 Skype Server 中的 Enterprise Voice 所需元件</span><span class="sxs-lookup"><span data-stu-id="b5d95-134">Components required for Enterprise Voice in Skype for Business Server</span></span>](components-required-for-enterprise-voice.md)
    
- [<span data-ttu-id="b5d95-135">在商務用 Skype Server 中規劃 PSTN 連線能力</span><span class="sxs-lookup"><span data-stu-id="b5d95-135">Plan for PSTN connectivity in Skype for Business Server</span></span>](pstn-connectivity-0.md)
    
- [<span data-ttu-id="b5d95-136">商務用 Skype Server 中的高級 Enterprise Voice 功能的網路設定</span><span class="sxs-lookup"><span data-stu-id="b5d95-136">Network settings for the advanced Enterprise Voice features in Skype for Business Server</span></span>](network-settings-for-advanced-features.md)
    
- [<span data-ttu-id="b5d95-137">在商務用 Skype Server 中規劃通話許可控制</span><span class="sxs-lookup"><span data-stu-id="b5d95-137">Plan for call admission control in Skype for Business Server</span></span>](call-admission-control.md)
    
- [<span data-ttu-id="b5d95-138">在商務用 Skype Server 中規劃緊急服務</span><span class="sxs-lookup"><span data-stu-id="b5d95-138">Plan for emergency services in Skype for Business Server</span></span>](emergency-services.md)
    
- [<span data-ttu-id="b5d95-139">在商務用 Skype 中規劃媒體旁路</span><span class="sxs-lookup"><span data-stu-id="b5d95-139">Plan for media bypass in Skype for Business</span></span>](media-bypass.md)
    
- [<span data-ttu-id="b5d95-140">使用商務用 Skype 規劃私人電話線</span><span class="sxs-lookup"><span data-stu-id="b5d95-140">Plan for private telephone lines with Skype for Business</span></span>](private-telephone-lines.md)
    
- [<span data-ttu-id="b5d95-141">規劃商務用 Skype 中的 Location-Based 路由</span><span class="sxs-lookup"><span data-stu-id="b5d95-141">Plan for Location-Based Routing in Skype for Business</span></span>](location-based-routing.md)
    
- [<span data-ttu-id="b5d95-142">在商務用 Skype 中規劃通話管理功能</span><span class="sxs-lookup"><span data-stu-id="b5d95-142">Plan for call management features in Skype for Business</span></span>](call-management-features.md)
    
- [<span data-ttu-id="b5d95-143">在商務用 Skype Server 中規劃 Enterprise Voice 韌性</span><span class="sxs-lookup"><span data-stu-id="b5d95-143">Plan for Enterprise Voice resiliency in Skype for Business Server</span></span>](enterprise-voice-resiliency.md)
    

