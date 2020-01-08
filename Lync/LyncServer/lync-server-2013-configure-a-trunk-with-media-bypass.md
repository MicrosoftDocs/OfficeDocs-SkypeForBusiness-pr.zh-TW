---
title: Lync Server 2013：使用 [旁路媒體] 設定主幹
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure a trunk with media bypass
ms:assetid: 99d729ea-5a4c-4ff2-a4a3-93a24368da6d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398792(v=OCS.15)
ms:contentKeyID: 48184959
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 41f5f254dfd3ad63d3f6390f16837c777bd02a91
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975602"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-a-trunk-with-media-bypass-in-lync-server-2013"></a><span data-ttu-id="46eec-102">在 Lync Server 2013 中使用 [旁路媒體] 設定主幹</span><span class="sxs-lookup"><span data-stu-id="46eec-102">Configure a trunk with media bypass in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="46eec-103">_**主題上次修改日期：** 2014-02-07_</span><span class="sxs-lookup"><span data-stu-id="46eec-103">_**Topic Last Modified:** 2014-02-07_</span></span>

<span data-ttu-id="46eec-104">請依照下列步驟來設定已啟用媒體旁路的幹線。</span><span class="sxs-lookup"><span data-stu-id="46eec-104">Follow these steps to configure a trunk with media bypass enabled.</span></span> <span data-ttu-id="46eec-105">若要設定停用媒體旁路的幹線，請參閱[在 Lync Server 2013 中設定沒有媒體旁路的幹線](lync-server-2013-configure-a-trunk-without-media-bypass.md)。</span><span class="sxs-lookup"><span data-stu-id="46eec-105">To configure a trunk with media bypass disabled, see [Configure a trunk without media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md).</span></span> <span data-ttu-id="46eec-106">如果您想要將部署的中繼伺服器數量減至最少，則可以使用 [媒體旁路]。</span><span class="sxs-lookup"><span data-stu-id="46eec-106">Media bypass is useful when you want to minimize the number of Mediation Servers deployed.</span></span> <span data-ttu-id="46eec-107">通常，會將中繼伺服器池部署在中央網站，它會控制分支網站上的閘道。</span><span class="sxs-lookup"><span data-stu-id="46eec-107">Typically, a Mediation Server pool will be deployed at a central site, and it will control gateways at branch sites.</span></span> <span data-ttu-id="46eec-108">啟用「媒體旁路」可讓您從分支網站上的用戶端直接透過閘道從分支網站傳送公用交換電話網絡（PSTN）通話的媒體。</span><span class="sxs-lookup"><span data-stu-id="46eec-108">Enabling media bypass allows media for public switched telephone network (PSTN) calls from clients at branch sites to flow directly through the gateways at those sites.</span></span> <span data-ttu-id="46eec-109">Lync Server 2013 出站通話路由及企業語音原則必須正確設定，才能將分支網站用戶端的 PSTN 呼叫路由至適當的閘道。</span><span class="sxs-lookup"><span data-stu-id="46eec-109">Lync Server 2013 outbound call routes and Enterprise Voice policies must be properly configured so that PSTN calls from clients at a branch site are routed to the appropriate gateway.</span></span>

<span data-ttu-id="46eec-110">我們強烈建議您啟用 [媒體旁路]。</span><span class="sxs-lookup"><span data-stu-id="46eec-110">We strongly recommend that you enable media bypass.</span></span> <span data-ttu-id="46eec-111">不過，在 SIP 主幹上啟用媒體旁路之前，請確認您的合格 SIP 幹線提供者支援媒體旁路，且能夠滿足成功啟用該案例的需求。</span><span class="sxs-lookup"><span data-stu-id="46eec-111">However, before you enable media bypass on a SIP trunk, confirm that your qualified SIP trunk provider supports media bypass and is able to accommodate the requirements for successfully enabling the scenario.</span></span> <span data-ttu-id="46eec-112">具體說來，提供者必須擁有貴組織內部網路中伺服器的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="46eec-112">Specifically, the provider must have the IP addresses of servers in your organization’s internal network.</span></span> <span data-ttu-id="46eec-113">如果提供者無法支援這個案例，媒體將無法成功。</span><span class="sxs-lookup"><span data-stu-id="46eec-113">If the provider cannot support this scenario, media bypass will not succeed.</span></span> <span data-ttu-id="46eec-114">如需詳細資訊，請參閱規劃檔中的[Lync Server 2013 中的媒體旁路規劃](lync-server-2013-planning-for-media-bypass.md)。</span><span class="sxs-lookup"><span data-stu-id="46eec-114">For details, see [Planning for media bypass in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) in the Planning documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="46eec-115">媒體旁路將無法與每個公開交換電話網絡（PSTN）閘道、IP PBX 和會話邊界控制器（SBC）進行交互操作。</span><span class="sxs-lookup"><span data-stu-id="46eec-115">Media bypass will not interoperate with every public switched telephone network (PSTN) gateway, IP-PBX, and Session Border Controller (SBC).</span></span> <span data-ttu-id="46eec-116">Microsoft 已經測試了一組 PSTN 閘道，並有已認證的合作夥伴，且已使用 Cisco IP-Pbx 進行了一些測試。</span><span class="sxs-lookup"><span data-stu-id="46eec-116">Microsoft has tested a set of PSTN gateways and SBCs with certified partners and has done some testing with Cisco IP-PBXs.</span></span> <span data-ttu-id="46eec-117">只有在整合通訊開啟互通性計畫（Lync Server at <A href="http://go.microsoft.com/fwlink/p/?linkid=214406">http://go.microsoft.com/fwlink/p/?linkId=214406</A>）中所列的產品和版本，才能支援媒體略過。</span><span class="sxs-lookup"><span data-stu-id="46eec-117">Media bypass is supported only with products and versions that are listed on Unified Communications Open Interoperability Program – Lync Server at <A href="http://go.microsoft.com/fwlink/p/?linkid=214406">http://go.microsoft.com/fwlink/p/?linkId=214406</A>.</span></span>



