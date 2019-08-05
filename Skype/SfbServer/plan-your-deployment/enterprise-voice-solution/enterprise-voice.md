---
title: 商務用 Skype Server 中的企業語音方案
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
ms.assetid: fd8d5867-0ac9-47f8-94f0-1c3ee5e25575
description: 商務用 Skype Server 中的企業語音規劃基礎, 包括網站、區域、網站之間的網路連結, 以及估計語音使用方式流量。
ms.openlocfilehash: fdc653404f6b7182086af00e6e788a1d3bd421eb
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36187693"
---
# <a name="plan-for-enterprise-voice-in-skype-for-business-server"></a><span data-ttu-id="029b6-103">商務用 Skype Server 中的企業語音方案</span><span class="sxs-lookup"><span data-stu-id="029b6-103">Plan for Enterprise Voice in Skype for Business Server</span></span>
 
<span data-ttu-id="029b6-104">商務用 Skype Server 中的企業語音規劃基礎, 包括網站、區域、網站之間的網路連結, 以及估計語音使用方式流量。</span><span class="sxs-lookup"><span data-stu-id="029b6-104">Enterprise Voice planning basics in Skype for Business Server, including sites, regions, network links between sites, and estimating voice usage traffic.</span></span>
  
<span data-ttu-id="029b6-105">企業語音的部署程式, 取決於您現有的拓撲、基礎結構, 以及您想要支援的企業語音功能。</span><span class="sxs-lookup"><span data-stu-id="029b6-105">The deployment process for Enterprise Voice depends on your existing topology, infrastructure, and the Enterprise Voice functionality that you want to support.</span></span> <span data-ttu-id="029b6-106">所需的程式取決於您所選擇的功能, 但是您必須在高層次進行其他規劃考慮。</span><span class="sxs-lookup"><span data-stu-id="029b6-106">The required procedures will depend on what features you choose, but there are other planning considerations that you must make at a high level.</span></span>
  
<span data-ttu-id="029b6-107">一般來說, 請考慮您想要部署的網站類型及數量, 以及它們的地理位置、每個網站的通話量、連接網站的網路連結類型, 而無論您是否要為每個使用者提供語音功能的冗余與容錯移轉網站, 以及您是否要使用現有的 PBX 裝置。</span><span class="sxs-lookup"><span data-stu-id="029b6-107">In general, consider the type and number of sites that you want to deploy and their geographical locations, the call volume at each site, the types of network links that connect sites, whether you want to provide redundancy and failover for voice functionality for each site, and whether you want to use existing PBX equipment.</span></span> <span data-ttu-id="029b6-108">在您規劃商務用 Skype Server 作為一個整體時, 必須考慮一些考慮 (例如高可用性)。</span><span class="sxs-lookup"><span data-stu-id="029b6-108">There are certain considerations, such as high availability, that you should consider when you plan for Skype for Business Server as a whole.</span></span> <span data-ttu-id="029b6-109">如有需要, 我們將在本區段的主題中討論這些考慮。</span><span class="sxs-lookup"><span data-stu-id="029b6-109">These considerations are discussed in topics throughout this section, as needed.</span></span>
  
## <a name="sites-and-regions"></a><span data-ttu-id="029b6-110">網站和區域</span><span class="sxs-lookup"><span data-stu-id="029b6-110">Sites and regions</span></span>

<span data-ttu-id="029b6-111">首先, 請在您的拓撲中找出您要部署企業語音的網站, 以及這些網站所屬的網路區域。</span><span class="sxs-lookup"><span data-stu-id="029b6-111">First, identify the sites in your topology where you will deploy Enterprise Voice and the network regions to which those sites belong.</span></span> <span data-ttu-id="029b6-112">具體來說, 請考慮您將如何提供公用的交換電話網絡 (PSTN) 連線至每個網站。</span><span class="sxs-lookup"><span data-stu-id="029b6-112">In particular, consider how you will provide public switched telephone network (PSTN) connectivity to each site.</span></span> <span data-ttu-id="029b6-113">出於易管理性和後勤原因, 這些網站所屬的區域可以是決定因素。</span><span class="sxs-lookup"><span data-stu-id="029b6-113">For manageability and logistical reasons, the regions to which these sites belong can be a deciding factor.</span></span> <span data-ttu-id="029b6-114">決定要在本機部署閘道的位置, 將部署 Survivable 分支裝置 (SBAs), 以及您可以將 SIP trunks (本機或在中央網站) 設定為網際網路電話服務提供者 (ITSP)。</span><span class="sxs-lookup"><span data-stu-id="029b6-114">Decide where gateways will be deployed locally, where Survivable Branch Appliances (SBAs) will be deployed, and where you can configure SIP trunks (either locally or at the central site) to an Internet telephony service provider (ITSP).</span></span>
  
