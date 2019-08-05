---
title: 商務用 Skype 中的通話許可控制元件與拓撲
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
ms.assetid: 0beec6be-2431-4255-a3d2-512dd030e66a
description: 如果您有 MPLS 網路、SIP 幹線或協力廠商 PSTN 閘道或 PBX, 請規劃通話許可控制 (CAC)。 適用于商務用 Skype Server 企業版語音。
ms.openlocfilehash: 326387b7b0794b3cbd027d539880f8c4b40f42d8
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36187750"
---
# <a name="components-and-topologies-for-call-admission-control-in-skype-for-business"></a><span data-ttu-id="1c3a1-104">商務用 Skype 中的通話許可控制元件與拓撲</span><span class="sxs-lookup"><span data-stu-id="1c3a1-104">Components and topologies for call admission control in Skype for Business</span></span>

<span data-ttu-id="1c3a1-105">如果您有 MPLS 網路、SIP 幹線或協力廠商 PSTN 閘道或 PBX, 請規劃通話許可控制 (CAC)。</span><span class="sxs-lookup"><span data-stu-id="1c3a1-105">Planning for call admission control (CAC) if you have an MPLS network, a SIP trunk, or a third-party PSTN gateway or PBX.</span></span> <span data-ttu-id="1c3a1-106">適用于商務用 Skype Server 企業版語音。</span><span class="sxs-lookup"><span data-stu-id="1c3a1-106">Applies to Skype for Business Server Enterprise Voice.</span></span>

<span data-ttu-id="1c3a1-107">本節中的主題提供使用各種類型的網路拓撲來部署通話許可控制 (CAC) 的特殊考慮事項的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="1c3a1-107">The topics in this section provide information about special considerations for deploying call admission control (CAC) with various types of network topologies.</span></span>

## <a name="call-admission-control-on-an-mpls-network"></a><span data-ttu-id="1c3a1-108">在 MPLS 網路上呼叫許可控制</span><span class="sxs-lookup"><span data-stu-id="1c3a1-108">Call admission control on an MPLS network</span></span>

<span data-ttu-id="1c3a1-109">在多協定標籤切換 (MPLS) 網路中, 所有網站都是以全網格連接。</span><span class="sxs-lookup"><span data-stu-id="1c3a1-109">In a Multiprotocol Label Switching (MPLS) network, all sites are connected by a full-mesh.</span></span> <span data-ttu-id="1c3a1-110">也就是說, 所有網站都直接連線至網際網路服務提供者的 MPLS 中樞, 且每個網站都配有頻寬, 可跨 WAN 連結使用到 MPLS 雲端。</span><span class="sxs-lookup"><span data-stu-id="1c3a1-110">That is, all sites are connected directly to the MPLS backbone of the Internet service provider, and each site is provisioned bandwidth to be used across a WAN link to the MPLS cloud.</span></span> <span data-ttu-id="1c3a1-111">沒有網路中樞或中央網站可控制 IP 路由。</span><span class="sxs-lookup"><span data-stu-id="1c3a1-111">There is no network hub or central site to control IP routing.</span></span> <span data-ttu-id="1c3a1-112">下圖顯示的是以 MPLS 技術為基礎的簡單網路。</span><span class="sxs-lookup"><span data-stu-id="1c3a1-112">The following figure shows a simple network based on MPLS technology.</span></span>

<span data-ttu-id="1c3a1-113">**MPLS 網路範例**</span><span class="sxs-lookup"><span data-stu-id="1c3a1-113">**Example MPLS network**</span></span>

![使用 MPLS 的 CAC](../../media/CAC_MPLS_1.jpg)

<span data-ttu-id="1c3a1-115">若要在 MPLS 網路中部署呼叫許可控制 (CAC), 您需要建立網路區域來代表 MPLS 雲端, 並建立網路網站來代表每個 MPLS 附屬網站。</span><span class="sxs-lookup"><span data-stu-id="1c3a1-115">To deploy call admission control (CAC) in an MPLS network, you create a network region to represent the MPLS cloud, and create a network site to represent each MPLS satellite site.</span></span> <span data-ttu-id="1c3a1-116">下圖說明如何設定網路區域和網路網站, 以代表前圖中的範例 MPLS 網路。</span><span class="sxs-lookup"><span data-stu-id="1c3a1-116">The following figure illustrates how the network region and network sites should be configured to represent the example MPLS network in the previous figure.</span></span> <span data-ttu-id="1c3a1-117">整個頻寬限制和頻寬會話限制是依據從每個網路網站到代表 MPLS 雲端之網路區域的 WAN 連結容量而定。</span><span class="sxs-lookup"><span data-stu-id="1c3a1-117">The overall bandwidth limits and bandwidth session limits are then based on the capacity of the WAN link from each network site to the network region that represents the MPLS cloud.</span></span>

