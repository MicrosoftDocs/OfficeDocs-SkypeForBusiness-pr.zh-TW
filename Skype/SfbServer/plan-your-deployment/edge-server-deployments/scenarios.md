---
title: 商務用 Skype Server 中的 Edge Server 案例
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: 摘要：查看這些案例，以協助您在商務用 Skype Server 中規劃 Edge Server 拓撲。
ms.openlocfilehash: cfcc1e8b34576fbec85464fb8d5e35903b47d8ef
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813789"
---
# <a name="edge-server-scenarios-in-skype-for-business-server"></a><span data-ttu-id="8faf2-103">商務用 Skype Server 中的 Edge Server 案例</span><span class="sxs-lookup"><span data-stu-id="8faf2-103">Edge Server scenarios in Skype for Business Server</span></span>
 
<span data-ttu-id="8faf2-104">**摘要：** 請複查這些案例，以協助您規劃商務用 Skype Server 中的 Edge Server 拓撲。</span><span class="sxs-lookup"><span data-stu-id="8faf2-104">**Summary:** Review these scenarios to help you plan your Edge Server topology in Skype for Business Server.</span></span>
  
<span data-ttu-id="8faf2-105">我們有一些案例圖表可協助您進行視覺化及決定要執行的商務用 Skype Server Edge Server 拓撲。</span><span class="sxs-lookup"><span data-stu-id="8faf2-105">We have some scenarios diagrams to assist with visualizing and deciding on what Skype for Business Server Edge Server topology you want to implement.</span></span> <span data-ttu-id="8faf2-106">當您挑選好候選人後，您就可以深入瞭解您必須解決的環境需求。</span><span class="sxs-lookup"><span data-stu-id="8faf2-106">Once you've picked a good candidate, you can go read up on the environmental requirements you'll need to address.</span></span> <span data-ttu-id="8faf2-107">以下是適用于任何案例的情形，因此我們先將其提及。</span><span class="sxs-lookup"><span data-stu-id="8faf2-107">The following is applicable to any of the scenarios, so we're mentioning it first.</span></span>
  
<span data-ttu-id="8faf2-108">這兩個圖只是 (的範例，也包含 IPv4 和 IPv6 資料) 的範例，不代表實際的通訊流程，而是可能流量的高層級視圖。</span><span class="sxs-lookup"><span data-stu-id="8faf2-108">These figures, which are shown for example purposes only (and as such contains sample IPv4 and IPv6 data), don't represent the actual communication flow, but rather a high-level view of your possible traffic.</span></span> <span data-ttu-id="8faf2-109">在下列每個案例的埠圖表中，也可以看到埠的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="8faf2-109">Port details can also be seen in the Port diagrams for each scenario below.</span></span>
  
<span data-ttu-id="8faf2-110">圖表會為內部的外部介面及 .net 顯示 .com，也就是範例材料;當然，當您將自己的最後 Edge 計畫放在一起時，您自己的專案可能會非常不同。</span><span class="sxs-lookup"><span data-stu-id="8faf2-110">The diagrams show .com for the external interface and .net for the internal, which is also sample material; of course your own entries may be quite different when you're putting together your own final Edge plan.</span></span>
  
<span data-ttu-id="8faf2-111">在任何圖表中，我們不會包含 Director (，也就是選用元件) ，但是您可以另行閱讀， (其他規劃主題) 中所述。</span><span class="sxs-lookup"><span data-stu-id="8faf2-111">We don't include the Director (which is an optional component) in any of the diagrams, but you can read about that separately (it's mentioned in other Planning topics).</span></span>
  
<span data-ttu-id="8faf2-112">如以上所述，圖表中有 IPv6 資料的範例。</span><span class="sxs-lookup"><span data-stu-id="8faf2-112">As noted above, there is sample IPv6 data in the diagrams.</span></span> <span data-ttu-id="8faf2-113">在 [商務用 Skype server 中規劃 Edge server 部署](edge-server-deployments.md) 的大部分檔都是指 IPv4，但是如果您想要使用 IPv6，您肯定會受到支援。</span><span class="sxs-lookup"><span data-stu-id="8faf2-113">Most of the documentation in [Plan for Edge Server deployments in Skype for Business Server](edge-server-deployments.md) will refer to IPv4, but you are certainly supported if you want to use IPv6.</span></span> <span data-ttu-id="8faf2-114">請注意，您必須在指派的位址空間中使用 IPv6 位址，而且必須使用內部和外部定址，如使用 IPv4 IPs。</span><span class="sxs-lookup"><span data-stu-id="8faf2-114">Note that you'll need IPv6 addresses in your assigned address space, and they'll need to work with internal and external addressing, as with IPv4 IPs.</span></span> <span data-ttu-id="8faf2-115">您可以借助于 Windows，使用雙棧功能，這是個別且獨特的網路堆疊，可供 IPv4 和 IPv6 使用。</span><span class="sxs-lookup"><span data-stu-id="8faf2-115">You can, thanks to Windows, employ the dual stack feature, which is a separate and distinct network stack for IPv4 and IPv6.</span></span> <span data-ttu-id="8faf2-116">這會在您需要時，允許您同時指派 IPv4 和 IPv6 位址。</span><span class="sxs-lookup"><span data-stu-id="8faf2-116">This will, if you need, allow you to assign IPv4 and IPv6 addresses concurrently.</span></span>
  
