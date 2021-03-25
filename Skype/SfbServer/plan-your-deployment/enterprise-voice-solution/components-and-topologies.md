---
title: 商務用 Skype 中通話許可控制的元件和拓撲
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
ms.assetid: 0beec6be-2431-4255-a3d2-512dd030e66a
description: 如果您有 MPLS 網路、SIP 主幹或協力廠商 PSTN 閘道或 PBX，請規劃通話許可控制 (CAC) 。 適用于商務用 Skype Server Enterprise Voice。
ms.openlocfilehash: 771b98e10c28248bc917bff2b8128b6258c140c5
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51109189"
---
# <a name="components-and-topologies-for-call-admission-control-in-skype-for-business"></a><span data-ttu-id="54851-104">商務用 Skype 中通話許可控制的元件和拓撲</span><span class="sxs-lookup"><span data-stu-id="54851-104">Components and topologies for call admission control in Skype for Business</span></span>

<span data-ttu-id="54851-105">如果您有 MPLS 網路、SIP 主幹或協力廠商 PSTN 閘道或 PBX，請規劃通話許可控制 (CAC) 。</span><span class="sxs-lookup"><span data-stu-id="54851-105">Planning for call admission control (CAC) if you have an MPLS network, a SIP trunk, or a third-party PSTN gateway or PBX.</span></span> <span data-ttu-id="54851-106">適用于商務用 Skype Server Enterprise Voice。</span><span class="sxs-lookup"><span data-stu-id="54851-106">Applies to Skype for Business Server Enterprise Voice.</span></span>

<span data-ttu-id="54851-107">本節中的主題提供部署通話許可控制 (CAC) 並搭配各種網路拓撲之特殊考量的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="54851-107">The topics in this section provide information about special considerations for deploying call admission control (CAC) with various types of network topologies.</span></span>

## <a name="call-admission-control-on-an-mpls-network"></a><span data-ttu-id="54851-108">MPLS 網路上的通話許可控制</span><span class="sxs-lookup"><span data-stu-id="54851-108">Call admission control on an MPLS network</span></span>

<span data-ttu-id="54851-p103">在多重通訊協定標籤交換 (Multiprotocol Label Switching，MPLS) 網路中，所有網站都由完整網狀 (Full-Mesh) 連線。也就是，所有網站都會直接連線至網際網路服務提供者的 MPLS 骨幹，而且每個網站都已佈建要透過 MPLS 雲端的 WAN 連結使用的頻寬。沒有網路集線器或中央網站可控制 IP 路由。下圖顯示以 MPLS 技術為基礎的簡易網路。</span><span class="sxs-lookup"><span data-stu-id="54851-p103">In a Multiprotocol Label Switching (MPLS) network, all sites are connected by a full-mesh. That is, all sites are connected directly to the MPLS backbone of the Internet service provider, and each site is provisioned bandwidth to be used across a WAN link to the MPLS cloud. There is no network hub or central site to control IP routing. The following figure shows a simple network based on MPLS technology.</span></span>

<span data-ttu-id="54851-113">**MPLS 網路範例**</span><span class="sxs-lookup"><span data-stu-id="54851-113">**Example MPLS network**</span></span>

![具有 MPLS 的 CAC](../../media/CAC_MPLS_1.jpg)

<span data-ttu-id="54851-p104">若要在 MPLS 網路中部署通話許可控制 (CAC)，您可建立網路地區代表 MPLS 雲端，以及建立網路網站代表每個 MPLS 衛星網站。下圖說明如何設定網路地區和網路網站以代表上圖中的 MPLS 網路範例。整體頻寬限制和頻寬工作階段限制都是以從每個網路網站連至代表 MPLS 雲端之網路地區的 WAN 連結為基礎。</span><span class="sxs-lookup"><span data-stu-id="54851-p104">To deploy call admission control (CAC) in an MPLS network, you create a network region to represent the MPLS cloud, and create a network site to represent each MPLS satellite site. The following figure illustrates how the network region and network sites should be configured to represent the example MPLS network in the previous figure. The overall bandwidth limits and bandwidth session limits are then based on the capacity of the WAN link from each network site to the network region that represents the MPLS cloud.</span></span>