<span data-ttu-id="1c3a1-118">**MPLS 網路的網路區域和網路網站**</span><span class="sxs-lookup"><span data-stu-id="1c3a1-118">**Network region and network sites for an MPLS network**</span></span>

![使用 MPLS 的通話許可控制 (CAC) 圖表](../../media/CAC_MPLS_2.jpg)

## <a name="call-admission-control-on-a-sip-trunk"></a><span data-ttu-id="1c3a1-120">SIP 主幹上的通話許可控制</span><span class="sxs-lookup"><span data-stu-id="1c3a1-120">Call admission control on a SIP trunk</span></span>

<span data-ttu-id="1c3a1-121">若要在 SIP 主幹上部署呼叫許可控制 (CAC), 您需要建立網路網站來代表網際網路電話服務提供者 (ITSP)。</span><span class="sxs-lookup"><span data-stu-id="1c3a1-121">To deploy call admission control (CAC) on a SIP trunk, you create a network site to represent the Internet telephony service provider (ITSP).</span></span> <span data-ttu-id="1c3a1-122">若要在 SIP 主幹上套用頻寬原則值, 您可以在企業中的網路網站和您建立用以代表 ITSP 的網路網站之間建立站間原則。</span><span class="sxs-lookup"><span data-stu-id="1c3a1-122">To apply bandwidth policy values on the SIP trunk, you create an inter-site policy between the network site in your enterprise and the network site that you create to represent the ITSP.</span></span>

<span data-ttu-id="1c3a1-123">下圖顯示 SIP 主幹上的 CAC 部署範例。</span><span class="sxs-lookup"><span data-stu-id="1c3a1-123">The following figure shows an example CAC deployment on a SIP trunk.</span></span>

<span data-ttu-id="1c3a1-124">**SIP 幹線上的 CAC 配置**</span><span class="sxs-lookup"><span data-stu-id="1c3a1-124">**CAC configuration on a SIP trunk**</span></span>

![通話許可控制 SIP 主幹圖表](../../media/CAC_SIP_trunk_1.jpg)

<span data-ttu-id="1c3a1-126">若要在 SIP 主幹上設定 CAC, 您必須在 CAC 部署期間執行下列工作:</span><span class="sxs-lookup"><span data-stu-id="1c3a1-126">To configure CAC on a SIP trunk, you will have to perform the following tasks during CAC deployment:</span></span>