<span data-ttu-id="8faf2-117">有 NAT 裝置允許 NAT64 (IPv6 IPv4) 和 NAT66 (IPv6 IPv6) # A4，而且這種裝置適用于商務用 Skype Server。</span><span class="sxs-lookup"><span data-stu-id="8faf2-117">There are NAT devices that allow for NAT64 (IPv6 to IPv4) and NAT66 (IPv6 to IPv6)), and this is valid for use with Skype for Business Server.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="8faf2-118">如果您要使用「通話許可控制」 (CAC) 您必須使用內部介面上的 IPv4 才能正常運作。</span><span class="sxs-lookup"><span data-stu-id="8faf2-118">If you're using Call Admission Control (CAC) you do have to use IPv4 on the internal interface for it to work.</span></span> 
  
## <a name="single-consolidated-skype-for-business-server-edge-server-with-private-ip-addresses-and-nat"></a><span data-ttu-id="8faf2-119">單一合併商務用 Skype Server Edge Server，具有私人 IP 位址和 NAT</span><span class="sxs-lookup"><span data-stu-id="8faf2-119">Single consolidated Skype for Business Server Edge Server with private IP addresses and NAT</span></span>

<span data-ttu-id="8faf2-120">在此案例中，高可用性沒有任何選項可供使用。</span><span class="sxs-lookup"><span data-stu-id="8faf2-120">With this scenario, there is no option for high availability.</span></span> <span data-ttu-id="8faf2-121">這表示您在硬體上花費的時間較少，且部署變得更簡單。</span><span class="sxs-lookup"><span data-stu-id="8faf2-121">This will mean you spend less on hardware and have a simpler deployment.</span></span> <span data-ttu-id="8faf2-122">如果有高可用性必須，請參閱下列縮放合併的案例。</span><span class="sxs-lookup"><span data-stu-id="8faf2-122">If high availability is a must, check out the Scaled consolidated scenarios below.</span></span>
  
![使用 NAT 透過私人 IP 進行單一合併 Edge 的 Edge 案例](../../media/Plan_LyncServer_Edge_Scenario_SingleConsolidatedEdgePrivateIP.jpg)
  
### <a name="port-diagram"></a><span data-ttu-id="8faf2-124">埠圖表</span><span class="sxs-lookup"><span data-stu-id="8faf2-124">Port diagram</span></span>

<span data-ttu-id="8faf2-125">我們也有一個用於單一合併 Edge Server 之埠的圖表。</span><span class="sxs-lookup"><span data-stu-id="8faf2-125">We also have a diagram for ports for single consolidated Edge Servers.</span></span>
  
![Edge 案例的網路周邊單一合併 Edge](../../media/Plan_LyncServer_Edge_NetPerimeter_SingleConsolidatedEdge.jpg)
  
## <a name="single-consolidated-skype-for-business-server-edge-server-with-public-ip-addresses"></a><span data-ttu-id="8faf2-127">單一合併的商務用 Skype Server Edge Server，具有公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="8faf2-127">Single consolidated Skype for Business Server Edge Server with public IP addresses</span></span>

<span data-ttu-id="8faf2-128">在此案例中，高可用性沒有任何選項可供使用。</span><span class="sxs-lookup"><span data-stu-id="8faf2-128">With this scenario, there is no option for high availability.</span></span> <span data-ttu-id="8faf2-129">這表示您在硬體上花費的時間較少，且部署變得更簡單。</span><span class="sxs-lookup"><span data-stu-id="8faf2-129">This will mean you spend less on hardware and have a simpler deployment.</span></span> <span data-ttu-id="8faf2-130">如果有高可用性必須，請參閱下列縮放合併的案例。</span><span class="sxs-lookup"><span data-stu-id="8faf2-130">If high availability is a must, check out the Scaled consolidated scenarios below.</span></span>
  
![具有公用 IP 之單一合併 Edge 的 Edge 案例](../../media/Plan_LyncServer_Edge_Scenario_SingleConsolidatedEdgePublicIP.jpg)
  
### <a name="port-diagram"></a><span data-ttu-id="8faf2-132">埠圖表</span><span class="sxs-lookup"><span data-stu-id="8faf2-132">Port diagram</span></span>

