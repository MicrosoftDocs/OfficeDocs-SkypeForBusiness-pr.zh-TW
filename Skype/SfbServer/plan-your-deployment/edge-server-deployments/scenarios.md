---
title: 商務用 Skype Server 中的邊緣伺服器案例
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
audience: ITPro
ms.topic: conceptual
manager: serdars
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 7b9c211b-deb0-479d-b184-973f08b96d07
description: 摘要：請查看這些案例，協助您規劃商務用 Skype Server 中的邊緣伺服器拓撲。
ms.openlocfilehash: a1d721ffabb78985d90848784cd587bda96300d5
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41803353"
---
# <a name="edge-server-scenarios-in-skype-for-business-server"></a><span data-ttu-id="b1122-103">商務用 Skype Server 中的邊緣伺服器案例</span><span class="sxs-lookup"><span data-stu-id="b1122-103">Edge Server scenarios in Skype for Business Server</span></span>
 
<span data-ttu-id="b1122-104">**摘要：** 請複習這些案例，協助您規劃商務用 Skype Server 中的邊緣伺服器拓撲。</span><span class="sxs-lookup"><span data-stu-id="b1122-104">**Summary:** Review these scenarios to help you plan your Edge Server topology in Skype for Business Server.</span></span>
  
<span data-ttu-id="b1122-105">我們有一些案例圖表，可協助在您想要實施哪種商務用 Skype Server Edge 伺服器拓撲中進行視覺化和決定。</span><span class="sxs-lookup"><span data-stu-id="b1122-105">We have some scenarios diagrams to assist with visualizing and deciding on what Skype for Business Server Edge Server topology you want to implement.</span></span> <span data-ttu-id="b1122-106">挑選好的候選方案之後，您就可以開始瞭解您需要解決的環境需求。</span><span class="sxs-lookup"><span data-stu-id="b1122-106">Once you've picked a good candidate, you can go read up on the environmental requirements you'll need to address.</span></span> <span data-ttu-id="b1122-107">下列是適用于任何案例，因此我們先將它提及。</span><span class="sxs-lookup"><span data-stu-id="b1122-107">The following is applicable to any of the scenarios, so we're mentioning it first.</span></span>
  
<span data-ttu-id="b1122-108">這些數位僅針對範例所示（也就是包含範例 IPv4 與 IPv6 資料），不代表實際的通訊流程，而是您可能的流量的高層次視圖。</span><span class="sxs-lookup"><span data-stu-id="b1122-108">These figures, which are shown for example purposes only (and as such contains sample IPv4 and IPv6 data), don't represent the actual communication flow, but rather a high-level view of your possible traffic.</span></span> <span data-ttu-id="b1122-109">您也可以在下列每個案例的埠圖表中看到埠詳細資料。</span><span class="sxs-lookup"><span data-stu-id="b1122-109">Port details can also be seen in the Port diagrams for each scenario below.</span></span>
  
<span data-ttu-id="b1122-110">圖表會針對內部介面與 .net （也就是樣本圖）顯示 .com;當然，當您要將自己的最終邊緣方案放在一起時，您自己的專案可能會有很大的差異。</span><span class="sxs-lookup"><span data-stu-id="b1122-110">The diagrams show .com for the external interface and .net for the internal, which is also sample material; of course your own entries may be quite different when you're putting together your own final Edge plan.</span></span>
  
<span data-ttu-id="b1122-111">在任何圖表中，我們不會包含主管（這是一個選用元件），但您可以單獨閱讀此資訊（在其他規劃主題中提到）。</span><span class="sxs-lookup"><span data-stu-id="b1122-111">We don't include the Director (which is an optional component) in any of the diagrams, but you can read about that separately (it's mentioned in other Planning topics).</span></span>
  
<span data-ttu-id="b1122-112">如前所述，圖表中有範例 IPv6 資料。</span><span class="sxs-lookup"><span data-stu-id="b1122-112">As noted above, there is sample IPv6 data in the diagrams.</span></span> <span data-ttu-id="b1122-113">在[商務用 Skype server 中規劃 Edge 伺服器部署](edge-server-deployments.md)的大部分檔將會參照 IPv4，但如果您想要使用 IPv6，您肯定會受到支援。</span><span class="sxs-lookup"><span data-stu-id="b1122-113">Most of the documentation in [Plan for Edge Server deployments in Skype for Business Server](edge-server-deployments.md) will refer to IPv4, but you are certainly supported if you want to use IPv6.</span></span> <span data-ttu-id="b1122-114">請注意，您在指派的位址空間中需要 IPv6 位址，而且它們必須與 IPv4 Ip 一樣使用內部和外部定址。</span><span class="sxs-lookup"><span data-stu-id="b1122-114">Note that you'll need IPv6 addresses in your assigned address space, and they'll need to work with internal and external addressing, as with IPv4 IPs.</span></span> <span data-ttu-id="b1122-115">您可以在 Windows 中使用雙堆疊功能，這是適用于 IPv4 和 IPv6 的獨立且獨特的網路堆疊。</span><span class="sxs-lookup"><span data-stu-id="b1122-115">You can, thanks to Windows, employ the dual stack feature, which is a separate and distinct network stack for IPv4 and IPv6.</span></span> <span data-ttu-id="b1122-116">如果您需要的話，這會讓您同時指派 IPv4 與 IPv6 位址。</span><span class="sxs-lookup"><span data-stu-id="b1122-116">This will, if you need, allow you to assign IPv4 and IPv6 addresses concurrently.</span></span>
  