</div>

<span data-ttu-id="46eec-118">下面所述的主幹設定會將套用至 trunks 指派這個幹線設定的一組參數組成。</span><span class="sxs-lookup"><span data-stu-id="46eec-118">A trunk configuration as described below groups a set of parameters that are applied to trunks assigned this trunk configuration.</span></span> <span data-ttu-id="46eec-119">您可以將特定的主幹設定設為全域（所有 trunks，而不會有更具體的網站或池配置），或是到網站或池中。</span><span class="sxs-lookup"><span data-stu-id="46eec-119">A particular trunk configuration can be scoped globally (to all trunks that do not have more specific site or pool configuration), or to a site, or to a pool.</span></span> <span data-ttu-id="46eec-120">[池層級中繼] 設定是用來將特定主幹設定的範圍限定在單一干線中。</span><span class="sxs-lookup"><span data-stu-id="46eec-120">The pool-level trunk configuration is used to scope a specific trunk configuration to a single trunk.</span></span>

<span id="BKMK_ConfigTrunkMediaBypassSteps"></span>

<div>

## <a name="to-configure-a-trunk-with-media-bypass"></a><span data-ttu-id="46eec-121">使用 [旁路媒體] 設定主幹</span><span class="sxs-lookup"><span data-stu-id="46eec-121">To configure a trunk with media bypass</span></span>