## <a name="network-links-between-sites"></a><span data-ttu-id="029b6-115">網站之間的網路連結</span><span class="sxs-lookup"><span data-stu-id="029b6-115">Network links between sites</span></span>

<span data-ttu-id="029b6-116">您也需要考慮您在中央網站與其分支網站之間的網路連結上預期的頻寬使用量。</span><span class="sxs-lookup"><span data-stu-id="029b6-116">You also need to consider the bandwidth usage that you expect on the network links between your central site and its branch sites.</span></span> <span data-ttu-id="029b6-117">如果您有或想要在網站之間部署彈性 WAN 連結, 建議您在每個分支網站部署一個閘道, 以針對這些網站上的使用者提供本機直向內撥打電話 (已結束)。</span><span class="sxs-lookup"><span data-stu-id="029b6-117">If you have, or plan to deploy, resilient WAN links between sites, we recommend that you deploy a gateway at each branch site to provide local direct inward dial (DID) termination for users at those sites.</span></span> <span data-ttu-id="029b6-118">如果您有彈性 WAN 連結, 但 WAN 連結上的頻寬可能受到限制, 請設定該連結的 [呼叫許可控制]。</span><span class="sxs-lookup"><span data-stu-id="029b6-118">If you have resilient WAN links, but the bandwidth on a WAN link is likely to be constrained, configure call admission control for that link.</span></span> <span data-ttu-id="029b6-119">如果您沒有可復原的 WAN 連結, 請在您的分支網站中主持少於1000個使用者, 而且沒有提供當地訓練有素的商務用 Skype 伺服器管理員, 我們建議您在分支網站上部署 Survivable 分支裝置。</span><span class="sxs-lookup"><span data-stu-id="029b6-119">If you do not have resilient WAN links, host fewer than 1000 users at your branch site, and do not have local trained Skype for Business Server administrators available, we recommend that you deploy a Survivable Branch Appliance at the branch site.</span></span> <span data-ttu-id="029b6-120">如果您是在分支網站上的1000和5000使用者之間主持、缺乏彈性 WAN 連線, 且有訓練有素的商務用 Skype Server 管理員, 我們建議您在分支網站上部署 Survivable 分支伺服器與小型閘道。</span><span class="sxs-lookup"><span data-stu-id="029b6-120">If you host between 1000 and 5000 users at your branch site, lack a resilient WAN connection, and have trained Skype for Business Server administrators available, we recommend that you deploy a Survivable Branch Server with a small gateway at the branch site.</span></span> <span data-ttu-id="029b6-121">如果您有支援媒體旁路的閘道對等, 也可以考慮在受限制的連結上啟用媒體旁路。</span><span class="sxs-lookup"><span data-stu-id="029b6-121">Consider also enabling media bypass on constrained links if you have a gateway peer that supports media bypass.</span></span>
  
## <a name="estimating-voice-usage-and-traffic"></a><span data-ttu-id="029b6-122">評估語音使用方式和流量</span><span class="sxs-lookup"><span data-stu-id="029b6-122">Estimating voice usage and traffic</span></span>

<span data-ttu-id="029b6-123">Microsoft Lync Server 2013、規劃工具會使用下列度量來估計每個網站的使用者流量, 以及支援該流量所需的埠數。</span><span class="sxs-lookup"><span data-stu-id="029b6-123">The Microsoft Lync Server 2013, Planning Tool uses the following metric to estimate user traffic at each site and the number of ports that are required to support that traffic.</span></span>
  
> <span data-ttu-id="029b6-124">對於**輕型流量**(每個使用者每小時一個 PSTN 通話), 請在每個埠上見15個使用者。</span><span class="sxs-lookup"><span data-stu-id="029b6-124">For **Light traffic** (one PSTN call per user per hour), figure 15 users per port.</span></span>
> 
> <span data-ttu-id="029b6-125">針對**中型交通**(每位使用者每小時2個 PSTN 通話), 圖10每個埠的使用者數。</span><span class="sxs-lookup"><span data-stu-id="029b6-125">For **Medium traffic** (2 PSTN calls per user per hour), figure 10 users per port.</span></span>
> 
> <span data-ttu-id="029b6-126">對於**大量流量**(3 個或更多每個使用者每小時的 PSTN 通話), 請依圖5每個埠的使用者。</span><span class="sxs-lookup"><span data-stu-id="029b6-126">For **Heavy traffic** (3 or more PSTN per user calls per hour), figure 5 users per port.</span></span>
    