<span data-ttu-id="b1122-117">NAT 裝置允許使用 NAT64 （IPv6 到 IPv4）與 NAT66 （IPv6 到 IPv6）），而且這對搭配商務用 Skype Server 而言是有效的。</span><span class="sxs-lookup"><span data-stu-id="b1122-117">There are NAT devices that allow for NAT64 (IPv6 to IPv4) and NAT66 (IPv6 to IPv6)), and this is valid for use with Skype for Business Server.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="b1122-118">如果您使用的是「通話許可控制」（CAC），則必須在內部介面上使用 IPv4 才能運作。</span><span class="sxs-lookup"><span data-stu-id="b1122-118">If you're using Call Admission Control (CAC) you do have to use IPv4 on the internal interface for it to work.</span></span> 
  
## <a name="single-consolidated-skype-for-business-server-edge-server-with-private-ip-addresses-and-nat"></a><span data-ttu-id="b1122-119">單一整合的商務用 Skype Server Edge 伺服器（含私人 IP 位址和 NAT）</span><span class="sxs-lookup"><span data-stu-id="b1122-119">Single consolidated Skype for Business Server Edge Server with private IP addresses and NAT</span></span>

<span data-ttu-id="b1122-120">在這個案例中，沒有高可用性的選項。</span><span class="sxs-lookup"><span data-stu-id="b1122-120">With this scenario, there is no option for high availability.</span></span> <span data-ttu-id="b1122-121">這將意味著您在硬體上的花費較少，且部署更簡單。</span><span class="sxs-lookup"><span data-stu-id="b1122-121">This will mean you spend less on hardware and have a simpler deployment.</span></span> <span data-ttu-id="b1122-122">如果必須具備高可用性，請參閱下方的伸縮合併案例。</span><span class="sxs-lookup"><span data-stu-id="b1122-122">If high availability is a must, check out the Scaled consolidated scenarios below.</span></span>
  
![使用 NAT 的單一綜合邊緣與專用 IP 的邊緣案例](../../media/Plan_LyncServer_Edge_Scenario_SingleConsolidatedEdgePrivateIP.jpg)
  
### <a name="port-diagram"></a><span data-ttu-id="b1122-124">埠圖表</span><span class="sxs-lookup"><span data-stu-id="b1122-124">Port diagram</span></span>

<span data-ttu-id="b1122-125">我們也為單一整合邊緣伺服器的埠建立圖表。</span><span class="sxs-lookup"><span data-stu-id="b1122-125">We also have a diagram for ports for single consolidated Edge Servers.</span></span>
  
![Edge 案例的網路周長單一合併邊緣](../../media/Plan_LyncServer_Edge_NetPerimeter_SingleConsolidatedEdge.jpg)
  
## <a name="single-consolidated-skype-for-business-server-edge-server-with-public-ip-addresses"></a><span data-ttu-id="b1122-127">單一整合的商務用 Skype Server Edge 伺服器與公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="b1122-127">Single consolidated Skype for Business Server Edge Server with public IP addresses</span></span>

<span data-ttu-id="b1122-128">在這個案例中，沒有高可用性的選項。</span><span class="sxs-lookup"><span data-stu-id="b1122-128">With this scenario, there is no option for high availability.</span></span> <span data-ttu-id="b1122-129">這將意味著您在硬體上的花費較少，且部署更簡單。</span><span class="sxs-lookup"><span data-stu-id="b1122-129">This will mean you spend less on hardware and have a simpler deployment.</span></span> <span data-ttu-id="b1122-130">如果必須具備高可用性，請參閱下方的伸縮合併案例。</span><span class="sxs-lookup"><span data-stu-id="b1122-130">If high availability is a must, check out the Scaled consolidated scenarios below.</span></span>
  
![含公用 IP 的單一合併邊緣的邊緣案例](../../media/Plan_LyncServer_Edge_Scenario_SingleConsolidatedEdgePublicIP.jpg)
  
### <a name="port-diagram"></a><span data-ttu-id="b1122-132">埠圖表</span><span class="sxs-lookup"><span data-stu-id="b1122-132">Port diagram</span></span>