<span data-ttu-id="54851-118">**MPLS 網路的網路地區和網路網站**</span><span class="sxs-lookup"><span data-stu-id="54851-118">**Network region and network sites for an MPLS network**</span></span>

![具有 MPLS 圖表 (CAC) 的通話許可控制](../../media/CAC_MPLS_2.jpg)

## <a name="call-admission-control-on-a-sip-trunk"></a><span data-ttu-id="54851-120">SIP 主幹上的通話許可控制</span><span class="sxs-lookup"><span data-stu-id="54851-120">Call admission control on a SIP trunk</span></span>

<span data-ttu-id="54851-p105">若要在 SIP 主幹上部署通話許可控制 (CAC)，您必須建立代表網際網路電話語音服務提供者 (ITSP) 的網路網站。若要在 SIP 主幹上套用頻寬原則值，您可以在企業中的網路網站與您建立以代表 ITSP 的網路網站之間，建立網站間原則。</span><span class="sxs-lookup"><span data-stu-id="54851-p105">To deploy call admission control (CAC) on a SIP trunk, you create a network site to represent the Internet telephony service provider (ITSP). To apply bandwidth policy values on the SIP trunk, you create an inter-site policy between the network site in your enterprise and the network site that you create to represent the ITSP.</span></span>

<span data-ttu-id="54851-123">下圖顯示在 SIP 主幹上部署 CAC 的範例。</span><span class="sxs-lookup"><span data-stu-id="54851-123">The following figure shows an example CAC deployment on a SIP trunk.</span></span>

<span data-ttu-id="54851-124">**SIP 主幹上的 CAC 組態**</span><span class="sxs-lookup"><span data-stu-id="54851-124">**CAC configuration on a SIP trunk**</span></span>

![通話許可控制 SIP 主幹圖表](../../media/CAC_SIP_trunk_1.jpg)

<span data-ttu-id="54851-126">若要在 SIP 主幹上設定 CAC，您必須在 CAC 部署期間執行下列工作：</span><span class="sxs-lookup"><span data-stu-id="54851-126">To configure CAC on a SIP trunk, you will have to perform the following tasks during CAC deployment:</span></span>

1. <span data-ttu-id="54851-127">建立代表 ITSP 的網路網站。</span><span class="sxs-lookup"><span data-stu-id="54851-127">Create a network site to represent the ITSP.</span></span> <span data-ttu-id="54851-128">讓此網路網站與適當的網路地區相關聯，並為此網路網站的音訊與視訊功能配置零的頻寬。</span><span class="sxs-lookup"><span data-stu-id="54851-128">Associate the network site to an appropriate network region, and allocate bandwidth of zero for audio and video for this network site.</span></span> <span data-ttu-id="54851-129">如需詳細資訊，請參閱部署文件中的＜[Configure Network Sites for CAC](/previous-versions/office/lync-server-2013/lync-server-2013-configure-network-sites-for-cac)＞。</span><span class="sxs-lookup"><span data-stu-id="54851-129">For details, see [Configure Network Sites for CAC](/previous-versions/office/lync-server-2013/lync-server-2013-configure-network-sites-for-cac) in the Deployment documentation.</span></span>

    > [!NOTE]
    > <span data-ttu-id="54851-130">對 ITSP 而言，此網路網站組態沒有作用。</span><span class="sxs-lookup"><span data-stu-id="54851-130">For the ITSP, this network site configuration is not functional.</span></span> <span data-ttu-id="54851-131">頻寬原則值實際是在步驟 2 套用。</span><span class="sxs-lookup"><span data-stu-id="54851-131">Bandwidth policy values are actually applied in step 2.</span></span>