<span data-ttu-id="029b6-127">接下來的埠數會決定要使用的中繼伺服器和閘道數目。</span><span class="sxs-lookup"><span data-stu-id="029b6-127">The number of ports in turn determines the number of Mediation Servers and gateways that will be required.</span></span> <span data-ttu-id="029b6-128">大多陣列織考慮將範圍從2個埠部署到最多960個埠的公用交換電話網絡 (PSTN) 閘道。</span><span class="sxs-lookup"><span data-stu-id="029b6-128">The public switched telephone network (PSTN) gateways that most organizations consider deploying range in size from 2 ports to as many as 960 ports.</span></span> <span data-ttu-id="029b6-129">(甚至是更大的閘道, 但主要是由電話服務提供者使用。)</span><span class="sxs-lookup"><span data-stu-id="029b6-129">(There are even larger gateways, but these are used mainly by telephony service providers.)</span></span>
  
<span data-ttu-id="029b6-130">例如, 有10000使用者和中型交通的組織需要1000埠。</span><span class="sxs-lookup"><span data-stu-id="029b6-130">For example, an organization with 10,000 users and medium traffic would require 1000 ports.</span></span> <span data-ttu-id="029b6-131">所需的閘道數目會等於由閘道總容量決定所需的埠總數。</span><span class="sxs-lookup"><span data-stu-id="029b6-131">The number of gateways required would equal the total number of ports required as determined by the total capacity of the gateways.</span></span>
  
## <a name="components-features-and-options-of-enterprise-voice"></a><span data-ttu-id="029b6-132">企業語音的元件、功能和選項</span><span class="sxs-lookup"><span data-stu-id="029b6-132">Components, features, and options of Enterprise Voice</span></span>

<span data-ttu-id="029b6-133">如需規劃企業語音部署的詳細資訊, 請參閱下列各節。</span><span class="sxs-lookup"><span data-stu-id="029b6-133">See the following sections for more information on planning your Enterprise Voice deployment.</span></span>
  
- [<span data-ttu-id="029b6-134">商務用 Skype Server 中的企業語音所需元件</span><span class="sxs-lookup"><span data-stu-id="029b6-134">Components required for Enterprise Voice in Skype for Business Server</span></span>](components-required-for-enterprise-voice.md)
    
- [<span data-ttu-id="029b6-135">在商務用 Skype Server 中規劃 PSTN 連通性</span><span class="sxs-lookup"><span data-stu-id="029b6-135">Plan for PSTN connectivity in Skype for Business Server</span></span>](pstn-connectivity-0.md)
    
- <span data-ttu-id="029b6-136">[商務用 Skype Server 中的 [高級企業語音功能] 的網路設定](network-settings-for-advanced-features.md)</span><span class="sxs-lookup"><span data-stu-id="029b6-136">[Network settings for the advanced Enterprise Voice features in Skype for Business Server](network-settings-for-advanced-features.md)</span></span>
    
- [<span data-ttu-id="029b6-137">在商務用 Skype Server 中規劃通話許可控制</span><span class="sxs-lookup"><span data-stu-id="029b6-137">Plan for call admission control in Skype for Business Server</span></span>](call-admission-control.md)
    
- [<span data-ttu-id="029b6-138">在商務用 Skype Server 中規劃緊急服務</span><span class="sxs-lookup"><span data-stu-id="029b6-138">Plan for emergency services in Skype for Business Server</span></span>](emergency-services.md)
    
- [<span data-ttu-id="029b6-139">在商務用 Skype 中規劃媒體旁路</span><span class="sxs-lookup"><span data-stu-id="029b6-139">Plan for media bypass in Skype for Business</span></span>](media-bypass.md)
    
- [<span data-ttu-id="029b6-140">使用商務用 Skype 規劃私人電話線</span><span class="sxs-lookup"><span data-stu-id="029b6-140">Plan for private telephone lines with Skype for Business</span></span>](private-telephone-lines.md)
    
- [<span data-ttu-id="029b6-141">在商務用 Skype 中規劃以位置為基礎的路由</span><span class="sxs-lookup"><span data-stu-id="029b6-141">Plan for Location-Based Routing in Skype for Business</span></span>](location-based-routing.md)
    
- [<span data-ttu-id="029b6-142">規劃商務用 Skype 中的通話管理功能</span><span class="sxs-lookup"><span data-stu-id="029b6-142">Plan for call management features in Skype for Business</span></span>](call-management-features.md)
    
- [<span data-ttu-id="029b6-143">商務用 Skype Server 中的企業語音復原方案</span><span class="sxs-lookup"><span data-stu-id="029b6-143">Plan for Enterprise Voice resiliency in Skype for Business Server</span></span>](enterprise-voice-resiliency.md)
    