1.  <span data-ttu-id="46eec-122">以 RTCUniversalServerAdmins 群組的成員或 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色的成員的身分登入電腦。</span><span class="sxs-lookup"><span data-stu-id="46eec-122">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="46eec-123">如需詳細資訊，請參閱[Lync Server 2013 中的委派設定許可權](lync-server-2013-delegate-setup-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="46eec-123">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="46eec-124">開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。</span><span class="sxs-lookup"><span data-stu-id="46eec-124">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="46eec-125">如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="46eec-125">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="46eec-126">在左側導覽列中，按一下 [**語音路由**]，然後按一下 [**幹線**設定]。</span><span class="sxs-lookup"><span data-stu-id="46eec-126">In the left navigation bar, click **Voice Routing**, and then click **Trunk Configuration**.</span></span>

4.  <span data-ttu-id="46eec-127">在 [**幹線**設定] 頁面上，使用下列其中一種方法來設定幹線：</span><span class="sxs-lookup"><span data-stu-id="46eec-127">On the **Trunk Configuration** page, use one of the following methods to configure a trunk:</span></span>
    
      - <span data-ttu-id="46eec-128">按兩下現有的幹線（例如，**全域**幹線），以顯示 [**編輯主幹**設定] 對話方塊。</span><span class="sxs-lookup"><span data-stu-id="46eec-128">Double-click an existing trunk (for example, the **Global** trunk) to display the **Edit Trunk Configuration** dialog box.</span></span>
    
      - <span data-ttu-id="46eec-129">按一下 [**新增**]，然後選取新主幹設定的範圍：</span><span class="sxs-lookup"><span data-stu-id="46eec-129">Click **New**, and then select a scope for the new trunk configuration:</span></span>
        
          - <span data-ttu-id="46eec-130">**網站主幹：** 從 [**選取網站**] 選擇此主幹設定的網站，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="46eec-130">**Site trunk:** Choose the site for this trunk configuration from **Select a Site**, and then click **OK**.</span></span> <span data-ttu-id="46eec-131">請注意，如果已為網站建立中繼設定，網站就不會出現在 [**選取網站**] 中。</span><span class="sxs-lookup"><span data-stu-id="46eec-131">Note that if a trunk configuration has already been created for a site, the site does not appear in **Select a Site**.</span></span> <span data-ttu-id="46eec-132">此主幹設定將會套用至網站中的所有 trunks。</span><span class="sxs-lookup"><span data-stu-id="46eec-132">This trunk configuration will be applied to all trunks in the site.</span></span>
        
          - <span data-ttu-id="46eec-133">**池主幹：** 選擇此幹線設定適用的主幹名稱。</span><span class="sxs-lookup"><span data-stu-id="46eec-133">**Pool trunk:** Choose the name of the trunk that this trunk configuration applies to.</span></span> <span data-ttu-id="46eec-134">這個幹線可以是根主幹或在拓撲建立器中定義的任何其他 trunks。</span><span class="sxs-lookup"><span data-stu-id="46eec-134">This trunk can be the root trunk or any additional trunks defined in Topology Builder.</span></span> <span data-ttu-id="46eec-135">從 [**選取服務**] 中，按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="46eec-135">From **Select a Service**, click **OK**.</span></span> <span data-ttu-id="46eec-136">請注意，如果已為特定主幹建立幹線設定，主幹不會出現在 [**選取服務**] 中。</span><span class="sxs-lookup"><span data-stu-id="46eec-136">Note that if a trunk configuration has already been created for a specific trunk, the trunk does not appear in **Select a Service**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="46eec-137">在您選取主幹設定的範圍之後，就無法變更它。</span><span class="sxs-lookup"><span data-stu-id="46eec-137">After you select the scope of the trunk configuration, it cannot be changed.</span></span><BR><span data-ttu-id="46eec-138">[ <STRONG>Name</STRONG> ] （名稱）欄位會填入與中繼設定的關聯網站或服務名稱，且無法變更。</span><span class="sxs-lookup"><span data-stu-id="46eec-138">The <STRONG>Name</STRONG> field is prepopulated with the name of the trunk configuration’s associated site or service and cannot be changed.</span></span>

    
    </div>

5.  <span data-ttu-id="46eec-139">在**支援的最大早期對話方塊**中指定值。</span><span class="sxs-lookup"><span data-stu-id="46eec-139">Specify a value in **Maximum early dialogs supported**.</span></span> <span data-ttu-id="46eec-140">這是公用交換電話網絡（PSTN）閘道、IP PBX 或 ITSP 會話邊界控制器（SBC）可接收傳送給轉送伺服器的邀請的數目上限。</span><span class="sxs-lookup"><span data-stu-id="46eec-140">This is the maximum number of forked responses a public switched telephone network (PSTN) gateway, IP-PBX, or ITSP Session Border Controller (SBC) can receive to an INVITE that it sent to the Mediation Server.</span></span> <span data-ttu-id="46eec-141">預設值為20。</span><span class="sxs-lookup"><span data-stu-id="46eec-141">The default value is 20.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="46eec-142">變更此值前，請諮詢您的服務提供者或設備製造商，以取得系統功能的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="46eec-142">Before you change this value, consult your service provider or equipment manufacturer for details about the capabilities of your system.</span></span>

    
    </div>

6.  <span data-ttu-id="46eec-143">選取下列其中一個**加密支援等級**選項：</span><span class="sxs-lookup"><span data-stu-id="46eec-143">Select one of the following **Encryption support level** options:</span></span>
    
      - <span data-ttu-id="46eec-144">**必要：** 安全即時傳輸通訊協定（SRTP）加密必須用來協助保護中繼伺服器與閘道或私人分支 exchange （PBX）之間的流量。</span><span class="sxs-lookup"><span data-stu-id="46eec-144">**Required:** Secure real-time transport protocol (SRTP) encryption must be used to help protect traffic between the Mediation Server and the gateway or private branch exchange (PBX).</span></span>
    
      - <span data-ttu-id="46eec-145">**選用：** 如果服務提供者或設備製造商支援，則會使用 SRTP 加密。</span><span class="sxs-lookup"><span data-stu-id="46eec-145">**Optional:** SRTP encryption will be used if the service provider or equipment manufacturer supports it.</span></span>
    
      - <span data-ttu-id="46eec-146">**不支援：** 服務提供者或設備製造商不支援 SRTP 加密，因此將無法使用。</span><span class="sxs-lookup"><span data-stu-id="46eec-146">**Not Supported:** SRTP encryption is not supported by the service provider or equipment manufacturer and therefore will not be used.</span></span>

7.  <span data-ttu-id="46eec-147">如果您想要媒體略過中繼伺服器以進行中繼對等處理，請選取 [**啟用媒體旁路**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="46eec-147">Select the **Enable media bypass** check box if you want media to bypass the Mediation Server for processing by the trunk peer.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="46eec-148">若要讓媒體旁路功能順利運作，PSTN 閘道、IP PBX 或 ITSP 會話框線控制器必須支援某些功能。</span><span class="sxs-lookup"><span data-stu-id="46eec-148">For media bypass to work successfully, the PSTN gateway, IP-PBX, or ITSP Session Border Controller must support certain capabilities.</span></span> <span data-ttu-id="46eec-149">如需詳細資訊，請參閱規劃檔中的<A href="lync-server-2013-planning-for-media-bypass.md">Lync Server 2013 中的媒體旁路規劃</A>。</span><span class="sxs-lookup"><span data-stu-id="46eec-149">For details, see <A href="lync-server-2013-planning-for-media-bypass.md">Planning for media bypass in Lync Server 2013</A> in the Planning documentation.</span></span>

    
    </div>

8.  <span data-ttu-id="46eec-150">如果有已知的媒體端接點，請選取 [**集中式媒體處理**] 核取方塊（例如，媒體端接的 PSTN 閘道與 [信號終止] 一樣）。</span><span class="sxs-lookup"><span data-stu-id="46eec-150">Select the **Centralized media processing** check box if there is a well-known media termination point (for example, a PSTN gateway where the media termination has the same IP as the signaling termination).</span></span> <span data-ttu-id="46eec-151">如果主幹沒有已知的媒體端接點，請清除此核取方塊。</span><span class="sxs-lookup"><span data-stu-id="46eec-151">Clear this check box if the trunk does not have a well-known media termination point.</span></span>

9.  <span data-ttu-id="46eec-152">如果乾線對等支援接收來自中繼伺服器的 SIP，請選取 [**啟用傳送參照至閘道**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="46eec-152">If the trunk peer supports receiving SIP REFER requests from the Mediation Server, select the **Enable sending refer to the gateway** check box.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="46eec-153">如果您在已選取 [<STRONG>啟用媒體旁路</STRONG>] 選項時停用此選項，則需要其他設定。</span><span class="sxs-lookup"><span data-stu-id="46eec-153">If you disable this option while the <STRONG>Enable media bypass</STRONG> option is selected, additional settings are required.</span></span> <span data-ttu-id="46eec-154">如果乾線對等不支援接收來自中繼伺服器和媒體旁路的 SIP 參照要求，您也必須執行<STRONG>new-cstrunkconfiguration</STRONG> Cmdlet 來停用使用中及保留通話的 RTCP，以支援媒體旁路的正確情況。</span><span class="sxs-lookup"><span data-stu-id="46eec-154">If the trunk peer does not support receiving SIP REFER requests from the Mediation Server and media bypass is enabled, you must also run the <STRONG>Set-CsTrunkConfiguration</STRONG> cmdlet to disable RTCP for active and held calls in order to support proper conditions for media bypass.</span></span> <span data-ttu-id="46eec-155">如需詳細資訊，請參閱<A href="lync-server-2013-lync-server-management-shell.md">Lync Server 2013 管理命令</A>介面檔。</span><span class="sxs-lookup"><span data-stu-id="46eec-155">For details, see the <A href="lync-server-2013-lync-server-management-shell.md">Lync Server 2013 Management Shell</A> documentation.</span></span><BR><span data-ttu-id="46eec-156">或者，如果您想要將轉接來電轉接給媒體，且閘道不支援 SIP，請選取 [<STRONG>使用協力廠商通話的參照</STRONG>]。</span><span class="sxs-lookup"><span data-stu-id="46eec-156">Alternatively, you can select <STRONG>Enable refer using third-party-call control</STRONG> if you want transferred calls to be media bypassed, and the gateway does not support SIP REFER requests.</span></span>

    
    </div>

10. <span data-ttu-id="46eec-157">可選若要啟用站間路由，請將 PSTN 使用記錄關聯並設定為此主幹設定。</span><span class="sxs-lookup"><span data-stu-id="46eec-157">(Optional) To enable inter-trunk routing, associate and configure PSTN usage records to this trunk configuration.</span></span> <span data-ttu-id="46eec-158">與此幹線設定相關聯的 PSTN 用法，將會針對並非來自 Lync 端點之幹線的所有撥入電話套用。</span><span class="sxs-lookup"><span data-stu-id="46eec-158">The PSTN usages associated to this trunk configuration will be applied for all incoming calls through the trunk that is not originating from a Lync endpoint.</span></span> <span data-ttu-id="46eec-159">若要管理與幹線設定相關聯的 PSTN 使用記錄，請使用下列其中一種方法：</span><span class="sxs-lookup"><span data-stu-id="46eec-159">To manage PSTN usage records associated to a trunk configuration, use one of the following methods:</span></span>
    
      - <span data-ttu-id="46eec-160">若要從企業語音部署中所有可用的 PSTN 使用記錄清單中選取一或多筆記錄，請按一下 [**選取**]。</span><span class="sxs-lookup"><span data-stu-id="46eec-160">To select one or more records from a list of all PSTN usage records available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="46eec-161">醒目提示您要與此主幹設定關聯的記錄，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="46eec-161">Highlight the records you want to associate with this trunk configuration and then click **OK**.</span></span>
    
      - <span data-ttu-id="46eec-162">若要從此幹線設定中移除 PSTN 使用記錄，請選取該記錄，然後按一下 [**移除**]。</span><span class="sxs-lookup"><span data-stu-id="46eec-162">To remove a PSTN usage record from this trunk configuration, select the record and click **Remove**.</span></span>
    
      - <span data-ttu-id="46eec-163">若要定義新的 PSTN 使用記錄，並將它與此幹線設定關聯，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="46eec-163">To define a new PSTN usage record and associate it with this trunk configuration, do the following:</span></span>
        
        1.  <span data-ttu-id="46eec-164">按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="46eec-164">Click **New**.</span></span>
        
        2.  <span data-ttu-id="46eec-165">在 [**名稱**] 欄位中，為記錄指定唯一的描述性名稱。</span><span class="sxs-lookup"><span data-stu-id="46eec-165">In the **Name** field, specify a descriptive name for the record that is unique.</span></span>
            
            <div>
            

            > [!NOTE]  
            > <span data-ttu-id="46eec-166">PSTN 使用記錄名稱在企業語音部署中必須是唯一的。</span><span class="sxs-lookup"><span data-stu-id="46eec-166">The PSTN usage record name must be unique within the Enterprise Voice deployment.</span></span> <span data-ttu-id="46eec-167">在儲存記錄之後，[<STRONG>名稱</STRONG>] 欄位就無法進行編輯。</span><span class="sxs-lookup"><span data-stu-id="46eec-167">After the record is saved, the <STRONG>Name</STRONG> field cannot be edited.</span></span>

            
            </div>
        
        3.  <span data-ttu-id="46eec-168">使用下列其中一種方法來關聯及設定此 PSTN 使用記錄的路線：</span><span class="sxs-lookup"><span data-stu-id="46eec-168">Use one of the following methods to associate and configure routes for this PSTN usage record:</span></span>
            
              - <span data-ttu-id="46eec-169">若要從企業語音部署中所有可用路由的清單中選取一或多個路由，請按一下 [**選取**]。</span><span class="sxs-lookup"><span data-stu-id="46eec-169">To select one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="46eec-170">醒目提示您想要與此 PSTN 使用記錄產生關聯的路線，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="46eec-170">Highlight the routes you want to associate with this PSTN usage record, and click **OK**.</span></span>
            
              - <span data-ttu-id="46eec-171">若要從 PSTN 使用量記錄移除路由，請選取路由，然後按一下 [**移除**]。</span><span class="sxs-lookup"><span data-stu-id="46eec-171">To remove a route from the PSTN usage record, select the route, and click **Remove**.</span></span>
            
              - <span data-ttu-id="46eec-172">若要定義新的路由，並將它與此 PSTN 使用記錄建立關聯，請按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="46eec-172">To define a new route and associate it to this PSTN usage record, click **New**.</span></span> <span data-ttu-id="46eec-173">如需詳細資訊，請參閱[在 Lync Server 2013 中建立語音路由](lync-server-2013-create-a-voice-route.md)。</span><span class="sxs-lookup"><span data-stu-id="46eec-173">For details, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>
            
              - <span data-ttu-id="46eec-174">若要編輯與此 PSTN 使用記錄相關聯的路線，請選取該路線，然後按一下 [**顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="46eec-174">To edit a route that is associated with this PSTN usage record, select the route, and click **Show details**.</span></span> <span data-ttu-id="46eec-175">如需詳細資訊，請參閱[在 Lync Server 2013 中修改語音路線](lync-server-2013-modify-a-voice-route.md)。</span><span class="sxs-lookup"><span data-stu-id="46eec-175">For details, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span></span>
        
        4.  <span data-ttu-id="46eec-176">按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="46eec-176">Click **OK**.</span></span>
    
      - <span data-ttu-id="46eec-177">若要編輯已與此幹線設定關聯的 PSTN 使用記錄，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="46eec-177">To edit a PSTN usage record that is already associated with this trunk configuration, do the following:</span></span>
        
        1.  <span data-ttu-id="46eec-178">選取您要編輯的 PSTN 使用量記錄，然後按一下 [**顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="46eec-178">Select the PSTN usage record you want to edit, and click **Show details**.</span></span>
        
        2.  <span data-ttu-id="46eec-179">使用下列其中一種方法來關聯及設定此 PSTN 使用記錄的路線：</span><span class="sxs-lookup"><span data-stu-id="46eec-179">Use one of the following methods to associate and configure routes for this PSTN usage record:</span></span>
            
              - <span data-ttu-id="46eec-180">若要從企業語音部署中所有可用路由的清單中選取一或多個路由，請按一下 [**選取**]。</span><span class="sxs-lookup"><span data-stu-id="46eec-180">To select one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="46eec-181">醒目提示您想要與此 PSTN 使用記錄產生關聯的路線，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="46eec-181">Highlight the routes you want to associate with this PSTN usage record, and click **OK**.</span></span>
            
              - <span data-ttu-id="46eec-182">若要從 PSTN 使用量記錄移除路由，請選取路由，然後按一下 [**移除**]。</span><span class="sxs-lookup"><span data-stu-id="46eec-182">To remove a route from the PSTN usage record, select the route, and click **Remove**.</span></span>
            
              - <span data-ttu-id="46eec-183">若要定義新的路由，並將它與此 PSTN 使用記錄建立關聯，請按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="46eec-183">To define a new route and associate it to this PSTN usage record, click **New**.</span></span> <span data-ttu-id="46eec-184">如需詳細資訊，請參閱[在 Lync Server 2013 中建立語音路由](lync-server-2013-create-a-voice-route.md)。</span><span class="sxs-lookup"><span data-stu-id="46eec-184">For details, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>
            
              - <span data-ttu-id="46eec-185">若要編輯與此 PSTN 使用記錄相關聯的路線，請選取該路線，然後按一下 [**顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="46eec-185">To edit a route that is associated with this PSTN usage record, select the route, and click **Show details**.</span></span> <span data-ttu-id="46eec-186">如需詳細資訊，請參閱[在 Lync Server 2013 中修改語音路線](lync-server-2013-modify-a-voice-route.md)。</span><span class="sxs-lookup"><span data-stu-id="46eec-186">For details, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span></span>
        
        3.  <span data-ttu-id="46eec-187">按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="46eec-187">Click **OK**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="46eec-188">將 PSTN 使用記錄與正在設定主幹的中繼伺服器對等相關聯是很重要的。</span><span class="sxs-lookup"><span data-stu-id="46eec-188">It important to associate PSTN usage records according to the Mediation Server peer that is associated to the trunk being configured.</span></span> <span data-ttu-id="46eec-189">如果中繼伺服器對等是 PSTN 閘道或會話邊界控制器（SBC），強烈建議您不要將幹線設定與路由至 PSTN 目的地的 PSTN 使用記錄或任何其他透過 Lync 連接的任何其他下游系統關聯伺服器.</span><span class="sxs-lookup"><span data-stu-id="46eec-189">If the Mediation Server peer is a PSTN gateway or a Session Border Controller (SBC), it is strongly recommended that the trunk configuration is not associated to a PSTN usage record that routes to a PSTN destination or any other downstream systems connected via Lync Server.</span></span>

    
    </div>

11. <span data-ttu-id="46eec-190">排列 PSTN 使用狀況記錄，以獲得最佳效能。</span><span class="sxs-lookup"><span data-stu-id="46eec-190">Arrange the PSTN usage records for optimum performance.</span></span> <span data-ttu-id="46eec-191">若要變更記錄在清單中的位置，請選取 PSTN 使用記錄，然後按一下向上或向下箭號。</span><span class="sxs-lookup"><span data-stu-id="46eec-191">To change a record’s position in the list, select the PSTN usage record, and click the up or down arrows.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="46eec-192">PSTN 使用記錄在幹線設定中的顯示順序非常重要。</span><span class="sxs-lookup"><span data-stu-id="46eec-192">The order in which PSTN usage records are listed in the trunk configuration is significant.</span></span> <span data-ttu-id="46eec-193">Lync Server 會從上到下遍歷清單。</span><span class="sxs-lookup"><span data-stu-id="46eec-193">Lync Server traverses the list from top to down.</span></span>

    
    </div>

12. <span data-ttu-id="46eec-194">應選取 [**啟用 RTP 閉鎖**]，以針對網路位址轉譯（NAT）或防火牆以及支援閂鎖的 SBC 啟用旁路媒體。</span><span class="sxs-lookup"><span data-stu-id="46eec-194">**Enable RTP Latching** should be selected to enable bypass media for clients behind a network address translation (NAT) or firewall and an SBC that supports latching.</span></span>

13. <span data-ttu-id="46eec-195">應選取 [**啟用轉寄通話記錄**]，以允許將通話記錄資訊傳送到中繼伺服器的閘道對等。</span><span class="sxs-lookup"><span data-stu-id="46eec-195">**Enable forward call history** should be selected to enable sending of call history information to the gateway peer of the Mediation Server.</span></span>

14. <span data-ttu-id="46eec-196">[**啟用前 p-已斷言身分識別的資料**] 請選取 [啟用 p 斷言身分識別（PAI）] 呼叫始發者資訊，以便在中繼伺服器端和閘道端（反之亦然）之間轉寄。</span><span class="sxs-lookup"><span data-stu-id="46eec-196">**Enable forward P-Asserted-Identity data** should be selected to enable the P-Asserted-Identity (PAI) call originator information to be forwarded between the Mediation Server side and gateway side (and vice versa), when present.</span></span>

15. <span data-ttu-id="46eec-197">若要啟用快速容錯移轉，請選取 [**啟用輸出路由容錯移轉計時器**]。</span><span class="sxs-lookup"><span data-stu-id="46eec-197">**Enable outbound routing failover timer** should be selected to enable fast failover.</span></span> <span data-ttu-id="46eec-198">與此幹線關聯的閘道可以在處理撥出通話的10秒內發出通知。</span><span class="sxs-lookup"><span data-stu-id="46eec-198">The gateway associated with this trunk can give notification within 10 seconds that it is processing an outbound call.</span></span> <span data-ttu-id="46eec-199">如果中繼伺服器未收到此通知，就會將重新路由至另一個主幹。</span><span class="sxs-lookup"><span data-stu-id="46eec-199">Rerouting to another trunk will occur if this notification is not received by the Mediation Server.</span></span> <span data-ttu-id="46eec-200">在延遲可能會延遲回應時間的網路上，或閘道需要10秒以上的時間才能回應，就應該停用 [快速容錯移轉]。</span><span class="sxs-lookup"><span data-stu-id="46eec-200">On networks where latency may delay the response time or the gateway takes longer than 10 seconds to respond, the fast failover should be disabled.</span></span>

16. <span data-ttu-id="46eec-201">可選關聯並設定主幹的**通話數轉譯規則**。</span><span class="sxs-lookup"><span data-stu-id="46eec-201">(Optional) Associate and configure **calling number translation rules** for the trunk.</span></span> <span data-ttu-id="46eec-202">這些翻譯規則會套用至撥出通話的電話號碼</span><span class="sxs-lookup"><span data-stu-id="46eec-202">These translation rules apply to the calling number for outbound calls</span></span>
    
      - <span data-ttu-id="46eec-203">若要從企業語音部署中提供的所有翻譯規則清單中選擇一或多個規則，請按一下 [**選取**]。</span><span class="sxs-lookup"><span data-stu-id="46eec-203">To choose one or more rules from a list of all translation rules that are available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="46eec-204">在 [**選取翻譯規則**] 中，按一下您要與主幹建立關聯的規則，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="46eec-204">In **Select Translation Rules**, click the rules that you want to associate with the trunk, and then click **OK**.</span></span>
    
      - <span data-ttu-id="46eec-205">若要定義新的翻譯規則，並將其與骨幹建立關聯，請按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="46eec-205">To define a new translation rule and associate it with the trunk, click **New**.</span></span> <span data-ttu-id="46eec-206">如需有關定義新規則的詳細資料，請參閱在部署檔中的[Lync Server 2013 中定義翻譯規則](lync-server-2013-defining-translation-rules.md)。</span><span class="sxs-lookup"><span data-stu-id="46eec-206">For details about defining a new rule, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="46eec-207">若要編輯已經與主幹建立關聯的翻譯規則，請按一下規則名稱，然後按一下 [**顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="46eec-207">To edit a translation rule that is already associated with the trunk, click the rule name, and then click **Show details**.</span></span> <span data-ttu-id="46eec-208">如需詳細資訊，請參閱在部署檔中的[Lync Server 2013 定義翻譯規則](lync-server-2013-defining-translation-rules.md)。</span><span class="sxs-lookup"><span data-stu-id="46eec-208">For details, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="46eec-209">若要複製現有的翻譯規則，以做為定義新規則的起點，請按一下規則名稱，然後按一下 [**複製**]，然後按一下 [**貼**上]。</span><span class="sxs-lookup"><span data-stu-id="46eec-209">To copy an existing translation rule to use as a starting point for defining a new rule, click the rule name and click **Copy**, and then click **Paste**.</span></span> <span data-ttu-id="46eec-210">如需詳細資訊，請參閱[在 Lync Server 2013 中定義翻譯規則](lync-server-2013-defining-translation-rules.md)。</span><span class="sxs-lookup"><span data-stu-id="46eec-210">For details, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md).</span></span>
    
      - <span data-ttu-id="46eec-211">若要從主幹中移除翻譯規則，請將規則名稱醒目提示，然後按一下 [**移除**]。</span><span class="sxs-lookup"><span data-stu-id="46eec-211">To remove a translation rule from the trunk, highlight the rule name and click **Remove**.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="46eec-212">如果您已在關聯的中繼對等上設定翻譯規則，請不要將翻譯規則與幹線建立關聯，因為這兩個規則可能會衝突。</span><span class="sxs-lookup"><span data-stu-id="46eec-212">Do not associate translation rules with a trunk if you have configured translation rules on the associated trunk peer, because the two rules might conflict.</span></span>

    
    </div>

17. <span data-ttu-id="46eec-213">可選關聯並設定主幹的已**呼叫數位轉譯規則**。</span><span class="sxs-lookup"><span data-stu-id="46eec-213">(Optional) Associate and configure **called number translation rules** for the trunk.</span></span> <span data-ttu-id="46eec-214">翻譯規則會套用至撥出通話中呼叫的號碼。</span><span class="sxs-lookup"><span data-stu-id="46eec-214">The translation rules apply to the called number in an outbound call.</span></span>
    
      - <span data-ttu-id="46eec-215">若要從企業語音部署中提供的所有翻譯規則清單中選擇一或多個規則，請按一下 [**選取**]。</span><span class="sxs-lookup"><span data-stu-id="46eec-215">To choose one or more rules from a list of all translation rules that are available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="46eec-216">在 [**選取翻譯規則**] 中，按一下您要與主幹建立關聯的規則，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="46eec-216">In **Select Translation Rules**, click the rules that you want to associate with the trunk, and then click **OK**.</span></span>
    
      - <span data-ttu-id="46eec-217">若要定義新的翻譯規則，並將其與骨幹建立關聯，請按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="46eec-217">To define a new translation rule and associate it with the trunk, click **New**.</span></span> <span data-ttu-id="46eec-218">如需有關定義新規則的詳細資料，請參閱在部署檔中的[Lync Server 2013 中定義翻譯規則](lync-server-2013-defining-translation-rules.md)。</span><span class="sxs-lookup"><span data-stu-id="46eec-218">For details about defining a new rule, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="46eec-219">若要編輯已經與主幹建立關聯的翻譯規則，請按一下規則名稱，然後按一下 [**顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="46eec-219">To edit a translation rule that is already associated with the trunk, click the rule name, and then click **Show details**.</span></span> <span data-ttu-id="46eec-220">如需詳細資訊，請參閱在部署檔中的[Lync Server 2013 定義翻譯規則](lync-server-2013-defining-translation-rules.md)。</span><span class="sxs-lookup"><span data-stu-id="46eec-220">For details, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="46eec-221">若要複製現有的翻譯規則，以做為定義新規則的起點，請按一下規則名稱，然後按一下 [**複製**]，然後按一下 [**貼**上]。</span><span class="sxs-lookup"><span data-stu-id="46eec-221">To copy an existing translation rule to use as a starting point for defining a new rule, click the rule name and click **Copy**, and then click **Paste**.</span></span> <span data-ttu-id="46eec-222">如需詳細資訊，請參閱[在 Lync Server 2013 中定義翻譯規則](lync-server-2013-defining-translation-rules.md)。</span><span class="sxs-lookup"><span data-stu-id="46eec-222">For details, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md).</span></span>
    
      - <span data-ttu-id="46eec-223">若要從主幹中移除翻譯規則，請將規則名稱醒目提示，然後按一下 [**移除**]。</span><span class="sxs-lookup"><span data-stu-id="46eec-223">To remove a translation rule from the trunk, highlight the rule name and click **Remove**.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="46eec-224">如果您已在關聯的中繼對等上設定翻譯規則，請不要將翻譯規則與幹線建立關聯，因為這兩個規則可能會衝突。</span><span class="sxs-lookup"><span data-stu-id="46eec-224">Do not associate translation rules with a trunk if you have configured translation rules on the associated trunk peer, because the two rules might conflict.</span></span>

    
    </div>

18. <span data-ttu-id="46eec-225">確定主幹的轉譯規則依正確順序排列。</span><span class="sxs-lookup"><span data-stu-id="46eec-225">Make sure that the trunk’s translation rules are arranged in the correct order.</span></span> <span data-ttu-id="46eec-226">若要變更規則在清單中的位置，請醒目提示 [規則名稱]，然後按一下向上或向下箭號。</span><span class="sxs-lookup"><span data-stu-id="46eec-226">To change a rule’s position in the list, highlight the rule name and then click the up or down arrow.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="46eec-227">Lync Server 2013 會從上到下遍歷翻譯規則清單，並使用與撥打的號碼相符的第一個規則。</span><span class="sxs-lookup"><span data-stu-id="46eec-227">Lync Server 2013 traverses the translation rule list from the top down and uses the first rule that matches the dialed number.</span></span> <span data-ttu-id="46eec-228">如果您設定幹線，讓撥入的號碼可以符合多個翻譯規則，請確定更嚴格的規則，在限制性較低的規則之上排序。</span><span class="sxs-lookup"><span data-stu-id="46eec-228">If you configure a trunk so that a dialed number can match more than one translation rule, be sure that the more restrictive rules are sorted above the less restrictive rules.</span></span> <span data-ttu-id="46eec-229">例如，如果您已包含符合任何11位數的翻譯規則，以及只符合以 + 1425 開頭的11位數的翻譯規則，請確定符合任何11位數的規則，以更嚴格的<EM>規則排序。</EM></span><span class="sxs-lookup"><span data-stu-id="46eec-229">For example, if you have included a translation rule that matches any 11-digit number and a translation rule that matches only 11-digit numbers that start with +1425, be sure that the rule that matches any 11-digit number is sorted <EM>below</EM> the more restrictive rule.</span></span>

    
    </div>

19. <span data-ttu-id="46eec-230">當您完成設定主幹時，請按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="46eec-230">When you are finished configuring the trunk, click **OK**.</span></span>

20. <span data-ttu-id="46eec-231">在 [**幹線**設定] 頁面上，按一下 [**認可**]，然後按一下 [**全部確認**]。</span><span class="sxs-lookup"><span data-stu-id="46eec-231">On the **Trunk Configuration** page, click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="46eec-232">每當您建立或修改幹線設定時，您都必須執行 [<STRONG>全部提交</STRONG>] 命令才能發佈設定變更。</span><span class="sxs-lookup"><span data-stu-id="46eec-232">Whenever you create or modify a trunk configuration, you must run the <STRONG>Commit all</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="46eec-233">如需詳細資訊，請參閱在 Operations 檔中<A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">發佈 Lync Server 2013 中的語音路由設定的未決變更</A>。</span><span class="sxs-lookup"><span data-stu-id="46eec-233">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

<span data-ttu-id="46eec-234">在您設定主幹之後，請選擇 [全域媒體旁路] 選項，繼續設定媒體旁路，如在部署檔中的[Lync Server 2013 的全域媒體旁路選項](lync-server-2013-global-media-bypass-options.md)中所述。</span><span class="sxs-lookup"><span data-stu-id="46eec-234">After you have configured the trunk, continue configuring media bypass by choosing between global media bypass options, as described in [Global media bypass options in Lync Server 2013](lync-server-2013-global-media-bypass-options.md) in the Deployment documentation.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="46eec-235">請參閱</span><span class="sxs-lookup"><span data-stu-id="46eec-235">See Also</span></span>


[<span data-ttu-id="46eec-236">在 Lync Server 2013 中設定沒有媒體旁路的主幹</span><span class="sxs-lookup"><span data-stu-id="46eec-236">Configure a trunk without media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-without-media-bypass.md)  


[<span data-ttu-id="46eec-237">在 Lync Server 2013 中設定媒體旁路</span><span class="sxs-lookup"><span data-stu-id="46eec-237">Configure media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-media-bypass.md)  
[<span data-ttu-id="46eec-238">Lync Server 2013 中的全域媒體旁路選項</span><span class="sxs-lookup"><span data-stu-id="46eec-238">Global media bypass options in Lync Server 2013</span></span>](lync-server-2013-global-media-bypass-options.md)  


[<span data-ttu-id="46eec-239">在 Lync Server 2013 中定義轉譯規則</span><span class="sxs-lookup"><span data-stu-id="46eec-239">Defining translation rules in Lync Server 2013</span></span>](lync-server-2013-defining-translation-rules.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

