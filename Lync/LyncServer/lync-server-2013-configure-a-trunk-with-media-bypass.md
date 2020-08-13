---
title: Lync Server 2013：設定具有媒體旁路的主幹
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure a trunk with media bypass
ms:assetid: 99d729ea-5a4c-4ff2-a4a3-93a24368da6d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398792(v=OCS.15)
ms:contentKeyID: 48184959
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 256962ace879c9d418d877b94f15227959177407
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42206939"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-a-trunk-with-media-bypass-in-lync-server-2013"></a><span data-ttu-id="3cf6e-102">在 Lync Server 2013 中設定含媒體旁路的主幹</span><span class="sxs-lookup"><span data-stu-id="3cf6e-102">Configure a trunk with media bypass in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3cf6e-103">_**主題上次修改日期：** 2014-02-07_</span><span class="sxs-lookup"><span data-stu-id="3cf6e-103">_**Topic Last Modified:** 2014-02-07_</span></span>

<span data-ttu-id="3cf6e-104">請遵循下列步驟，設定啟用媒體旁路的主幹。</span><span class="sxs-lookup"><span data-stu-id="3cf6e-104">Follow these steps to configure a trunk with media bypass enabled.</span></span> <span data-ttu-id="3cf6e-105">若要設定停用媒體旁路的主幹，請參閱[在 Lync Server 2013 中設定無媒體旁路的主幹](lync-server-2013-configure-a-trunk-without-media-bypass.md)。</span><span class="sxs-lookup"><span data-stu-id="3cf6e-105">To configure a trunk with media bypass disabled, see [Configure a trunk without media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md).</span></span> <span data-ttu-id="3cf6e-106">當您想要將已部署的轉送伺服器數目降至最低時，媒體旁路很有用。</span><span class="sxs-lookup"><span data-stu-id="3cf6e-106">Media bypass is useful when you want to minimize the number of Mediation Servers deployed.</span></span> <span data-ttu-id="3cf6e-107">一般來說，轉送伺服器集區會部署在中央網站，它會控制分支網站上的閘道。</span><span class="sxs-lookup"><span data-stu-id="3cf6e-107">Typically, a Mediation Server pool will be deployed at a central site, and it will control gateways at branch sites.</span></span> <span data-ttu-id="3cf6e-108">啟用媒體旁路允許公用交換電話網路的媒體 (PSTN) 來自分支網站用戶端的呼叫，以直接透過這些網站上的閘道來流向。</span><span class="sxs-lookup"><span data-stu-id="3cf6e-108">Enabling media bypass allows media for public switched telephone network (PSTN) calls from clients at branch sites to flow directly through the gateways at those sites.</span></span> <span data-ttu-id="3cf6e-109">Lync Server 2013 輸出呼叫路由和 Enterprise Voice 原則必須正確設定，才能讓來自分支網站之用戶端的 PSTN 呼叫路由傳送至適當的閘道。</span><span class="sxs-lookup"><span data-stu-id="3cf6e-109">Lync Server 2013 outbound call routes and Enterprise Voice policies must be properly configured so that PSTN calls from clients at a branch site are routed to the appropriate gateway.</span></span>

<span data-ttu-id="3cf6e-110">強烈建議您啟用媒體旁路。</span><span class="sxs-lookup"><span data-stu-id="3cf6e-110">We strongly recommend that you enable media bypass.</span></span> <span data-ttu-id="3cf6e-111">不過，在 SIP 主幹上啟用媒體旁路之前，請先確認您合格的 SIP 主幹提供者支援媒體旁路，而且能夠滿足成功啟用此案例的需求。</span><span class="sxs-lookup"><span data-stu-id="3cf6e-111">However, before you enable media bypass on a SIP trunk, confirm that your qualified SIP trunk provider supports media bypass and is able to accommodate the requirements for successfully enabling the scenario.</span></span> <span data-ttu-id="3cf6e-112">具體而言，提供者必須具有組織內部網路中伺服器的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="3cf6e-112">Specifically, the provider must have the IP addresses of servers in your organization’s internal network.</span></span> <span data-ttu-id="3cf6e-113">如果提供者無法支援此案例，媒體旁路將會失敗。</span><span class="sxs-lookup"><span data-stu-id="3cf6e-113">If the provider cannot support this scenario, media bypass will not succeed.</span></span> <span data-ttu-id="3cf6e-114">如需詳細資訊，請參閱規劃檔中的[規劃 Lync Server 2013 中的媒體旁路](lync-server-2013-planning-for-media-bypass.md)。</span><span class="sxs-lookup"><span data-stu-id="3cf6e-114">For details, see [Planning for media bypass in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) in the Planning documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3cf6e-115">媒體旁路不會與每一部公用交換電話網路 (PSTN) 閘道、IP-PBX 和會話邊界控制器 (SBC) 互動。</span><span class="sxs-lookup"><span data-stu-id="3cf6e-115">Media bypass will not interoperate with every public switched telephone network (PSTN) gateway, IP-PBX, and Session Border Controller (SBC).</span></span> <span data-ttu-id="3cf6e-116">Microsoft 已測試一組 PSTN 閘道，並與認證的協力廠商 SBCs，並利用 Cisco IP PBXs 進行一些測試。</span><span class="sxs-lookup"><span data-stu-id="3cf6e-116">Microsoft has tested a set of PSTN gateways and SBCs with certified partners and has done some testing with Cisco IP-PBXs.</span></span> <span data-ttu-id="3cf6e-117">只有在整合通訊開啟互通性計畫– Lync Server at 上列出的產品及版本，才支援媒體旁路 <A href="https://go.microsoft.com/fwlink/p/?linkid=214406">https://go.microsoft.com/fwlink/p/?linkId=214406</A> 。</span><span class="sxs-lookup"><span data-stu-id="3cf6e-117">Media bypass is supported only with products and versions that are listed on Unified Communications Open Interoperability Program – Lync Server at <A href="https://go.microsoft.com/fwlink/p/?linkid=214406">https://go.microsoft.com/fwlink/p/?linkId=214406</A>.</span></span>