1. <span data-ttu-id="1c3a1-127">建立代表 ITSP 的網路網站。</span><span class="sxs-lookup"><span data-stu-id="1c3a1-127">Create a network site to represent the ITSP.</span></span> <span data-ttu-id="1c3a1-128">將網路網站與合適的網路區域建立關聯, 並為此網路網站的音訊和影片分配零頻寬。</span><span class="sxs-lookup"><span data-stu-id="1c3a1-128">Associate the network site to an appropriate network region, and allocate bandwidth of zero for audio and video for this network site.</span></span> <span data-ttu-id="1c3a1-129">如需詳細資訊, 請參閱在部署檔中[設定 CAC 的網路網站](https://technet.microsoft.com/library/afcea38f-5789-45ec-97af-c6e38364950c.aspx)。</span><span class="sxs-lookup"><span data-stu-id="1c3a1-129">For details, see [Configure Network Sites for CAC](https://technet.microsoft.com/library/afcea38f-5789-45ec-97af-c6e38364950c.aspx) in the Deployment documentation.</span></span>

    > [!NOTE]
    > <span data-ttu-id="1c3a1-130">針對 ITSP, 此網路網站設定無法正常運作。</span><span class="sxs-lookup"><span data-stu-id="1c3a1-130">For the ITSP, this network site configuration is not functional.</span></span> <span data-ttu-id="1c3a1-131">在步驟2中實際會套用頻寬原則值。</span><span class="sxs-lookup"><span data-stu-id="1c3a1-131">Bandwidth policy values are actually applied in step 2.</span></span>

2. <span data-ttu-id="1c3a1-132">使用您在步驟1中建立的網站相關參數值, 為 SIP 幹線建立站間連結。</span><span class="sxs-lookup"><span data-stu-id="1c3a1-132">Create an inter-site link for the SIP trunk using the relevant parameter values for the site you created in step 1.</span></span> <span data-ttu-id="1c3a1-133">例如, 在企業中使用網路網站的名稱做為 NetworkSiteID1 參數的值, 並使用 ITSP network 網站作為 NetworkSiteID2 參數的值。</span><span class="sxs-lookup"><span data-stu-id="1c3a1-133">For example, use the name of the network site in your enterprise as the value of the NetworkSiteID1 parameter, and the ITSP network site as the value of the NetworkSiteID2 parameter.</span></span> <span data-ttu-id="1c3a1-134">如需詳細資訊, 請參閱部署檔中的[商務用 Skype Server 中建立網路站間原則](../../deploy/deploy-enterprise-voice/create-network-intersite-policies.md), 以及[新的 CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/new-csnetworkintersitepolicy?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="1c3a1-134">For details, see [Create network intersite policies in Skype for Business Server](../../deploy/deploy-enterprise-voice/create-network-intersite-policies.md) in the Deployment documentation, and [New-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/new-csnetworkintersitepolicy?view=skype-ps).</span></span>

3. <span data-ttu-id="1c3a1-135">從您的 ITSP 取得會話邊界控制器 (SCB) 媒體終止點的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="1c3a1-135">Get the IP address of the Session Border Controller's (SCB) Media Termination Point from your ITSP.</span></span> <span data-ttu-id="1c3a1-136">將具有子網路遮罩32的 IP 位址新增至代表 ITSP 的網路網站。</span><span class="sxs-lookup"><span data-stu-id="1c3a1-136">Add that IP address with a subnet mask of 32 to the network site that represents the ITSP.</span></span> <span data-ttu-id="1c3a1-137">如需詳細資訊, 請參閱[將子網與網路網站建立關聯](https://technet.microsoft.com/library/aa69e3ac-542a-4ba1-9582-2e6bee29f633.aspx)。</span><span class="sxs-lookup"><span data-stu-id="1c3a1-137">For details, see [Associate a Subnet with a Network Site](https://technet.microsoft.com/library/aa69e3ac-542a-4ba1-9582-2e6bee29f633.aspx).</span></span>

## <a name="call-admission-control-with-a-third-party-pstn-gateway-or-pbx"></a><span data-ttu-id="1c3a1-138">協力廠商 PSTN 閘道或 PBX 的通話許可控制</span><span class="sxs-lookup"><span data-stu-id="1c3a1-138">Call admission control with a third-party PSTN gateway or PBX</span></span>

<span data-ttu-id="1c3a1-139">本主題說明如何將呼叫許可控制 (CAC) 部署在中繼伺服器的閘道介面與協力廠商公用交換電話網絡 (PSTN) 閘道或私人分支 exchange (PBX) 之間的連結上。</span><span class="sxs-lookup"><span data-stu-id="1c3a1-139">This topic describes examples of how call admission control (CAC) can be deployed on the link between the Mediation Server's gateway interface and a third-party public switched telephone network (PSTN) gateway or private branch exchange (PBX).</span></span>

### <a name="case-1-cac-between-the-mediation-server-and-a-pstn-gateway"></a><span data-ttu-id="1c3a1-140">Case 1: 在中繼伺服器與 PSTN 閘道之間的 CAC</span><span class="sxs-lookup"><span data-stu-id="1c3a1-140">Case 1: CAC between the Mediation Server and a PSTN gateway</span></span>

<span data-ttu-id="1c3a1-141">在從中繼伺服器的閘道介面到協力廠商 PBX 或 PSTN 閘道的 WAN 連結上, 可以部署 CAC。</span><span class="sxs-lookup"><span data-stu-id="1c3a1-141">CAC can be deployed on the WAN link from the Mediation Server's gateway interface to a third-party PBX or PSTN gateway.</span></span>

<span data-ttu-id="1c3a1-142">**Case 1: 在中繼伺服器與 PSTN 閘道之間的 CAC**</span><span class="sxs-lookup"><span data-stu-id="1c3a1-142">**Case 1: CAC between the Mediation Server and a PSTN gateway**</span></span>

![案例 1：中繼伺服器和 PSTN 閘道間的 CAC](../../media/CAC_gateways_1.jpg)

<span data-ttu-id="1c3a1-144">在這個範例中, 在中繼伺服器和 PSTN 閘道之間會套用 CAC。</span><span class="sxs-lookup"><span data-stu-id="1c3a1-144">In this example, CAC is applied between the Mediation Server and a PSTN gateway.</span></span> <span data-ttu-id="1c3a1-145">如果網路網站1的商務用 Skype 用戶端使用者是透過 Network Site 2 中的 PSTN 閘道撥打電話給 PSTN 電話, 則媒體會透過 WAN 連結流過。</span><span class="sxs-lookup"><span data-stu-id="1c3a1-145">If a Skype for Business client user at Network Site 1 places a PSTN call through the PSTN gateway in Network Site 2, the media flows through the WAN link.</span></span> <span data-ttu-id="1c3a1-146">因此, 每個 PSTN 會話都會執行兩個 CAC 檢查:</span><span class="sxs-lookup"><span data-stu-id="1c3a1-146">Therefore, two CAC checks are performed for each PSTN session:</span></span>

- <span data-ttu-id="1c3a1-147">在商務用 Skype 用戶端應用程式與中繼伺服器之間</span><span class="sxs-lookup"><span data-stu-id="1c3a1-147">Between the Skype for Business client application and the Mediation Server</span></span>

- <span data-ttu-id="1c3a1-148">在中繼伺服器與 PSTN 閘道之間</span><span class="sxs-lookup"><span data-stu-id="1c3a1-148">Between the Mediation Server and the PSTN gateway</span></span>

<span data-ttu-id="1c3a1-149">這適用于網路 Site 1 中的用戶端撥入 PSTN 呼叫, 以及源自網路 Site 1 中用戶端應用程式的出局 PSTN 呼叫。</span><span class="sxs-lookup"><span data-stu-id="1c3a1-149">This works for both incoming PSTN calls to a client in Network Site 1, and for outgoing PSTN calls originating from a client application in Network Site 1.</span></span>

> [!NOTE]
> <span data-ttu-id="1c3a1-150">確認 PSTN 閘道所屬的 IP 子網已設定並與網路 Site 2 相關聯。</span><span class="sxs-lookup"><span data-stu-id="1c3a1-150">Make sure that the IP subnet that the PSTN gateway belongs to is configured and associated with Network Site 2.</span></span>

> [!NOTE]
> <span data-ttu-id="1c3a1-151">請確定已設定中繼伺服器的兩個介面所屬的 IP 子網, 並與網路 Site 1 產生關聯。</span><span class="sxs-lookup"><span data-stu-id="1c3a1-151">Make sure that the IP subnet that both interfaces of the Mediation Server belong to is configured and associated with Network Site 1.</span></span>

> [!NOTE]
> <span data-ttu-id="1c3a1-152">如需詳細資訊, 請參閱[將子網與網路網站建立關聯](https://technet.microsoft.com/library/aa69e3ac-542a-4ba1-9582-2e6bee29f633.aspx)。</span><span class="sxs-lookup"><span data-stu-id="1c3a1-152">For details, see [Associate a Subnet with a Network Site](https://technet.microsoft.com/library/aa69e3ac-542a-4ba1-9582-2e6bee29f633.aspx).</span></span>

### <a name="case-2-cac-between-the-mediation-server-and-a-third-party-pbx-with-media-termination-point"></a><span data-ttu-id="1c3a1-153">Case 2: 在中繼伺服器與含媒體端接點的協力廠商 PBX 之間使用 CAC</span><span class="sxs-lookup"><span data-stu-id="1c3a1-153">Case 2: CAC between the Mediation Server and a third-party PBX with Media Termination Point</span></span>

<span data-ttu-id="1c3a1-154">此設定類似于 Case 1。</span><span class="sxs-lookup"><span data-stu-id="1c3a1-154">This configuration is similar to Case 1.</span></span> <span data-ttu-id="1c3a1-155">在這兩種情況下, 中繼伺服器會知道在 WAN 連結的另一端終止媒體的裝置, 以及具有媒體端接點 (MTP) 之 PSTN 閘道或 PBX 的 IP 位址, 都是在轉送伺服器上設定為下一個躍點。</span><span class="sxs-lookup"><span data-stu-id="1c3a1-155">In both the cases, the Mediation Server knows what device terminates media at the opposite end of the WAN link, and the IP address of the PSTN gateway or PBX with Media Termination Point (MTP) is configured on the Mediation Server as the next hop.</span></span>

<span data-ttu-id="1c3a1-156">**Case 2: 在中繼伺服器與含 MTP 的協力廠商 PBX 之間使用的 CAC**</span><span class="sxs-lookup"><span data-stu-id="1c3a1-156">**Case 2: CAC between the Mediation Server and a third-party PBX with MTP**</span></span>

![案例 2：中繼伺服器和具有 MTP 之 PBX 間的 CAC](../../media/CAC_gateways_2.jpg)

<span data-ttu-id="1c3a1-158">在這個範例中, 在中繼伺服器與 PBX/MTP 之間會套用 CAC。</span><span class="sxs-lookup"><span data-stu-id="1c3a1-158">In this example, CAC is applied between the Mediation Server and the PBX/MTP.</span></span> <span data-ttu-id="1c3a1-159">如果網路網站1上的商務用 Skype 用戶端使用者是透過網路 Site 2 中的 PBX/MTP 進行 PSTN 呼叫, 則媒體會透過 WAN 連結流過。</span><span class="sxs-lookup"><span data-stu-id="1c3a1-159">If a Skype for Business client user at the Network Site 1 places a PSTN call through the PBX/MTP located in Network Site 2, the media flows through the WAN link.</span></span> <span data-ttu-id="1c3a1-160">因此, 對於每個 PSTN 會話, 都會執行兩個 CAC 檢查:</span><span class="sxs-lookup"><span data-stu-id="1c3a1-160">Therefore, for each PSTN session two CAC checks are performed:</span></span>

- <span data-ttu-id="1c3a1-161">在商務用 Skype 用戶端應用程式與中繼伺服器之間</span><span class="sxs-lookup"><span data-stu-id="1c3a1-161">Between the Skype for Business client application and the Mediation Server</span></span>

- <span data-ttu-id="1c3a1-162">在中繼伺服器與 PBX/MTP 之間</span><span class="sxs-lookup"><span data-stu-id="1c3a1-162">Between the Mediation Server and the PBX/MTP</span></span>

<span data-ttu-id="1c3a1-163">這適用于對網路 Site 1 中的用戶端進行撥入 PSTN 呼叫, 以及源自網路 Site 1 中用戶端的出局 PSTN 呼叫。</span><span class="sxs-lookup"><span data-stu-id="1c3a1-163">This works for both incoming PSTN calls to a client in Network Site 1, and outgoing PSTN calls originating from a client in Network Site 1.</span></span>

> [!NOTE]
> <span data-ttu-id="1c3a1-164">確認 MTP 所屬的 IP 子網已設定並與網路 Site 2 相關聯。</span><span class="sxs-lookup"><span data-stu-id="1c3a1-164">Make sure that the IP subnet that the MTP belongs to is configured and associated with Network Site 2.</span></span>

> [!NOTE]
> <span data-ttu-id="1c3a1-165">請確定已設定中繼伺服器的兩個介面所屬的 IP 子網, 並與網路 Site 1 產生關聯。</span><span class="sxs-lookup"><span data-stu-id="1c3a1-165">Make sure that the IP subnet that both interfaces of the Mediation Server belong to is configured and associated with Network Site 1.</span></span>

> [!NOTE]
> <span data-ttu-id="1c3a1-166">如需詳細資訊, 請參閱[將子網與網路網站建立關聯](https://technet.microsoft.com/library/aa69e3ac-542a-4ba1-9582-2e6bee29f633.aspx)。</span><span class="sxs-lookup"><span data-stu-id="1c3a1-166">For details, see [Associate a Subnet with a Network Site](https://technet.microsoft.com/library/aa69e3ac-542a-4ba1-9582-2e6bee29f633.aspx).</span></span>

### <a name="case-3-cac-between-the-mediation-server-and-a-third-party-pbx-without-a-media-termination-point"></a><span data-ttu-id="1c3a1-167">Case 3: 在中繼伺服器與協力廠商 PBX 之間的 CAC (不含媒體終止點)</span><span class="sxs-lookup"><span data-stu-id="1c3a1-167">Case 3: CAC between the Mediation Server and a third-party PBX without a Media Termination Point</span></span>

<span data-ttu-id="1c3a1-168">Case 3 與前兩個案例稍有不同。</span><span class="sxs-lookup"><span data-stu-id="1c3a1-168">Case 3 is slightly different from the first two cases.</span></span> <span data-ttu-id="1c3a1-169">如果在協力廠商 PBX 上沒有 MTP, 那麼對於協力廠商 PBX 的傳出會話要求, 中繼伺服器不知道媒體將在 PBX 邊界中終止的位置。</span><span class="sxs-lookup"><span data-stu-id="1c3a1-169">If there is no MTP on the third-party PBX, for an outgoing session request to the third-party PBX the Mediation Server does not know where media will terminate in the PBX boundary.</span></span> <span data-ttu-id="1c3a1-170">在這種情況下, 媒體會直接在中繼伺服器與協力廠商端點裝置之間流動。</span><span class="sxs-lookup"><span data-stu-id="1c3a1-170">In this case, the media flows directly between the Mediation Server and the third-party endpoint device.</span></span>

<span data-ttu-id="1c3a1-171">**Case 3: 在中繼伺服器與沒有 MTP 的協力廠商 PBX 之間使用 CAC**</span><span class="sxs-lookup"><span data-stu-id="1c3a1-171">**Case 3: CAC between the Mediation Server and a third-party PBX without MTP**</span></span>

![案例 3：中繼伺服器和不具有 MTP 之 PBX 間的 CAC](../../media/CAC_gateways_3.jpg)

<span data-ttu-id="1c3a1-173">在這個範例中, 如果網路網站1上的商務用 Skype 用戶端使用者是透過 PBX 撥打電話給使用者, 則轉送伺服器只能在 proxy 腿 (商務用 Skype 用戶端應用程式與中繼伺服器之間) 執行 CAC 檢查。</span><span class="sxs-lookup"><span data-stu-id="1c3a1-173">In this example, if a Skype for Business client user at Network Site 1 places a call to a user through the PBX, the Mediation Server is able to perform CAC checks only on the proxy leg (between the Skype for Business client application and Mediation Server).</span></span> <span data-ttu-id="1c3a1-174">因為在進行會話時, 中繼伺服器沒有端點裝置的相關資訊, 所以在通話建立之前, 無法在 WAN 連結 (在中繼伺服器與協力廠商端點之間) 執行 CAC 檢查。</span><span class="sxs-lookup"><span data-stu-id="1c3a1-174">Because the Mediation Server does not have information about the endpoint device while the session is being requested, CAC checks cannot be performed on the WAN link (between the Mediation Server and the third-party endpoint) prior to call establishment.</span></span> <span data-ttu-id="1c3a1-175">不過, 在建立會話之後, 中繼伺服器會針對主幹上使用的頻寬進行記帳。</span><span class="sxs-lookup"><span data-stu-id="1c3a1-175">After the session is established, however, the Mediation Server facilitates in accounting for the bandwidth used on the trunk.</span></span>

<span data-ttu-id="1c3a1-176">針對源自協力廠商端點的呼叫, 您可以在進行會話要求時, 在中繼伺服器端的兩面執行 CAC 檢查時, 提供該端點裝置的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="1c3a1-176">For calls that originate from the third-party endpoint, the information about that endpoint device is available at the time of session request and CAC check can be performed on both the sides of the Mediation Server.</span></span>

> [!NOTE]
> <span data-ttu-id="1c3a1-177">確認端點裝置所屬的 IP 子網已設定並與網路 Site 2 相關聯。</span><span class="sxs-lookup"><span data-stu-id="1c3a1-177">Make sure that the IP subnet that the endpoint devices belong to is configured and associated with Network Site 2.</span></span>

> [!NOTE]
> <span data-ttu-id="1c3a1-178">請確定已設定中繼伺服器的兩個介面所屬的 IP 子網, 並與網路 Site 1 產生關聯。</span><span class="sxs-lookup"><span data-stu-id="1c3a1-178">Make sure that the IP subnet that both interfaces of the Mediation Server belong to is configured and associated with Network Site 1.</span></span>

> [!NOTE]
> <span data-ttu-id="1c3a1-179">如需詳細資訊, 請參閱[將子網與網路網站建立關聯](https://technet.microsoft.com/library/aa69e3ac-542a-4ba1-9582-2e6bee29f633.aspx)。</span><span class="sxs-lookup"><span data-stu-id="1c3a1-179">For details, see [Associate a Subnet with a Network Site](https://technet.microsoft.com/library/aa69e3ac-542a-4ba1-9582-2e6bee29f633.aspx).</span></span>