2. <span data-ttu-id="54851-132">針對您在步驟 1 建立的網站使用相關的參數值，建立 SIP 主幹的網站間連結。</span><span class="sxs-lookup"><span data-stu-id="54851-132">Create an inter-site link for the SIP trunk using the relevant parameter values for the site you created in step 1.</span></span> <span data-ttu-id="54851-133">例如，您可以使用企業中網路網站的名稱作為 NetworkSiteID1 參數的值，並以 ITSP 網路網站作為 NetworkSiteID2 參數的值。</span><span class="sxs-lookup"><span data-stu-id="54851-133">For example, use the name of the network site in your enterprise as the value of the NetworkSiteID1 parameter, and the ITSP network site as the value of the NetworkSiteID2 parameter.</span></span> <span data-ttu-id="54851-134">如需詳細資訊，請參閱部署檔中的在 [商務用 Skype Server 中建立網路網站間原則](../../deploy/deploy-enterprise-voice/create-network-intersite-policies.md) ，以及 [新的-CsNetworkInterSitePolicy](/powershell/module/skype/new-csnetworkintersitepolicy?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="54851-134">For details, see [Create network intersite policies in Skype for Business Server](../../deploy/deploy-enterprise-voice/create-network-intersite-policies.md) in the Deployment documentation, and [New-CsNetworkInterSitePolicy](/powershell/module/skype/new-csnetworkintersitepolicy?view=skype-ps).</span></span>

3. <span data-ttu-id="54851-135">從 ITSP 取得會話邊界控制器的 (SCB) 媒體端接點的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="54851-135">Get the IP address of the Session Border Controller's (SCB) Media Termination Point from your ITSP.</span></span> <span data-ttu-id="54851-136">將該子網路遮罩為32的 IP 位址，新增至代表 ITSP 的網路網站。</span><span class="sxs-lookup"><span data-stu-id="54851-136">Add that IP address with a subnet mask of 32 to the network site that represents the ITSP.</span></span> <span data-ttu-id="54851-137">如需詳細資訊，請參閱 [建立子網與網路網站的關聯](/previous-versions/office/lync-server-2013/lync-server-2013-associate-a-subnet-with-a-network-site)。</span><span class="sxs-lookup"><span data-stu-id="54851-137">For details, see [Associate a Subnet with a Network Site](/previous-versions/office/lync-server-2013/lync-server-2013-associate-a-subnet-with-a-network-site).</span></span>

## <a name="call-admission-control-with-a-third-party-pstn-gateway-or-pbx"></a><span data-ttu-id="54851-138">使用協力廠商 PSTN 閘道或 PBX 的通話許可控制</span><span class="sxs-lookup"><span data-stu-id="54851-138">Call admission control with a third-party PSTN gateway or PBX</span></span>

<span data-ttu-id="54851-139">本主題說明如何在轉送伺服器的閘道介面和協力廠商公用交換電話網路 (PSTN) 閘道或專用交換機 (PBX) 之間的連結上，部署通話許可控制 (CAC) 的範例。</span><span class="sxs-lookup"><span data-stu-id="54851-139">This topic describes examples of how call admission control (CAC) can be deployed on the link between the Mediation Server's gateway interface and a third-party public switched telephone network (PSTN) gateway or private branch exchange (PBX).</span></span>

### <a name="case-1-cac-between-the-mediation-server-and-a-pstn-gateway"></a><span data-ttu-id="54851-140">案例1：轉送伺服器和 PSTN 閘道之間的 CAC</span><span class="sxs-lookup"><span data-stu-id="54851-140">Case 1: CAC between the Mediation Server and a PSTN gateway</span></span>

<span data-ttu-id="54851-141">CAC 可以從轉送伺服器閘道介面到協力廠商 PBX 或 PSTN 閘道的 WAN 連結上部署。</span><span class="sxs-lookup"><span data-stu-id="54851-141">CAC can be deployed on the WAN link from the Mediation Server's gateway interface to a third-party PBX or PSTN gateway.</span></span>

<span data-ttu-id="54851-142">**案例1：轉送伺服器和 PSTN 閘道之間的 CAC**</span><span class="sxs-lookup"><span data-stu-id="54851-142">**Case 1: CAC between the Mediation Server and a PSTN gateway**</span></span>

![案例1：轉送伺服器 PSTN 閘道之間的 CAC](../../media/CAC_gateways_1.jpg)

<span data-ttu-id="54851-144">在此範例中，轉送伺服器和 PSTN 閘道之間會套用 CAC。</span><span class="sxs-lookup"><span data-stu-id="54851-144">In this example, CAC is applied between the Mediation Server and a PSTN gateway.</span></span> <span data-ttu-id="54851-145">如果位於網路 Site 1 的商務用 Skype 用戶端使用者，透過網路 Site 2 中的 PSTN 閘道撥打 PSTN 通話，該媒體會透過 WAN 連結進行流量。</span><span class="sxs-lookup"><span data-stu-id="54851-145">If a Skype for Business client user at Network Site 1 places a PSTN call through the PSTN gateway in Network Site 2, the media flows through the WAN link.</span></span> <span data-ttu-id="54851-146">因此，每個 PSTN 會話會執行兩個 CAC 檢查：</span><span class="sxs-lookup"><span data-stu-id="54851-146">Therefore, two CAC checks are performed for each PSTN session:</span></span>

- <span data-ttu-id="54851-147">商務用 Skype 用戶端應用程式與轉送伺服器之間</span><span class="sxs-lookup"><span data-stu-id="54851-147">Between the Skype for Business client application and the Mediation Server</span></span>

- <span data-ttu-id="54851-148">轉送伺服器和 PSTN 閘道之間</span><span class="sxs-lookup"><span data-stu-id="54851-148">Between the Mediation Server and the PSTN gateway</span></span>

<span data-ttu-id="54851-149">這適用于網路 Site 1 中的用戶端傳入 PSTN 通話，以及來自網路 Site 1 中用戶端應用程式的撥出 PSTN 通話。</span><span class="sxs-lookup"><span data-stu-id="54851-149">This works for both incoming PSTN calls to a client in Network Site 1, and for outgoing PSTN calls originating from a client application in Network Site 1.</span></span>

> [!NOTE]
> <span data-ttu-id="54851-150">確定 PSTN 閘道所屬的 IP 子網已經過設定，並與網路網站2相關聯。</span><span class="sxs-lookup"><span data-stu-id="54851-150">Make sure that the IP subnet that the PSTN gateway belongs to is configured and associated with Network Site 2.</span></span>

> [!NOTE]
> <span data-ttu-id="54851-151">請確定轉送伺服器的兩個介面都屬於的 IP 子網已設定，並與網路網站1產生關聯。</span><span class="sxs-lookup"><span data-stu-id="54851-151">Make sure that the IP subnet that both interfaces of the Mediation Server belong to is configured and associated with Network Site 1.</span></span>

> [!NOTE]
> <span data-ttu-id="54851-152">如需詳細資訊，請參閱 [建立子網與網路網站的關聯](/previous-versions/office/lync-server-2013/lync-server-2013-associate-a-subnet-with-a-network-site)。</span><span class="sxs-lookup"><span data-stu-id="54851-152">For details, see [Associate a Subnet with a Network Site](/previous-versions/office/lync-server-2013/lync-server-2013-associate-a-subnet-with-a-network-site).</span></span>

### <a name="case-2-cac-between-the-mediation-server-and-a-third-party-pbx-with-media-termination-point"></a><span data-ttu-id="54851-153">案例2：轉送伺服器和具有媒體終止點之協力廠商 PBX 之間的 CAC</span><span class="sxs-lookup"><span data-stu-id="54851-153">Case 2: CAC between the Mediation Server and a third-party PBX with Media Termination Point</span></span>

<span data-ttu-id="54851-154">這種設定與案例1類似。</span><span class="sxs-lookup"><span data-stu-id="54851-154">This configuration is similar to Case 1.</span></span> <span data-ttu-id="54851-155">在這兩種情況下，轉送伺服器都知道在 WAN 連結的相對端終止媒體的方式，以及 PSTN 閘道或 PBX 的 IP 位址，以及具有媒體終止點 (MTP) 會在轉送伺服器上設定為下一個躍點。</span><span class="sxs-lookup"><span data-stu-id="54851-155">In both the cases, the Mediation Server knows what device terminates media at the opposite end of the WAN link, and the IP address of the PSTN gateway or PBX with Media Termination Point (MTP) is configured on the Mediation Server as the next hop.</span></span>

<span data-ttu-id="54851-156">**案例2：轉送伺服器和具有 MTP 之協力廠商 PBX 之間的 CAC**</span><span class="sxs-lookup"><span data-stu-id="54851-156">**Case 2: CAC between the Mediation Server and a third-party PBX with MTP**</span></span>

![案例2：轉送伺服器 PBX 與 MTP 之間的 CAC](../../media/CAC_gateways_2.jpg)

<span data-ttu-id="54851-158">在此範例中，轉送伺服器和 PBX/MTP 之間會套用 CAC。</span><span class="sxs-lookup"><span data-stu-id="54851-158">In this example, CAC is applied between the Mediation Server and the PBX/MTP.</span></span> <span data-ttu-id="54851-159">如果位於網路網站1的商務用 Skype 用戶端使用者，透過位於網路 Site 2 的 PBX/MTP 來撥打 PSTN 通話，媒體會透過 WAN 連結進行流量。</span><span class="sxs-lookup"><span data-stu-id="54851-159">If a Skype for Business client user at the Network Site 1 places a PSTN call through the PBX/MTP located in Network Site 2, the media flows through the WAN link.</span></span> <span data-ttu-id="54851-160">因此，每個 PSTN 會話都會執行兩個 CAC 檢查：</span><span class="sxs-lookup"><span data-stu-id="54851-160">Therefore, for each PSTN session two CAC checks are performed:</span></span>

- <span data-ttu-id="54851-161">商務用 Skype 用戶端應用程式與轉送伺服器之間</span><span class="sxs-lookup"><span data-stu-id="54851-161">Between the Skype for Business client application and the Mediation Server</span></span>

- <span data-ttu-id="54851-162">轉送伺服器和 PBX/MTP 之間</span><span class="sxs-lookup"><span data-stu-id="54851-162">Between the Mediation Server and the PBX/MTP</span></span>

<span data-ttu-id="54851-163">這適用于對網路 Site 1 中的用戶端進行傳入 PSTN 通話，以及發自來自網路 Site 1 之用戶端的傳出 PSTN 通話。</span><span class="sxs-lookup"><span data-stu-id="54851-163">This works for both incoming PSTN calls to a client in Network Site 1, and outgoing PSTN calls originating from a client in Network Site 1.</span></span>

> [!NOTE]
> <span data-ttu-id="54851-164">確定 MTP 所屬的 IP 子網已經過設定，並與網路網站2相關聯。</span><span class="sxs-lookup"><span data-stu-id="54851-164">Make sure that the IP subnet that the MTP belongs to is configured and associated with Network Site 2.</span></span>

> [!NOTE]
> <span data-ttu-id="54851-165">請確定轉送伺服器的兩個介面都屬於的 IP 子網已設定，並與網路網站1產生關聯。</span><span class="sxs-lookup"><span data-stu-id="54851-165">Make sure that the IP subnet that both interfaces of the Mediation Server belong to is configured and associated with Network Site 1.</span></span>

> [!NOTE]
> <span data-ttu-id="54851-166">如需詳細資訊，請參閱 [建立子網與網路網站的關聯](/previous-versions/office/lync-server-2013/lync-server-2013-associate-a-subnet-with-a-network-site)。</span><span class="sxs-lookup"><span data-stu-id="54851-166">For details, see [Associate a Subnet with a Network Site](/previous-versions/office/lync-server-2013/lync-server-2013-associate-a-subnet-with-a-network-site).</span></span>

### <a name="case-3-cac-between-the-mediation-server-and-a-third-party-pbx-without-a-media-termination-point"></a><span data-ttu-id="54851-167">案例3：轉送伺服器和不具有媒體終端點之協力廠商 PBX 之間的 CAC</span><span class="sxs-lookup"><span data-stu-id="54851-167">Case 3: CAC between the Mediation Server and a third-party PBX without a Media Termination Point</span></span>

<span data-ttu-id="54851-168">Case 3 與前兩個案例稍有不同。</span><span class="sxs-lookup"><span data-stu-id="54851-168">Case 3 is slightly different from the first two cases.</span></span> <span data-ttu-id="54851-169">如果在協力廠商 PBX 上沒有 MTP，轉送伺服器不會知道媒體在 PBX 界限中將終止的哪個位置。</span><span class="sxs-lookup"><span data-stu-id="54851-169">If there is no MTP on the third-party PBX, for an outgoing session request to the third-party PBX the Mediation Server does not know where media will terminate in the PBX boundary.</span></span> <span data-ttu-id="54851-170">在此情況下，媒體會直接流過轉送伺服器和協力廠商端點裝置。</span><span class="sxs-lookup"><span data-stu-id="54851-170">In this case, the media flows directly between the Mediation Server and the third-party endpoint device.</span></span>

<span data-ttu-id="54851-171">**案例3：轉送伺服器和不具有 MTP 之協力廠商 PBX 之間的 CAC**</span><span class="sxs-lookup"><span data-stu-id="54851-171">**Case 3: CAC between the Mediation Server and a third-party PBX without MTP**</span></span>

![案例3：轉送伺服器 PBX 之間的 CAC 無 MTP](../../media/CAC_gateways_3.jpg)

<span data-ttu-id="54851-173">在此範例中，如果網路 Site 1 上的商務用 Skype 用戶端使用者透過 PBX 撥打給使用者，則轉送伺服器只能在商務用 Skype 用戶端應用程式與轉送伺服器) 之間，于 proxy 腿 (執行 CAC 檢查。</span><span class="sxs-lookup"><span data-stu-id="54851-173">In this example, if a Skype for Business client user at Network Site 1 places a call to a user through the PBX, the Mediation Server is able to perform CAC checks only on the proxy leg (between the Skype for Business client application and Mediation Server).</span></span> <span data-ttu-id="54851-174">因為在要求會話時，轉送伺服器沒有端點裝置的相關資訊，所以在建立通話之前，無法在轉送伺服器和協力廠商) 端點之間的 WAN 連結 (上執行 CAC 檢查。</span><span class="sxs-lookup"><span data-stu-id="54851-174">Because the Mediation Server does not have information about the endpoint device while the session is being requested, CAC checks cannot be performed on the WAN link (between the Mediation Server and the third-party endpoint) prior to call establishment.</span></span> <span data-ttu-id="54851-175">在建立會話後，轉送伺服器會為主幹使用的頻寬進行會計核算。</span><span class="sxs-lookup"><span data-stu-id="54851-175">After the session is established, however, the Mediation Server facilitates in accounting for the bandwidth used on the trunk.</span></span>

<span data-ttu-id="54851-176">針對來自協力廠商端點的呼叫，在會話要求時可使用該端點裝置的相關資訊，同時也可以在轉送伺服器的兩側執行 CAC 檢查。</span><span class="sxs-lookup"><span data-stu-id="54851-176">For calls that originate from the third-party endpoint, the information about that endpoint device is available at the time of session request and CAC check can be performed on both the sides of the Mediation Server.</span></span>

> [!NOTE]
> <span data-ttu-id="54851-177">確定端點裝置所屬的 IP 子網已經過設定，並與網路網站2相關聯。</span><span class="sxs-lookup"><span data-stu-id="54851-177">Make sure that the IP subnet that the endpoint devices belong to is configured and associated with Network Site 2.</span></span>

> [!NOTE]
> <span data-ttu-id="54851-178">請確定轉送伺服器的兩個介面都屬於的 IP 子網已設定，並與網路網站1產生關聯。</span><span class="sxs-lookup"><span data-stu-id="54851-178">Make sure that the IP subnet that both interfaces of the Mediation Server belong to is configured and associated with Network Site 1.</span></span>

> [!NOTE]
> <span data-ttu-id="54851-179">如需詳細資訊，請參閱 [建立子網與網路網站的關聯](/previous-versions/office/lync-server-2013/lync-server-2013-associate-a-subnet-with-a-network-site)。</span><span class="sxs-lookup"><span data-stu-id="54851-179">For details, see [Associate a Subnet with a Network Site](/previous-versions/office/lync-server-2013/lync-server-2013-associate-a-subnet-with-a-network-site).</span></span>