</div>

<span data-ttu-id="3cf6e-118">如下所述的主幹設定群組一組套用至主幹指派此主幹設定的參數。</span><span class="sxs-lookup"><span data-stu-id="3cf6e-118">A trunk configuration as described below groups a set of parameters that are applied to trunks assigned this trunk configuration.</span></span> <span data-ttu-id="3cf6e-119">特定的主幹組態可涵蓋全域 (涵蓋至不具更明確網站或集區組態的所有主幹)，或涵蓋至網站或集區。</span><span class="sxs-lookup"><span data-stu-id="3cf6e-119">A particular trunk configuration can be scoped globally (to all trunks that do not have more specific site or pool configuration), or to a site, or to a pool.</span></span> <span data-ttu-id="3cf6e-120">集區層級組態是用於將明確主幹組態涵蓋至單一主幹。</span><span class="sxs-lookup"><span data-stu-id="3cf6e-120">The pool-level trunk configuration is used to scope a specific trunk configuration to a single trunk.</span></span>

<span id="BKMK_ConfigTrunkMediaBypassSteps"></span>

<div>

## <a name="to-configure-a-trunk-with-media-bypass"></a><span data-ttu-id="3cf6e-121">使用媒體旁路設定主幹</span><span class="sxs-lookup"><span data-stu-id="3cf6e-121">To configure a trunk with media bypass</span></span>