<span data-ttu-id="b1122-133">我們也為單一整合邊緣伺服器的埠建立圖表。</span><span class="sxs-lookup"><span data-stu-id="b1122-133">We also have a diagram for ports for single consolidated Edge Servers.</span></span>
  
![Edge 案例的網路周長單一合併邊緣](../../media/Plan_LyncServer_Edge_NetPerimeter_SingleConsolidatedEdge.jpg)
  
## <a name="scaled-consolidated-skype-for-business-server-edge-pool-with-dns-load-balancing-and-private-ip-addresses-and-nat"></a><span data-ttu-id="b1122-135">已調整整合的商務用 Skype Server Edge 池（含 DNS 負載平衡），以及私人 IP 位址和 NAT</span><span class="sxs-lookup"><span data-stu-id="b1122-135">Scaled consolidated Skype for Business Server Edge pool, with DNS load balancing, and private IP addresses and NAT</span></span>

<span data-ttu-id="b1122-136">在這種情況下，您可以在 Edge 部署中取得高可用性，這可讓您有伸縮性和容錯移轉支援的優點。</span><span class="sxs-lookup"><span data-stu-id="b1122-136">With this scenario, you are able to have high availability in your Edge deployment, which gives you the advantages of scalability and failover support.</span></span>
  
![使用 NAT 調整合並邊緣的邊緣案例、含專用 IP 的 DNS LB](../../media/Plan_LyncServer_Edge_Scenario_ScaledConsolidatedEdgeDNSLBPrivateIP.jpg)
  
### <a name="port-diagram"></a><span data-ttu-id="b1122-138">埠圖表</span><span class="sxs-lookup"><span data-stu-id="b1122-138">Port diagram</span></span>

<span data-ttu-id="b1122-139">我們也有一個使用 DNS 負載平衡來調整整合的邊緣池的圖表。</span><span class="sxs-lookup"><span data-stu-id="b1122-139">We also have a diagram for scaled consolidated Edge pools with DNS load balancing.</span></span>
  
![邊緣案例的網路周邊使用 DNS LB 調整合並的邊緣](../../media/Plan_LyncServer_Edge_NetPerimeter_ScaledConsolidatedEdgeDNSLB.jpg)
  
## <a name="scaled-consolidated-skype-for-business-server-edge-pool-with-dns-load-balancing-and-public-ip-addresses"></a><span data-ttu-id="b1122-141">使用 DNS 負載平衡與公用 IP 位址調整整合的商務用 Skype Server Edge 池</span><span class="sxs-lookup"><span data-stu-id="b1122-141">Scaled consolidated Skype for Business Server Edge pool, with DNS load balancing and public IP addresses</span></span>

<span data-ttu-id="b1122-142">在這種情況下，您可以在 Edge 部署中取得高可用性，這可讓您有伸縮性和容錯移轉支援的優點。</span><span class="sxs-lookup"><span data-stu-id="b1122-142">With this scenario, you are able to have high availability in your Edge deployment, which gives you the advantages of scalability and failover support.</span></span>
  
![已調整合並邊緣的邊緣案例，具有公用 IP 的 DNS LB](../../media/Plan_LyncServer_Edge_Scenario_ScaledConsolidatedEdgeDNSLBPublicIP.jpg)
  
### <a name="port-diagram"></a><span data-ttu-id="b1122-144">埠圖表</span><span class="sxs-lookup"><span data-stu-id="b1122-144">Port diagram</span></span>

<span data-ttu-id="b1122-145">我們也有一個使用 DNS 負載平衡來調整整合的邊緣池的圖表。</span><span class="sxs-lookup"><span data-stu-id="b1122-145">We also have a diagram for scaled consolidated Edge pools with DNS load balancing.</span></span>
  
![邊緣案例的網路周邊使用 DNS LB 調整合並的邊緣](../../media/Plan_LyncServer_Edge_NetPerimeter_ScaledConsolidatedEdgeDNSLB.jpg)
  
## <a name="scaled-consolidated-skype-for-business-server-edge-pool-with-hardware-load-balancing"></a><span data-ttu-id="b1122-147">已調整整合的商務用 Skype Server Edge 池（含硬體負載平衡）</span><span class="sxs-lookup"><span data-stu-id="b1122-147">Scaled consolidated Skype for Business Server Edge pool, with hardware load balancing</span></span>

<span data-ttu-id="b1122-148">在這種情況下，您可以在 Edge 部署中取得高可用性，這可讓您有伸縮性和容錯移轉支援的優點。</span><span class="sxs-lookup"><span data-stu-id="b1122-148">With this scenario, you are able to have high availability in your Edge deployment, which gives you the advantages of scalability and failover support.</span></span>
  
![使用 HLB 調整合並邊緣的邊緣案例](../../media/Plan_LyncServer_Edge_Scenario_ScaledConsolidatedEdgeHLB.jpg)
 