<span data-ttu-id="8faf2-133">我們也有一個用於單一合併 Edge Server 之埠的圖表。</span><span class="sxs-lookup"><span data-stu-id="8faf2-133">We also have a diagram for ports for single consolidated Edge Servers.</span></span>
  
![Edge 案例的網路周邊單一合併 Edge](../../media/Plan_LyncServer_Edge_NetPerimeter_SingleConsolidatedEdge.jpg)
  
## <a name="scaled-consolidated-skype-for-business-server-edge-pool-with-dns-load-balancing-and-private-ip-addresses-and-nat"></a><span data-ttu-id="8faf2-135">調整式合併商務用 Skype Server Edge 集區，使用 DNS 負載平衡，以及私人 IP 位址與 NAT</span><span class="sxs-lookup"><span data-stu-id="8faf2-135">Scaled consolidated Skype for Business Server Edge pool, with DNS load balancing, and private IP addresses and NAT</span></span>

<span data-ttu-id="8faf2-136">在此案例中，您可以在 Edge 部署中擁有高可用性，這可讓您提高可擴充性和容錯移轉支援的優點。</span><span class="sxs-lookup"><span data-stu-id="8faf2-136">With this scenario, you are able to have high availability in your Edge deployment, which gives you the advantages of scalability and failover support.</span></span>
  
![調整式合併 Edge 的 Edge 案例（使用 NAT 透過私人 IP 進行 DNS LB）](../../media/Plan_LyncServer_Edge_Scenario_ScaledConsolidatedEdgeDNSLBPrivateIP.jpg)
  
### <a name="port-diagram"></a><span data-ttu-id="8faf2-138">埠圖表</span><span class="sxs-lookup"><span data-stu-id="8faf2-138">Port diagram</span></span>

<span data-ttu-id="8faf2-139">我們也會有調整式合併 Edge 集區的圖表，使用 DNS 負載平衡。</span><span class="sxs-lookup"><span data-stu-id="8faf2-139">We also have a diagram for scaled consolidated Edge pools with DNS load balancing.</span></span>
  
![使用 DNS LB 針對 Edge 案例調整的合併 Edge 的網路周邊](../../media/Plan_LyncServer_Edge_NetPerimeter_ScaledConsolidatedEdgeDNSLB.jpg)
  
## <a name="scaled-consolidated-skype-for-business-server-edge-pool-with-dns-load-balancing-and-public-ip-addresses"></a><span data-ttu-id="8faf2-141">調整式合併商務用 Skype Server Edge 集區，使用 DNS 負載平衡和公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="8faf2-141">Scaled consolidated Skype for Business Server Edge pool, with DNS load balancing and public IP addresses</span></span>

<span data-ttu-id="8faf2-142">在此案例中，您可以在 Edge 部署中擁有高可用性，這可讓您提高可擴充性和容錯移轉支援的優點。</span><span class="sxs-lookup"><span data-stu-id="8faf2-142">With this scenario, you are able to have high availability in your Edge deployment, which gives you the advantages of scalability and failover support.</span></span>
  
![調整式合併 Edge 的 Edge 案例，DNS LB with Public IP](../../media/Plan_LyncServer_Edge_Scenario_ScaledConsolidatedEdgeDNSLBPublicIP.jpg)
  
### <a name="port-diagram"></a><span data-ttu-id="8faf2-144">埠圖表</span><span class="sxs-lookup"><span data-stu-id="8faf2-144">Port diagram</span></span>

<span data-ttu-id="8faf2-145">我們也會有調整式合併 Edge 集區的圖表，使用 DNS 負載平衡。</span><span class="sxs-lookup"><span data-stu-id="8faf2-145">We also have a diagram for scaled consolidated Edge pools with DNS load balancing.</span></span>
  
![使用 DNS LB 針對 Edge 案例調整的合併 Edge 的網路周邊](../../media/Plan_LyncServer_Edge_NetPerimeter_ScaledConsolidatedEdgeDNSLB.jpg)
  
## <a name="scaled-consolidated-skype-for-business-server-edge-pool-with-hardware-load-balancing"></a><span data-ttu-id="8faf2-147">調整式合併商務用 Skype Server Edge 集區，使用硬體負載平衡</span><span class="sxs-lookup"><span data-stu-id="8faf2-147">Scaled consolidated Skype for Business Server Edge pool, with hardware load balancing</span></span>

<span data-ttu-id="8faf2-148">在此案例中，您可以在 Edge 部署中擁有高可用性，這可讓您提高可擴充性和容錯移轉支援的優點。</span><span class="sxs-lookup"><span data-stu-id="8faf2-148">With this scenario, you are able to have high availability in your Edge deployment, which gives you the advantages of scalability and failover support.</span></span>
  
![調整式合併 Edge 與 HLB 的 Edge 案例](../../media/Plan_LyncServer_Edge_Scenario_ScaledConsolidatedEdgeHLB.jpg)
 