1.  <span data-ttu-id="3cf6e-122">以 RTCUniversalServerAdmins 群組成員的身分，或是 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色的成員身分登入電腦。</span><span class="sxs-lookup"><span data-stu-id="3cf6e-122">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="3cf6e-123">如需詳細資訊，請參閱[在 Lync Server 2013 中委派設定許可權](lync-server-2013-delegate-setup-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="3cf6e-123">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="3cf6e-124">開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="3cf6e-124">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="3cf6e-125">如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱[Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="3cf6e-125">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="3cf6e-126">在左導覽列中，按一下 **[語音路由]**，再按一下 **[主幹組態]**。</span><span class="sxs-lookup"><span data-stu-id="3cf6e-126">In the left navigation bar, click **Voice Routing**, and then click **Trunk Configuration**.</span></span>

4.  <span data-ttu-id="3cf6e-127">在 **[主幹組態]** 頁面上，使用下列其中一個方法設定主幹：</span><span class="sxs-lookup"><span data-stu-id="3cf6e-127">On the **Trunk Configuration** page, use one of the following methods to configure a trunk:</span></span>
    
      - <span data-ttu-id="3cf6e-128">按兩下現有主幹 (例如 **[通用]** 主幹)，顯示 **[編輯主幹組態]** 對話方塊。</span><span class="sxs-lookup"><span data-stu-id="3cf6e-128">Double-click an existing trunk (for example, the **Global** trunk) to display the **Edit Trunk Configuration** dialog box.</span></span>
    
      - <span data-ttu-id="3cf6e-129">按一下 **[新增]**，然後選取新主幹組態：</span><span class="sxs-lookup"><span data-stu-id="3cf6e-129">Click **New**, and then select a scope for the new trunk configuration:</span></span>
        
          - <span data-ttu-id="3cf6e-130">**網站主幹：** 從 [**選取網站**] 選擇此主幹設定的網站，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="3cf6e-130">**Site trunk:** Choose the site for this trunk configuration from **Select a Site**, and then click **OK**.</span></span> <span data-ttu-id="3cf6e-131">請注意，如果已為某個網站建立主幹組態，則該網站不會出現在 **[選取站台]** 中。</span><span class="sxs-lookup"><span data-stu-id="3cf6e-131">Note that if a trunk configuration has already been created for a site, the site does not appear in **Select a Site**.</span></span> <span data-ttu-id="3cf6e-132">此主幹組態將套用至網站中的所有主幹。</span><span class="sxs-lookup"><span data-stu-id="3cf6e-132">This trunk configuration will be applied to all trunks in the site.</span></span>
        
          - <span data-ttu-id="3cf6e-133">**集區主幹：** 選擇此主幹設定適用的主幹名稱。</span><span class="sxs-lookup"><span data-stu-id="3cf6e-133">**Pool trunk:** Choose the name of the trunk that this trunk configuration applies to.</span></span> <span data-ttu-id="3cf6e-134">這個主幹可以是根主幹或在拓撲產生器中定義的任何其他主幹。</span><span class="sxs-lookup"><span data-stu-id="3cf6e-134">This trunk can be the root trunk or any additional trunks defined in Topology Builder.</span></span> <span data-ttu-id="3cf6e-135">從 [**選取服務**] 中，按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="3cf6e-135">From **Select a Service**, click **OK**.</span></span> <span data-ttu-id="3cf6e-136">請注意，如果已經針對特定主幹建立主幹組態，則該主幹就不會顯示在 **[選取服務]** 中。</span><span class="sxs-lookup"><span data-stu-id="3cf6e-136">Note that if a trunk configuration has already been created for a specific trunk, the trunk does not appear in **Select a Service**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="3cf6e-137">一旦選取主幹組態的範圍後，就無法變更。</span><span class="sxs-lookup"><span data-stu-id="3cf6e-137">After you select the scope of the trunk configuration, it cannot be changed.</span></span><BR><span data-ttu-id="3cf6e-138"><STRONG>[名稱]</STRONG> 欄位會預先填入主幹組態所關聯之網站或服務的名稱，此名稱無法變更。</span><span class="sxs-lookup"><span data-stu-id="3cf6e-138">The <STRONG>Name</STRONG> field is prepopulated with the name of the trunk configuration’s associated site or service and cannot be changed.</span></span>

    
    </div>

5.  <span data-ttu-id="3cf6e-139">在**支援的最大早期對話方塊**中指定一個值。</span><span class="sxs-lookup"><span data-stu-id="3cf6e-139">Specify a value in **Maximum early dialogs supported**.</span></span> <span data-ttu-id="3cf6e-140">這是公用交換電話網路 (PSTN) 閘道、IP-PBX 或 ITSP 會話邊界控制器 (SBC) 可以接收到它傳送給轉送伺服器的邀請數目上限。</span><span class="sxs-lookup"><span data-stu-id="3cf6e-140">This is the maximum number of forked responses a public switched telephone network (PSTN) gateway, IP-PBX, or ITSP Session Border Controller (SBC) can receive to an INVITE that it sent to the Mediation Server.</span></span> <span data-ttu-id="3cf6e-141">預設值是 20。</span><span class="sxs-lookup"><span data-stu-id="3cf6e-141">The default value is 20.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="3cf6e-142">變更此值之前，請諮詢服務提供者或設備製造商，以取得系統功能的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="3cf6e-142">Before you change this value, consult your service provider or equipment manufacturer for details about the capabilities of your system.</span></span>

    
    </div>

6.  <span data-ttu-id="3cf6e-143">選取下列其中一個 **[加密支援等級]** 選項：</span><span class="sxs-lookup"><span data-stu-id="3cf6e-143">Select one of the following **Encryption support level** options:</span></span>
    
      - <span data-ttu-id="3cf6e-144">**必要：** 安全即時傳輸通訊協定 (SRTP) 加密必須用來協助保護轉送伺服器和閘道或專用交換機 (PBX) 之間的流量。</span><span class="sxs-lookup"><span data-stu-id="3cf6e-144">**Required:** Secure real-time transport protocol (SRTP) encryption must be used to help protect traffic between the Mediation Server and the gateway or private branch exchange (PBX).</span></span>
    
      - <span data-ttu-id="3cf6e-145">**選用：** 如果服務提供者或設備製造商支援，就會使用 SRTP 加密。</span><span class="sxs-lookup"><span data-stu-id="3cf6e-145">**Optional:** SRTP encryption will be used if the service provider or equipment manufacturer supports it.</span></span>
    
      - <span data-ttu-id="3cf6e-146">**不支援：** SRTP 不支援服務提供者或設備製造商的加密，因此不會使用此加密。</span><span class="sxs-lookup"><span data-stu-id="3cf6e-146">**Not Supported:** SRTP encryption is not supported by the service provider or equipment manufacturer and therefore will not be used.</span></span>

7.  <span data-ttu-id="3cf6e-147">如果您想讓媒體略過轉送伺服器，以供主幹對等處理，請選取 [**啟用媒體旁路**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="3cf6e-147">Select the **Enable media bypass** check box if you want media to bypass the Mediation Server for processing by the trunk peer.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="3cf6e-148">若要讓媒體旁路順利運作，PSTN 閘道、IP-PBX 或 ITSP 會話邊界控制器必須支援某些功能。</span><span class="sxs-lookup"><span data-stu-id="3cf6e-148">For media bypass to work successfully, the PSTN gateway, IP-PBX, or ITSP Session Border Controller must support certain capabilities.</span></span> <span data-ttu-id="3cf6e-149">如需詳細資訊，請參閱規劃檔中的<A href="lync-server-2013-planning-for-media-bypass.md">規劃 Lync Server 2013 中的媒體旁路</A>。</span><span class="sxs-lookup"><span data-stu-id="3cf6e-149">For details, see <A href="lync-server-2013-planning-for-media-bypass.md">Planning for media bypass in Lync Server 2013</A> in the Planning documentation.</span></span>

    
    </div>

8.  <span data-ttu-id="3cf6e-150">如果有已知的媒體終端 (點，請選取 [**集中式媒體處理**] 核取方塊（例如，媒體端接系的 IP 位址與「終止」) 相同）。</span><span class="sxs-lookup"><span data-stu-id="3cf6e-150">Select the **Centralized media processing** check box if there is a well-known media termination point (for example, a PSTN gateway where the media termination has the same IP as the signaling termination).</span></span> <span data-ttu-id="3cf6e-151">如果主幹沒有已知的媒體終端點，請清除此核取方塊。</span><span class="sxs-lookup"><span data-stu-id="3cf6e-151">Clear this check box if the trunk does not have a well-known media termination point.</span></span>

9.  <span data-ttu-id="3cf6e-152">如果主幹對等支援從轉送伺服器接收 SIP 參考要求，請選取 [**啟用傳送參照至閘道**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="3cf6e-152">If the trunk peer supports receiving SIP REFER requests from the Mediation Server, select the **Enable sending refer to the gateway** check box.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="3cf6e-153">如果在選取 [<STRONG>啟用媒體旁路</STRONG>] 選項時停用此選項，則需要其他設定。</span><span class="sxs-lookup"><span data-stu-id="3cf6e-153">If you disable this option while the <STRONG>Enable media bypass</STRONG> option is selected, additional settings are required.</span></span> <span data-ttu-id="3cf6e-154">若主幹對等不支援從轉送伺服器接收 SIP 參考要求和媒體旁路，您也必須執行<STRONG>Set-CsTrunkConfiguration</STRONG> Cmdlet 以停用使用中和保留通話的 RTCP，以便支援媒體旁路的適當狀況。</span><span class="sxs-lookup"><span data-stu-id="3cf6e-154">If the trunk peer does not support receiving SIP REFER requests from the Mediation Server and media bypass is enabled, you must also run the <STRONG>Set-CsTrunkConfiguration</STRONG> cmdlet to disable RTCP for active and held calls in order to support proper conditions for media bypass.</span></span> <span data-ttu-id="3cf6e-155">如需詳細資訊，請參閱<A href="lync-server-2013-lync-server-management-shell.md">Lync Server 2013 管理命令</A>介面檔。</span><span class="sxs-lookup"><span data-stu-id="3cf6e-155">For details, see the <A href="lync-server-2013-lync-server-management-shell.md">Lync Server 2013 Management Shell</A> documentation.</span></span><BR><span data-ttu-id="3cf6e-156">或者，您也可以選取 [<STRONG>使用協力廠商通話控制啟用參考</STRONG>]，如果您想要將轉接來電轉接到媒體略過，而閘道不支援 SIP 參考要求。</span><span class="sxs-lookup"><span data-stu-id="3cf6e-156">Alternatively, you can select <STRONG>Enable refer using third-party-call control</STRONG> if you want transferred calls to be media bypassed, and the gateway does not support SIP REFER requests.</span></span>

    
    </div>

10. <span data-ttu-id="3cf6e-p113">(選用) 若要啟用主幹間的路由，請關聯至此主幹組態並設定其 PSTN 使用方式記錄。與此主幹組態相關聯的 PSTN 使用方式，將會套用至整個主幹中並非由 Lync 端點產生的所有來電。若要管理與主幹組態關聯的 PSTN 使用方式記錄，請使用下列其中一種方法：</span><span class="sxs-lookup"><span data-stu-id="3cf6e-p113">(Optional) To enable inter-trunk routing, associate and configure PSTN usage records to this trunk configuration. The PSTN usages associated to this trunk configuration will be applied for all incoming calls through the trunk that is not originating from a Lync endpoint. To manage PSTN usage records associated to a trunk configuration, use one of the following methods:</span></span>
    
      - <span data-ttu-id="3cf6e-160">若要從 Enterprise Voice 部署中所有可用的 PSTN 使用方式記錄清單中選取一或多筆記錄，請按一下 [**選取**]。</span><span class="sxs-lookup"><span data-stu-id="3cf6e-160">To select one or more records from a list of all PSTN usage records available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="3cf6e-161">反白顯示您要與此主幹組態建立關聯的記錄，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="3cf6e-161">Highlight the records you want to associate with this trunk configuration and then click **OK**.</span></span>
    
      - <span data-ttu-id="3cf6e-162">若要從此主幹組態移除 PSTN 使用方式記錄，請選取該記錄然後按一下 **[移除]**。</span><span class="sxs-lookup"><span data-stu-id="3cf6e-162">To remove a PSTN usage record from this trunk configuration, select the record and click **Remove**.</span></span>
    
      - <span data-ttu-id="3cf6e-163">若要定義新的 PSTN 使用方式記錄，並建立與此主幹組態的關聯，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="3cf6e-163">To define a new PSTN usage record and associate it with this trunk configuration, do the following:</span></span>
        
        1.  <span data-ttu-id="3cf6e-164">按一下 **[新增]**。</span><span class="sxs-lookup"><span data-stu-id="3cf6e-164">Click **New**.</span></span>
        
        2.  <span data-ttu-id="3cf6e-165">在 **[名稱]** 欄位中，指定該記錄的唯一描述性名稱。</span><span class="sxs-lookup"><span data-stu-id="3cf6e-165">In the **Name** field, specify a descriptive name for the record that is unique.</span></span>
            
            <div>
            

            > [!NOTE]  
            > <span data-ttu-id="3cf6e-p115">PSTN 使用方式記錄名稱必須是 Enterprise Voice 部署內的唯一名稱。儲存記錄之後，就無法編輯 <STRONG>[名稱]</STRONG> 欄位。</span><span class="sxs-lookup"><span data-stu-id="3cf6e-p115">The PSTN usage record name must be unique within the Enterprise Voice deployment. After the record is saved, the <STRONG>Name</STRONG> field cannot be edited.</span></span>

            
            </div>
        
        3.  <span data-ttu-id="3cf6e-168">使用下列其中一種方法，關聯至此 PSTN 使用方式記錄並設定其路由：</span><span class="sxs-lookup"><span data-stu-id="3cf6e-168">Use one of the following methods to associate and configure routes for this PSTN usage record:</span></span>
            
              - <span data-ttu-id="3cf6e-169">若要從 Enterprise Voice 部署中所有可用路由的清單中選取一個或多個路由，請按一下 [**選取**]。</span><span class="sxs-lookup"><span data-stu-id="3cf6e-169">To select one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="3cf6e-170">反白顯示您要與此 PSTN 使用方式記錄相關聯的路由，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="3cf6e-170">Highlight the routes you want to associate with this PSTN usage record, and click **OK**.</span></span>
            
              - <span data-ttu-id="3cf6e-171">若要從 PSTN 使用方式記錄移除路由，請選取該路由，然後按一下 **[移除]**。</span><span class="sxs-lookup"><span data-stu-id="3cf6e-171">To remove a route from the PSTN usage record, select the route, and click **Remove**.</span></span>
            
              - <span data-ttu-id="3cf6e-172">若要定義新路由，並將其關聯至此 PSTN 使用記錄，請按一下 **[新增]**。</span><span class="sxs-lookup"><span data-stu-id="3cf6e-172">To define a new route and associate it to this PSTN usage record, click **New**.</span></span> <span data-ttu-id="3cf6e-173">如需詳細資訊，請參閱[Create a voice route In Lync Server 2013](lync-server-2013-create-a-voice-route.md)。</span><span class="sxs-lookup"><span data-stu-id="3cf6e-173">For details, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>
            
              - <span data-ttu-id="3cf6e-174">若要編輯與此 PSTN 使用方式記錄相關聯的路由，請選取該路由，然後按一下 **[顯示詳細資料]**。</span><span class="sxs-lookup"><span data-stu-id="3cf6e-174">To edit a route that is associated with this PSTN usage record, select the route, and click **Show details**.</span></span> <span data-ttu-id="3cf6e-175">如需詳細資訊，請參閱[Modify a voice route In Lync Server 2013](lync-server-2013-modify-a-voice-route.md)。</span><span class="sxs-lookup"><span data-stu-id="3cf6e-175">For details, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span></span>
        
        4.  <span data-ttu-id="3cf6e-176">按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="3cf6e-176">Click **OK**.</span></span>
    
      - <span data-ttu-id="3cf6e-177">若要編輯已經與此主幹組態建立關聯的 PSTN 使用方式記錄，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="3cf6e-177">To edit a PSTN usage record that is already associated with this trunk configuration, do the following:</span></span>
        
        1.  <span data-ttu-id="3cf6e-178">選取您要編輯的 PSTN 使用方式記錄，然後按一下 **[顯示詳細資料]**。</span><span class="sxs-lookup"><span data-stu-id="3cf6e-178">Select the PSTN usage record you want to edit, and click **Show details**.</span></span>
        
        2.  <span data-ttu-id="3cf6e-179">使用下列其中一種方法，關聯至此 PSTN 使用方式記錄並設定其路由：</span><span class="sxs-lookup"><span data-stu-id="3cf6e-179">Use one of the following methods to associate and configure routes for this PSTN usage record:</span></span>
            
              - <span data-ttu-id="3cf6e-180">若要從 Enterprise Voice 部署中所有可用路由的清單中選取一個或多個路由，請按一下 [**選取**]。</span><span class="sxs-lookup"><span data-stu-id="3cf6e-180">To select one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="3cf6e-181">反白顯示您要與此 PSTN 使用方式記錄相關聯的路由，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="3cf6e-181">Highlight the routes you want to associate with this PSTN usage record, and click **OK**.</span></span>
            
              - <span data-ttu-id="3cf6e-182">若要從 PSTN 使用方式記錄移除路由，請選取該路由，然後按一下 **[移除]**。</span><span class="sxs-lookup"><span data-stu-id="3cf6e-182">To remove a route from the PSTN usage record, select the route, and click **Remove**.</span></span>
            
              - <span data-ttu-id="3cf6e-183">若要定義新路由，並將其關聯至此 PSTN 使用記錄，請按一下 **[新增]**。</span><span class="sxs-lookup"><span data-stu-id="3cf6e-183">To define a new route and associate it to this PSTN usage record, click **New**.</span></span> <span data-ttu-id="3cf6e-184">如需詳細資訊，請參閱[Create a voice route In Lync Server 2013](lync-server-2013-create-a-voice-route.md)。</span><span class="sxs-lookup"><span data-stu-id="3cf6e-184">For details, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>
            
              - <span data-ttu-id="3cf6e-185">若要編輯與此 PSTN 使用方式記錄相關聯的路由，請選取該路由，然後按一下 **[顯示詳細資料]**。</span><span class="sxs-lookup"><span data-stu-id="3cf6e-185">To edit a route that is associated with this PSTN usage record, select the route, and click **Show details**.</span></span> <span data-ttu-id="3cf6e-186">如需詳細資訊，請參閱[Modify a voice route In Lync Server 2013](lync-server-2013-modify-a-voice-route.md)。</span><span class="sxs-lookup"><span data-stu-id="3cf6e-186">For details, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span></span>
        
        3.  <span data-ttu-id="3cf6e-187">按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="3cf6e-187">Click **OK**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="3cf6e-188">將 PSTN 使用方式記錄與所設定之主幹相關聯的轉送伺服器對等相關聯是很重要的。</span><span class="sxs-lookup"><span data-stu-id="3cf6e-188">It important to associate PSTN usage records according to the Mediation Server peer that is associated to the trunk being configured.</span></span> <span data-ttu-id="3cf6e-189">若轉送伺服器對等是 PSTN 閘道或會話邊界控制器 (SBC) ，強烈建議您不要將主幹設定相關聯至 PSTN 使用方式記錄，該記錄會路由傳送至 PSTN 目的地或透過 Lync Server 連接的任何其他下游系統。</span><span class="sxs-lookup"><span data-stu-id="3cf6e-189">If the Mediation Server peer is a PSTN gateway or a Session Border Controller (SBC), it is strongly recommended that the trunk configuration is not associated to a PSTN usage record that routes to a PSTN destination or any other downstream systems connected via Lync Server.</span></span>

    
    </div>

11. <span data-ttu-id="3cf6e-p123">請排列 PSTN 使用方式記錄以達到最佳效能。若要變更記錄在清單中的位置，請選取 PSTN 使用記錄，然後按一下向上或向下箭號。</span><span class="sxs-lookup"><span data-stu-id="3cf6e-p123">Arrange the PSTN usage records for optimum performance. To change a record’s position in the list, select the PSTN usage record, and click the up or down arrows.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="3cf6e-192">PSTN 使用方式記錄列示在主幹組態中的順序非常重要。</span><span class="sxs-lookup"><span data-stu-id="3cf6e-192">The order in which PSTN usage records are listed in the trunk configuration is significant.</span></span> <span data-ttu-id="3cf6e-193">Lync Server 從上到上，從上到上的遍歷清單。</span><span class="sxs-lookup"><span data-stu-id="3cf6e-193">Lync Server traverses the list from top to down.</span></span>

    
    </div>

12. <span data-ttu-id="3cf6e-194">應該選取 [**啟用 RTP**鎖定]，以啟用網路位址轉譯之後用戶端的旁路媒體（ (NAT) 或防火牆，以及支援閉鎖的 SBC）。</span><span class="sxs-lookup"><span data-stu-id="3cf6e-194">**Enable RTP Latching** should be selected to enable bypass media for clients behind a network address translation (NAT) or firewall and an SBC that supports latching.</span></span>

13. <span data-ttu-id="3cf6e-195">應該選取 [**啟用轉接來電記錄**]，以啟用將通話記錄資訊傳送至轉送伺服器的閘道對等功能。</span><span class="sxs-lookup"><span data-stu-id="3cf6e-195">**Enable forward call history** should be selected to enable sending of call history information to the gateway peer of the Mediation Server.</span></span>

14. <span data-ttu-id="3cf6e-196">您應該選取 [**啟用轉寄 P-Asserted-Identity 資料**]，以啟用 P-ASSERTED-IDENTITY (PAI) 呼叫發信方資訊，以便在轉送伺服器端與閘道端 (之間轉送，反之亦然。</span><span class="sxs-lookup"><span data-stu-id="3cf6e-196">**Enable forward P-Asserted-Identity data** should be selected to enable the P-Asserted-Identity (PAI) call originator information to be forwarded between the Mediation Server side and gateway side (and vice versa), when present.</span></span>

15. <span data-ttu-id="3cf6e-197">您應選取 **[啟用輸出路由容錯移轉計時器]** 才能啟用快速容錯移轉。</span><span class="sxs-lookup"><span data-stu-id="3cf6e-197">**Enable outbound routing failover timer** should be selected to enable fast failover.</span></span> <span data-ttu-id="3cf6e-198">由於與此主幹相關聯的閘道正在處理撥出電話，所以可以在 10 秒內發出通知。</span><span class="sxs-lookup"><span data-stu-id="3cf6e-198">The gateway associated with this trunk can give notification within 10 seconds that it is processing an outbound call.</span></span> <span data-ttu-id="3cf6e-199">若轉送伺服器未收到此通知，則會進行重新路由至另一個主幹。</span><span class="sxs-lookup"><span data-stu-id="3cf6e-199">Rerouting to another trunk will occur if this notification is not received by the Mediation Server.</span></span> <span data-ttu-id="3cf6e-200">在延遲可能遞延回應時間的網路上或是閘道回應時間在 10 秒以上者，應停用快速容錯移轉。</span><span class="sxs-lookup"><span data-stu-id="3cf6e-200">On networks where latency may delay the response time or the gateway takes longer than 10 seconds to respond, the fast failover should be disabled.</span></span>

16. <span data-ttu-id="3cf6e-201">(選用) 建立與主幹的關聯並設定其 **[撥號轉譯規則]**。</span><span class="sxs-lookup"><span data-stu-id="3cf6e-201">(Optional) Associate and configure **calling number translation rules** for the trunk.</span></span> <span data-ttu-id="3cf6e-202">這些轉譯規則適用於撥出電話的撥打號碼</span><span class="sxs-lookup"><span data-stu-id="3cf6e-202">These translation rules apply to the calling number for outbound calls</span></span>
    
      - <span data-ttu-id="3cf6e-203">若要從 Enterprise Voice 部署中所有可用轉譯規則的清單中選擇一個或多個規則，請按一下 [**選取**]。</span><span class="sxs-lookup"><span data-stu-id="3cf6e-203">To choose one or more rules from a list of all translation rules that are available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="3cf6e-204">在 **[選取轉譯規則]** 中，按一下您要建立關聯的主幹，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="3cf6e-204">In **Select Translation Rules**, click the rules that you want to associate with the trunk, and then click **OK**.</span></span>
    
      - <span data-ttu-id="3cf6e-205">若要定義新的轉譯規則並建立其與主幹的關聯，請按一下 **[新增]**。</span><span class="sxs-lookup"><span data-stu-id="3cf6e-205">To define a new translation rule and associate it with the trunk, click **New**.</span></span> <span data-ttu-id="3cf6e-206">如需定義新規則的詳細資訊，請參閱部署檔中的在[Lync Server 2013 中定義轉譯規則](lync-server-2013-defining-translation-rules.md)。</span><span class="sxs-lookup"><span data-stu-id="3cf6e-206">For details about defining a new rule, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="3cf6e-207">若要編輯已與主幹建立關聯的轉譯規則，按一下規則名稱，然後按一下 **[顯示詳細資料]**。</span><span class="sxs-lookup"><span data-stu-id="3cf6e-207">To edit a translation rule that is already associated with the trunk, click the rule name, and then click **Show details**.</span></span> <span data-ttu-id="3cf6e-208">如需詳細資訊，請參閱部署檔中的在[Lync Server 2013 中定義轉譯規則](lync-server-2013-defining-translation-rules.md)。</span><span class="sxs-lookup"><span data-stu-id="3cf6e-208">For details, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="3cf6e-209">若要複製現有轉譯規則，以用來作為定義新規則時的起點，請按一下規則名稱，再按一下 **[複製]**，然後按一下 **[貼上]**。</span><span class="sxs-lookup"><span data-stu-id="3cf6e-209">To copy an existing translation rule to use as a starting point for defining a new rule, click the rule name and click **Copy**, and then click **Paste**.</span></span> <span data-ttu-id="3cf6e-210">如需詳細資訊，請參閱[在 Lync Server 2013 中定義轉譯規則](lync-server-2013-defining-translation-rules.md)。</span><span class="sxs-lookup"><span data-stu-id="3cf6e-210">For details, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md).</span></span>
    
      - <span data-ttu-id="3cf6e-211">若要從主幹移除轉譯規則，請反白顯示該規則名稱並按一下 **[移除]**。</span><span class="sxs-lookup"><span data-stu-id="3cf6e-211">To remove a translation rule from the trunk, highlight the rule name and click **Remove**.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="3cf6e-212">如果您已在關聯的主幹對等上設定轉譯規則，請勿再將轉譯規則與主幹建立關聯，因為這兩個規則可能會產生衝突。</span><span class="sxs-lookup"><span data-stu-id="3cf6e-212">Do not associate translation rules with a trunk if you have configured translation rules on the associated trunk peer, because the two rules might conflict.</span></span>

    
    </div>

17. <span data-ttu-id="3cf6e-p131">(選用) 建立與主幹的關聯並設定其 **[撥號轉譯規則]**。這些轉譯規則適用於撥出電話的撥打號碼。</span><span class="sxs-lookup"><span data-stu-id="3cf6e-p131">(Optional) Associate and configure **called number translation rules** for the trunk. The translation rules apply to the called number in an outbound call.</span></span>
    
      - <span data-ttu-id="3cf6e-215">若要從 Enterprise Voice 部署中所有可用轉譯規則的清單中選擇一個或多個規則，請按一下 [**選取**]。</span><span class="sxs-lookup"><span data-stu-id="3cf6e-215">To choose one or more rules from a list of all translation rules that are available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="3cf6e-216">在 **[選取轉譯規則]** 中，按一下您要建立關聯的主幹，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="3cf6e-216">In **Select Translation Rules**, click the rules that you want to associate with the trunk, and then click **OK**.</span></span>
    
      - <span data-ttu-id="3cf6e-217">若要定義新的轉譯規則並建立其與主幹的關聯，請按一下 **[新增]**。</span><span class="sxs-lookup"><span data-stu-id="3cf6e-217">To define a new translation rule and associate it with the trunk, click **New**.</span></span> <span data-ttu-id="3cf6e-218">如需定義新規則的詳細資訊，請參閱部署檔中的在[Lync Server 2013 中定義轉譯規則](lync-server-2013-defining-translation-rules.md)。</span><span class="sxs-lookup"><span data-stu-id="3cf6e-218">For details about defining a new rule, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="3cf6e-219">若要編輯已與主幹建立關聯的轉譯規則，按一下規則名稱，然後按一下 **[顯示詳細資料]**。</span><span class="sxs-lookup"><span data-stu-id="3cf6e-219">To edit a translation rule that is already associated with the trunk, click the rule name, and then click **Show details**.</span></span> <span data-ttu-id="3cf6e-220">如需詳細資訊，請參閱部署檔中的在[Lync Server 2013 中定義轉譯規則](lync-server-2013-defining-translation-rules.md)。</span><span class="sxs-lookup"><span data-stu-id="3cf6e-220">For details, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="3cf6e-221">若要複製現有轉譯規則，以用來作為定義新規則時的起點，請按一下規則名稱，再按一下 **[複製]**，然後按一下 **[貼上]**。</span><span class="sxs-lookup"><span data-stu-id="3cf6e-221">To copy an existing translation rule to use as a starting point for defining a new rule, click the rule name and click **Copy**, and then click **Paste**.</span></span> <span data-ttu-id="3cf6e-222">如需詳細資訊，請參閱[在 Lync Server 2013 中定義轉譯規則](lync-server-2013-defining-translation-rules.md)。</span><span class="sxs-lookup"><span data-stu-id="3cf6e-222">For details, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md).</span></span>
    
      - <span data-ttu-id="3cf6e-223">若要從主幹移除轉譯規則，請反白顯示該規則名稱並按一下 **[移除]**。</span><span class="sxs-lookup"><span data-stu-id="3cf6e-223">To remove a translation rule from the trunk, highlight the rule name and click **Remove**.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="3cf6e-224">如果您已在相關聯的主幹對等上設定轉譯規則，則請勿將轉譯規則與主幹建立關聯，因為兩種規則可能會衝突。</span><span class="sxs-lookup"><span data-stu-id="3cf6e-224">Do not associate translation rules with a trunk if you have configured translation rules on the associated trunk peer, because the two rules might conflict.</span></span>

    
    </div>

18. <span data-ttu-id="3cf6e-225">請確定主幹的轉譯規則依正確的順序排列。</span><span class="sxs-lookup"><span data-stu-id="3cf6e-225">Make sure that the trunk’s translation rules are arranged in the correct order.</span></span> <span data-ttu-id="3cf6e-226">若要變更規則在清單中的位置，請反白顯示規則名稱，然後按一下向上或向下箭號。</span><span class="sxs-lookup"><span data-stu-id="3cf6e-226">To change a rule’s position in the list, highlight the rule name and then click the up or down arrow.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="3cf6e-227">Lync Server 2013 會從左上部開始轉譯轉譯規則清單，並使用符合撥號號碼的第一個規則。</span><span class="sxs-lookup"><span data-stu-id="3cf6e-227">Lync Server 2013 traverses the translation rule list from the top down and uses the first rule that matches the dialed number.</span></span> <span data-ttu-id="3cf6e-228">如果您設定的主幹會使撥號號碼符合不只一個轉譯規則，請確定限制較多的規則排在限制較少的規則上方。</span><span class="sxs-lookup"><span data-stu-id="3cf6e-228">If you configure a trunk so that a dialed number can match more than one translation rule, be sure that the more restrictive rules are sorted above the less restrictive rules.</span></span> <span data-ttu-id="3cf6e-229">例如，如果您包含的轉譯規則中有一個規則符合所有 11 位數號碼，另有一個轉譯規則僅符合開頭為 +1425 的 11 位數號碼，則請確定符合所有 11 位數號碼的規則排在另一個限制較多規則的<EM>下方</EM>。</span><span class="sxs-lookup"><span data-stu-id="3cf6e-229">For example, if you have included a translation rule that matches any 11-digit number and a translation rule that matches only 11-digit numbers that start with +1425, be sure that the rule that matches any 11-digit number is sorted <EM>below</EM> the more restrictive rule.</span></span>

    
    </div>

19. <span data-ttu-id="3cf6e-230">完成主幹的設定時，請按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="3cf6e-230">When you are finished configuring the trunk, click **OK**.</span></span>

20. <span data-ttu-id="3cf6e-231">在 **[主幹組態]** 頁面上，按一下 **[認可]**，再按一下 **[全部認可]**。</span><span class="sxs-lookup"><span data-stu-id="3cf6e-231">On the **Trunk Configuration** page, click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="3cf6e-232">只要建立或修改主幹組態後，都應執行 <STRONG>[全部認可]</STRONG> 命令以發行組態變更。</span><span class="sxs-lookup"><span data-stu-id="3cf6e-232">Whenever you create or modify a trunk configuration, you must run the <STRONG>Commit all</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="3cf6e-233">如需詳細資訊，請參閱 Operations 檔中的在<A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Lync Server 2013 中發佈擱置的變更至語音路由</A>設定。</span><span class="sxs-lookup"><span data-stu-id="3cf6e-233">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

<span data-ttu-id="3cf6e-234">設定主幹之後，請選擇通用媒體旁路選項，繼續設定媒體旁路，如部署檔中的 [ [Lync Server 2013 中的全域媒體旁路選項](lync-server-2013-global-media-bypass-options.md)所述。</span><span class="sxs-lookup"><span data-stu-id="3cf6e-234">After you have configured the trunk, continue configuring media bypass by choosing between global media bypass options, as described in [Global media bypass options in Lync Server 2013](lync-server-2013-global-media-bypass-options.md) in the Deployment documentation.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="3cf6e-235">另請參閱</span><span class="sxs-lookup"><span data-stu-id="3cf6e-235">See Also</span></span>


[<span data-ttu-id="3cf6e-236">在 Lync Server 2013 中設定無媒體旁路的主幹</span><span class="sxs-lookup"><span data-stu-id="3cf6e-236">Configure a trunk without media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-without-media-bypass.md)  


[<span data-ttu-id="3cf6e-237">在 Lync Server 2013 中設定媒體旁路</span><span class="sxs-lookup"><span data-stu-id="3cf6e-237">Configure media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-media-bypass.md)  
[<span data-ttu-id="3cf6e-238">Lync Server 2013 中的全域媒體旁路選項</span><span class="sxs-lookup"><span data-stu-id="3cf6e-238">Global media bypass options in Lync Server 2013</span></span>](lync-server-2013-global-media-bypass-options.md)  


[<span data-ttu-id="3cf6e-239">在 Lync Server 2013 中定義轉譯規則</span><span class="sxs-lookup"><span data-stu-id="3cf6e-239">Defining translation rules in Lync Server 2013</span></span>](lync-server-2013-defining-translation-rules.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

