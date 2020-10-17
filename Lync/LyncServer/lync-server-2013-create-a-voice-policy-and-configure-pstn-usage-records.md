---
title: Lync Server 2013：建立語音原則和設定 PSTN 使用方式記錄
description: Lync Server 2013：建立語音原則和設定 PSTN 使用方式記錄。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a voice policy and configure PSTN usage records
ms:assetid: e6ff27e0-e2d1-4445-840f-08f738200c20
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399027(v=OCS.15)
ms:contentKeyID: 48185693
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 55833572b5ca79019d5037406ae530ef5591b6fe
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562449"
---
# <a name="create-a-voice-policy-and-configure-pstn-usage-records-in-lync-server-2013"></a><span data-ttu-id="98c39-103">在 Lync Server 2013 中建立語音原則和設定 PSTN 使用方式記錄</span><span class="sxs-lookup"><span data-stu-id="98c39-103">Create a voice policy and configure PSTN usage records in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="98c39-104">_**主題上次修改日期：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="98c39-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="98c39-105">如果您想要建立新的語音原則，請遵循下列步驟。</span><span class="sxs-lookup"><span data-stu-id="98c39-105">Follow these steps if you want to create a new voice policy.</span></span> <span data-ttu-id="98c39-106">如果您想要編輯語音原則，請參閱 [在 Lync Server 2013 中修改語音原則和設定 PSTN 使用方式記錄](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md) ，以取得此過程。</span><span class="sxs-lookup"><span data-stu-id="98c39-106">If you want to edit a voice policy, see [Modify a voice policy and configure PSTN usage records in Lync Server 2013](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md) for the procedure.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="98c39-107">每個語音原則都必須至少有一個相關聯的公用交換電話網路 (PSTN) 使用方式記錄。</span><span class="sxs-lookup"><span data-stu-id="98c39-107">Each voice policy must have at least one associated public switched telephone network (PSTN) usage record.</span></span> <span data-ttu-id="98c39-108">若要查看您 Enterprise Voice 部署中所有可用的 PSTN 使用方式記錄清單，並查看其屬性，請參閱 <A href="lync-server-2013-view-pstn-usage-records.md">在 Lync Server 2013 中查看 PSTN 使用方式記錄</A>。</span><span class="sxs-lookup"><span data-stu-id="98c39-108">To see a listing of all PSTN usage records available in your Enterprise Voice deployment and view their properties, see <A href="lync-server-2013-view-pstn-usage-records.md">View PSTN usage records in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-create-a-voice-policy"></a><span data-ttu-id="98c39-109">若要建立語音原則</span><span class="sxs-lookup"><span data-stu-id="98c39-109">To create a voice policy</span></span>

1.  <span data-ttu-id="98c39-110">以 RTCUniversalServerAdmins 群組成員的身分，或是 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色的成員身分登入電腦。</span><span class="sxs-lookup"><span data-stu-id="98c39-110">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="98c39-111">如需詳細資訊，請參閱 [在 Lync Server 2013 中委派設定許可權](lync-server-2013-delegate-setup-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="98c39-111">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="98c39-112">開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="98c39-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="98c39-113">如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="98c39-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="98c39-114">在左導覽列中，依序按一下 [ **語音路由** ] 及 [ **語音原則**]。</span><span class="sxs-lookup"><span data-stu-id="98c39-114">In the left navigation bar, click **Voice Routing** and then click **Voice Policy**.</span></span>

4.  <span data-ttu-id="98c39-115">在 [ **語音原則** ] 頁面上，按一下 [ **新增** ]，然後選取新原則的範圍：</span><span class="sxs-lookup"><span data-stu-id="98c39-115">On the **Voice Policy** page, click **New** and then select a scope for the new policy:</span></span>
    
      - <span data-ttu-id="98c39-116">**網站原則** 適用于整個網站，但任何指派給使用者原則的使用者或群組除外。</span><span class="sxs-lookup"><span data-stu-id="98c39-116">**Site policy** applies to an entire site, except any users or groups that are assigned to a user policy.</span></span> <span data-ttu-id="98c39-117">如果您為 [原則] 範圍選取 [網站]，請從 [ **選取網站** ] 對話方塊中選擇網站。</span><span class="sxs-lookup"><span data-stu-id="98c39-117">If you select Site for a policy scope, choose the site from the **Select a Site** dialog box.</span></span> <span data-ttu-id="98c39-118">如果已為網站建立語音原則，則網站不會出現在 [ **選取網站** ] 對話方塊中。</span><span class="sxs-lookup"><span data-stu-id="98c39-118">If a voice policy has already been created for a site, the site does not appear in the **Select a Site** dialog box.</span></span>
    
      - <span data-ttu-id="98c39-119">**使用者原則** 可以套用至指定的使用者或群組。</span><span class="sxs-lookup"><span data-stu-id="98c39-119">**User policy** can be applied to specified users or groups.</span></span>

5.  <span data-ttu-id="98c39-120">若語音原則範圍是 [使用者]，請在 [ **名稱** ] 欄位中輸入原則的描述性名稱。</span><span class="sxs-lookup"><span data-stu-id="98c39-120">If the voice policy scope is User, enter a descriptive name for the policy in the **Name** field.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="98c39-121">若語音原則範圍是網站，<STRONG>新語音原則</STRONG>中的 [<STRONG>名稱</STRONG>] 欄位會預先填入網站名稱，而且無法變更。</span><span class="sxs-lookup"><span data-stu-id="98c39-121">If the voice policy scope is Site, the <STRONG>Name</STRONG> field in <STRONG>New Voice Policy</STRONG> is prepopulated with the site name and cannot be changed.</span></span>

    
    </div>

6.  <span data-ttu-id="98c39-122"> (選用) 請輸入語音原則的其他描述性資訊。</span><span class="sxs-lookup"><span data-stu-id="98c39-122">(Optional) Enter additional descriptive information for the voice policy.</span></span>

7.  <span data-ttu-id="98c39-123">選取或清除下列核取方塊，以啟用或停用此語音原則的每個 **通話功能** ：</span><span class="sxs-lookup"><span data-stu-id="98c39-123">Select or clear the following check boxes to enable or disable each of the **Calling features** for this voice policy:</span></span>
    
      - <span data-ttu-id="98c39-124">**[語音信箱逸出]** 可在設定為同時響鈴，且手機在關機、電池電力耗盡或在收訊範圍之外時，防止通話立即路由傳送至使用者的行動電話語音信箱系統。</span><span class="sxs-lookup"><span data-stu-id="98c39-124">**Voice mail escape** prevents calls from being immediately routed to the user’s mobile phone voice mail system when simultaneous ringing is configured and the phone is turned off, out of battery, or out of range.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="98c39-125">此功能僅可透過 Lync Server 管理命令介面進行設定</span><span class="sxs-lookup"><span data-stu-id="98c39-125">This feature is only configurable through the Lync Server Management Shell</span></span>

        
        </div>
    
      - <span data-ttu-id="98c39-126">**[來電轉接]** 可讓使用者將來電轉接到其他電話和用戶端裝置。</span><span class="sxs-lookup"><span data-stu-id="98c39-126">**Call forwarding** enables users to forward calls to other phones and client devices.</span></span> <span data-ttu-id="98c39-127">Lync Server 2013 為來電轉接提供更為廣泛的設定選項。</span><span class="sxs-lookup"><span data-stu-id="98c39-127">Lync Server 2013 provides a significantly wider range of configuration options for call forwarding.</span></span> <span data-ttu-id="98c39-128">例如，如果組織不想讓來電向外轉接到 PSTN，系統管理員可套用特殊語音原則以部署此限制。</span><span class="sxs-lookup"><span data-stu-id="98c39-128">For example, if an organization does not want to allow incoming calls to be forwarded externally to the PSTN, an administrator can apply a special voice policy to deploy this restriction.</span></span> <span data-ttu-id="98c39-129">預設為啟用。</span><span class="sxs-lookup"><span data-stu-id="98c39-129">Enabled by default.</span></span>
    
      - <span data-ttu-id="98c39-130">**[委派]** 可讓使用者指定其他使用者，來代表他們撥號和接聽電話。</span><span class="sxs-lookup"><span data-stu-id="98c39-130">**Delegation** enables users to specify other users to send and receive calls on their behalf.</span></span> <span data-ttu-id="98c39-131">在 Lync Server 2013 中，代理人可以設定同時震鈴，讓來電者能夠撥打所有代理人同時震鈴的目標。</span><span class="sxs-lookup"><span data-stu-id="98c39-131">In Lync Server 2013, a delegate can configure simultaneous ringing that enables incoming calls to his or her manager to ring all of the delegate’s simultaneous ringing targets.</span></span> <span data-ttu-id="98c39-132">這樣可在回應撥至主管的通話時給予代理人更大的彈性。</span><span class="sxs-lookup"><span data-stu-id="98c39-132">This provides the delegate with greater flexibility in responding to calls directed to the manager.</span></span> <span data-ttu-id="98c39-133">預設為啟用。</span><span class="sxs-lookup"><span data-stu-id="98c39-133">Enabled by default.</span></span>
    
      - <span data-ttu-id="98c39-134">**[通話轉接]** 可讓使用者將通話轉接給其他使用者。</span><span class="sxs-lookup"><span data-stu-id="98c39-134">**Call transfer** enables users to transfer calls to other users.</span></span> <span data-ttu-id="98c39-135">預設為啟用。</span><span class="sxs-lookup"><span data-stu-id="98c39-135">Enabled by default.</span></span>
    
      - <span data-ttu-id="98c39-136">**通話駐留** 可讓使用者駐留通話，然後從不同的電話或用戶端挑選來電。</span><span class="sxs-lookup"><span data-stu-id="98c39-136">**Call park** enables users to park calls on hold and then pick up the call from a different phone or client.</span></span> <span data-ttu-id="98c39-137">預設為停用。</span><span class="sxs-lookup"><span data-stu-id="98c39-137">Disabled by default.</span></span>
    
      - <span data-ttu-id="98c39-138">**[同時響鈴]** 可讓來電在更多電話 (例如，行動電話) 或其他端點裝置上發出鈴聲。</span><span class="sxs-lookup"><span data-stu-id="98c39-138">**Simultaneous ringing** enables incoming calls to ring on additional phones (for example, a mobile phone) or other endpoint devices.</span></span> <span data-ttu-id="98c39-139">Lync Server 2013 為同時震鈴的設定選項提供了極大範圍的設定。</span><span class="sxs-lookup"><span data-stu-id="98c39-139">Lync Server 2013 provides a significantly wider range of configuration options for simultaneous ringing.</span></span> <span data-ttu-id="98c39-140">預設為啟用。</span><span class="sxs-lookup"><span data-stu-id="98c39-140">Enabled by default.</span></span>
    
      - <span data-ttu-id="98c39-p111">**[小組通話]** 可讓所定義小組的使用者接聽該小組其他成員的通話。預設為啟用。</span><span class="sxs-lookup"><span data-stu-id="98c39-p111">**Team call** enables users on a defined team to answer calls for other members of the team. Enabled by default.</span></span>
    
      - <span data-ttu-id="98c39-p112">**[PSTN 重新路由]** 可在 WAN 擁塞或無法使用時，將被指派此原則的使用者撥打給其他企業使用者的電話，以公用交換電話網路 (PSTN) 重新路由。預設為啟用。</span><span class="sxs-lookup"><span data-stu-id="98c39-p112">**PSTN re-route** enables calls made by users who are assigned this policy to other enterprise users to be rerouted on the public switched telephone network (PSTN) if the WAN is congested or unavailable. Enabled by default.</span></span>
    
      - <span data-ttu-id="98c39-145">**頻寬原則覆寫** 可讓系統管理員覆寫特定使用者的通話許可控制原則決定。</span><span class="sxs-lookup"><span data-stu-id="98c39-145">**Bandwidth policy override** enables administrators to override call admission control policy decisions for a particular user.</span></span> <span data-ttu-id="98c39-146">預設為停用。</span><span class="sxs-lookup"><span data-stu-id="98c39-146">Disabled by default.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="98c39-147">系統只會針對撥入給使用者的來電，而不會針對使用者撥出的電話覆寫此原則。</span><span class="sxs-lookup"><span data-stu-id="98c39-147">The policy will be overridden only for incoming calls to the user and not for outgoing calls that are placed by the user.</span></span> <span data-ttu-id="98c39-148">工作階段建立之後，便可準確地記錄頻寬使用量。</span><span class="sxs-lookup"><span data-stu-id="98c39-148">After the session is established, the bandwidth consumption will be accurately recorded.</span></span> <span data-ttu-id="98c39-149">此設定應該謹慎使用，且應該保留以供適當的通話許可控制決定。</span><span class="sxs-lookup"><span data-stu-id="98c39-149">This setting should be used sparingly and should be reserved for appropriate call admission control decisions.</span></span>

        
        </div>
    
      - <span data-ttu-id="98c39-150">**惡意呼叫追蹤功能** 可讓使用者報告惡意來電 (例如，使用用戶端 UI) 炸彈威脅，進而將通話詳細資料記錄中的呼叫旗標 (cdr) 。</span><span class="sxs-lookup"><span data-stu-id="98c39-150">**Malicious call tracing** enables users to report malicious calls (such as bomb threats) by using the client UI, which in turn flags the calls in the call detail records (CDRs).</span></span> <span data-ttu-id="98c39-151">預設為停用。</span><span class="sxs-lookup"><span data-stu-id="98c39-151">Disabled by default.</span></span>

8.  <span data-ttu-id="98c39-152">若要為此語音原則來關聯及設定 PSTN 使用方式記錄，請執行下列任何一項動作：</span><span class="sxs-lookup"><span data-stu-id="98c39-152">To associate and configure PSTN usage records for this voice policy, do any of the following:</span></span>
    
      - <span data-ttu-id="98c39-p116">若要從您 Enterprise Voice 部署中所有可用的 PSTN 使用方式記錄清單中選擇一或多個記錄，請按一下 **[選取]**。反白顯示您想要與此語音原則關聯的記錄，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="98c39-p116">To choose one or more records from a list of all PSTN usage records available in your Enterprise Voice deployment, click **Select**. Highlight the records that you want to associate with this voice policy, and then click **OK**.</span></span>
    
      - <span data-ttu-id="98c39-155">若要從此語音原則中移除 PSTN 使用方式記錄，請反白顯示記錄，然後按一下 **[移除]**。</span><span class="sxs-lookup"><span data-stu-id="98c39-155">To remove a PSTN usage record from this voice policy, highlight the record and click **Remove**.</span></span>
    
      - <span data-ttu-id="98c39-156">若要定義新的 PSTN 使用方式記錄，並將它與此語音原則關聯，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="98c39-156">To define a new PSTN usage record and associate it with this voice policy, do the following:</span></span>
        
        1.  <span data-ttu-id="98c39-157">按一下 **[新增]**。</span><span class="sxs-lookup"><span data-stu-id="98c39-157">Click **New**.</span></span>
        
        2.  <span data-ttu-id="98c39-158">在 **[名稱]** 欄位中，輸入記錄的唯一描述性名稱。</span><span class="sxs-lookup"><span data-stu-id="98c39-158">In the **Name** field, enter a unique descriptive name for the record.</span></span> <span data-ttu-id="98c39-159">例如，您可能想要為位於 Redmond 的全職員工建立名為 **redmond** 的 PSTN 使用方式記錄，以及暫時員工的另一個已命名的 **RedmondTemps** 。</span><span class="sxs-lookup"><span data-stu-id="98c39-159">For example, you may want to create a PSTN usage record named **Redmond** for full-time employees located in Redmond, and another named **RedmondTemps** for temporary employees.</span></span>
            
            <div>
            

            > [!NOTE]  
            > <span data-ttu-id="98c39-p118">PSTN 使用方式記錄名稱必須是 Enterprise Voice 部署內的唯一名稱。儲存記錄之後，就無法編輯 <STRONG>[名稱]</STRONG> 欄位。</span><span class="sxs-lookup"><span data-stu-id="98c39-p118">The PSTN usage record name must be unique within the Enterprise Voice deployment. After the record is saved, the <STRONG>Name</STRONG> field cannot be edited.</span></span>

            
            </div>
        
        3.  <span data-ttu-id="98c39-162">使用下列任一方法針對此 PSTN 使用方式記錄建立關聯及設定路由：</span><span class="sxs-lookup"><span data-stu-id="98c39-162">Use any of the following methods to associate and configure routes for this PSTN usage record:</span></span>
            
              - <span data-ttu-id="98c39-163">若要從 Enterprise Voice 部署中所有可用路由的清單中選擇一個或多個路由，請按一下 **[選取]**，並反白顯示想要與此 PSTN 使用方式記錄建立關聯的路由，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="98c39-163">To choose one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**, highlight the routes that you want to associate with this PSTN usage record, and then click **OK**.</span></span>
            
              - <span data-ttu-id="98c39-164">若要從 PSTN 使用方式記錄中移除路由，請反白顯示路由，然後按一下 [ **移除**]。</span><span class="sxs-lookup"><span data-stu-id="98c39-164">To remove a route from the PSTN usage record, highlight the route, and then click **Remove**.</span></span>
            
              - <span data-ttu-id="98c39-165">若要定義新的路由，並將它與此 PSTN 使用方式記錄關聯，請按一下 **[新增]**。</span><span class="sxs-lookup"><span data-stu-id="98c39-165">To define a new route and associate it with this PSTN usage record, click **New**.</span></span> <span data-ttu-id="98c39-166">如需詳細資訊，請參閱 [Create a voice route In Lync Server 2013](lync-server-2013-create-a-voice-route.md)。</span><span class="sxs-lookup"><span data-stu-id="98c39-166">For details, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>
            
              - <span data-ttu-id="98c39-167">若要編輯已與此 PSTN 使用方式記錄關聯的路由，請反白顯示路由，然後按一下 **[顯示詳細資料]**。</span><span class="sxs-lookup"><span data-stu-id="98c39-167">To edit a route that is already associated with this PSTN usage record, highlight the route and click **Show details**.</span></span> <span data-ttu-id="98c39-168">如需詳細資訊，請參閱 [Modify a voice route In Lync Server 2013](lync-server-2013-modify-a-voice-route.md)。</span><span class="sxs-lookup"><span data-stu-id="98c39-168">For details, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span></span>
        
        4.  <span data-ttu-id="98c39-169">按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="98c39-169">Click **OK**.</span></span>
    
      - <span data-ttu-id="98c39-170">若要編輯已經與此語音原則建立關聯的 PSTN 使用方式記錄，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="98c39-170">To edit a PSTN usage record that is already associated with this voice policy, do the following:</span></span>
        
        1.  <span data-ttu-id="98c39-171">反白顯示您想要編輯的 PSTN 使用方式記錄，然後按一下 [ **顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="98c39-171">Highlight the PSTN usage record that you want to edit, and then click **Show details**.</span></span>
        
        2.  <span data-ttu-id="98c39-172">使用下列任一方法，針對此 PSTN 使用方式記錄來建立關聯及設定路由：</span><span class="sxs-lookup"><span data-stu-id="98c39-172">Use any of the following methods to associate and configure routes for this PSTN usage record:</span></span>
            
              - <span data-ttu-id="98c39-173">若要從 Enterprise Voice 部署中所有可用路由的清單中選擇一個或多個路由，請按一下 **[選取]**，並反白顯示想要與此 PSTN 使用方式記錄關聯的路由，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="98c39-173">To choose one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**, highlight the routes you want to associate with this PSTN usage record, and then click **OK**.</span></span>
            
              - <span data-ttu-id="98c39-174">若要從此 PSTN 使用方式記錄中移除路由，請反白顯示路由，然後按一下 [ **移除**]。</span><span class="sxs-lookup"><span data-stu-id="98c39-174">To remove a route from this PSTN usage record, highlight the route, and then click **Remove**.</span></span>
            
              - <span data-ttu-id="98c39-175">若要定義新的路由，並將它與此 PSTN 使用方式記錄關聯，請按一下 **[新增]**。</span><span class="sxs-lookup"><span data-stu-id="98c39-175">To define a new route and associate it with this PSTN usage record, click **New**.</span></span> <span data-ttu-id="98c39-176">如需詳細資訊，請參閱 [Create a voice route In Lync Server 2013](lync-server-2013-create-a-voice-route.md)。</span><span class="sxs-lookup"><span data-stu-id="98c39-176">For details, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>
            
              - <span data-ttu-id="98c39-177">若要編輯已與此 PSTN 使用方式記錄相關聯的路由，請反白顯示路由和 lick **顯示詳細資料**。</span><span class="sxs-lookup"><span data-stu-id="98c39-177">To edit a route that is already associated with this PSTN usage record, highlight the route and lick **Show details**.</span></span> <span data-ttu-id="98c39-178">如需詳細資訊，請參閱 [Modify a voice route In Lync Server 2013](lync-server-2013-modify-a-voice-route.md)。</span><span class="sxs-lookup"><span data-stu-id="98c39-178">For details, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span></span>
        
        3.  <span data-ttu-id="98c39-179">按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="98c39-179">Click **OK**.</span></span>

9.  <span data-ttu-id="98c39-p123">排列 PSTN 使用方式記錄，以獲得最佳效能。若要變更清單中某筆記錄的位置，請反白顯示記錄名稱，然後按一下向上或向下箭頭。</span><span class="sxs-lookup"><span data-stu-id="98c39-p123">Arrange the PSTN usage records for optimum performance. To change a record’s position in the list, highlight the record name and click the up or down arrow.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="98c39-182">PSTN 使用方式記錄列在語音原則中的順序十分重要。</span><span class="sxs-lookup"><span data-stu-id="98c39-182">The order in which PSTN usage records are listed in the voice policy is significant.</span></span> <span data-ttu-id="98c39-183">Lync Server 會從上而往上，遍歷清單。</span><span class="sxs-lookup"><span data-stu-id="98c39-183">Lync Server traverses the list from the top down.</span></span> <span data-ttu-id="98c39-184">建議您依使用頻率來組織清單，例如：RedmondLocal、RedmondLongDist、RedmondInternational 和 RedmondBackup。</span><span class="sxs-lookup"><span data-stu-id="98c39-184">We recommend that you organize the list by frequency of use, for example: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup.</span></span>

    
    </div>

10. <span data-ttu-id="98c39-185">若要針對此語音原則中的來電轉接和同時鈴響建立關聯並設定 PSTN 使用方式記錄，請執行下列其中一項作業：</span><span class="sxs-lookup"><span data-stu-id="98c39-185">To associate and configure PSTN usage records for call forwarding and simultaneous ringing in this voice policy, do any of the following:</span></span>
    
      - <span data-ttu-id="98c39-186">若要依據此語音原則針對來電轉接和同時響鈴使用相同的 PSTN 使用方式記錄，請從下拉式功能表中選取 **[使用通話 PSTN 使用方式的路由]** 選項。</span><span class="sxs-lookup"><span data-stu-id="98c39-186">To use the same PSTN usage records for call forwarding and simultaneous ringing as this voice policy, select the option **Route using the call PSTN usages** from the drop-down menu.</span></span>
    
      - <span data-ttu-id="98c39-187">若要僅允許對內部 Lync 使用者進行來電轉接和同時響鈴，請選取 [僅從下拉式功能表 **傳送至內部 lync 使用者** 的選項]。</span><span class="sxs-lookup"><span data-stu-id="98c39-187">To allow call forwarding and simultaneous ringing to internal Lync users only, select the option **Route to internal Lync users only** from the drop-down menu.</span></span> <span data-ttu-id="98c39-188">通話不會轉接至外部 PSTN 號碼。</span><span class="sxs-lookup"><span data-stu-id="98c39-188">Calls will not be forwarded to external PSTN numbers.</span></span>
    
      - <span data-ttu-id="98c39-189">若要為此語音原則指定不同的 PSTN 使用方式記錄來進行來電轉接和同時響鈴，請從下拉式功能表中選取 [ **使用自訂 PSTN 使用** 方式的選項路由]。</span><span class="sxs-lookup"><span data-stu-id="98c39-189">To specify different PSTN usage records for call forwarding and simultaneous ringing than used for this voice policy, select the option **Route using custom PSTN usages** from the drop-down menu.</span></span> <span data-ttu-id="98c39-190">這個選項會顯示一個控制項，以選取現有的 PSTN 使用方式記錄，或專門針對來電轉接和同時響鈴建立新的 PSTN 使用方式記錄。</span><span class="sxs-lookup"><span data-stu-id="98c39-190">This option displays a control to select existing PSTN usage records or create new PSTN usage records specifically for call forwarding and simultaneous ringing.</span></span>
        
          - <span data-ttu-id="98c39-p127">若要針對來電轉接和同時響鈴從所有可用的 PSTN 使用方式記錄清單中選擇一筆或多筆記錄，請按一下 **[選取]**。反白顯示想要與此來電轉接和同時鈴響原則關聯的記錄，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="98c39-p127">To choose one or more records from a list of PSTN usage records for call forwarding and simultaneous ringing, click **Select**. Highlight the records that you want to associate with this call forwarding and simultaneous ringing policy, and then click **OK**.</span></span>
        
          - <span data-ttu-id="98c39-193">若要從此來電轉接和同時鈴響原則移除 PSTN 使用方式記錄，請反白顯示記錄，然後按一下 **[移除]**。</span><span class="sxs-lookup"><span data-stu-id="98c39-193">To remove a PSTN usage record from this call forwarding and simultaneous ringing policy, highlight the record and click **Remove**.</span></span>
        
          - <span data-ttu-id="98c39-194">若要定義新的 PSTN 使用方式記錄，並建立其與此來電轉接和同時鈴響的關聯，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="98c39-194">To define a new PSTN usage record and associate it with this call forwarding and simultaneous ringing policy, do the following:</span></span>
            
            1.  <span data-ttu-id="98c39-195">按一下 **[新增]**。</span><span class="sxs-lookup"><span data-stu-id="98c39-195">Click **New**.</span></span>
            
            2.  <span data-ttu-id="98c39-196">在 **[名稱]** 欄位中，輸入記錄的唯一描述性名稱。</span><span class="sxs-lookup"><span data-stu-id="98c39-196">In the **Name** field, enter a unique descriptive name for the record.</span></span>
                
                <div>
                

                > [!NOTE]  
                > <span data-ttu-id="98c39-p128">PSTN 使用方式記錄名稱必須是 Enterprise Voice 部署內的唯一名稱。儲存記錄之後，就無法編輯 <STRONG>[名稱]</STRONG> 欄位。</span><span class="sxs-lookup"><span data-stu-id="98c39-p128">The PSTN usage record name must be unique within the Enterprise Voice deployment. After the record is saved, the <STRONG>Name</STRONG> field cannot be edited.</span></span>

                
                </div>
            
            3.  <span data-ttu-id="98c39-199">使用下列任一方法針對此 PSTN 使用方式記錄建立關聯及設定路由：</span><span class="sxs-lookup"><span data-stu-id="98c39-199">Use any of the following methods to associate and configure routes for this PSTN usage record:</span></span>
                
                  - <span data-ttu-id="98c39-200">若要從 Enterprise Voice 部署中所有可用路由的清單中選擇一個或多個路由，請按一下 **[選取]**，並反白顯示想要與此 PSTN 使用方式記錄建立關聯的路由，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="98c39-200">To choose one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**, highlight the routes that you want to associate with this PSTN usage record, and then click **OK**.</span></span>
                
                  - <span data-ttu-id="98c39-201">若要從 PSTN 使用方式記錄中移除路由，請反白顯示路由，然後按一下 **[移除]**。</span><span class="sxs-lookup"><span data-stu-id="98c39-201">To remove a route from the PSTN usage record, highlight the route and click **Remove**.</span></span>
                
                  - <span data-ttu-id="98c39-202">若要定義新的路由，並將它與此 PSTN 使用方式記錄關聯，請按一下 **[新增]**。</span><span class="sxs-lookup"><span data-stu-id="98c39-202">To define a new route and associate it with this PSTN usage record, click **New**.</span></span> <span data-ttu-id="98c39-203">如需詳細資訊，請參閱 [Create a voice route In Lync Server 2013](lync-server-2013-create-a-voice-route.md)。</span><span class="sxs-lookup"><span data-stu-id="98c39-203">For details, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>
                
                  - <span data-ttu-id="98c39-204">若要編輯已與此 PSTN 使用方式記錄關聯的路由，請反白顯示路由，然後按一下 **[顯示詳細資料]**。</span><span class="sxs-lookup"><span data-stu-id="98c39-204">To edit a route that is already associated with this PSTN usage record, highlight the route and click **Show details**.</span></span> <span data-ttu-id="98c39-205">如需詳細資訊，請參閱 [Modify a voice route In Lync Server 2013](lync-server-2013-modify-a-voice-route.md)。</span><span class="sxs-lookup"><span data-stu-id="98c39-205">For details, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span></span>
            
            4.  <span data-ttu-id="98c39-206">按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="98c39-206">Click **OK**.</span></span>
        
          - <span data-ttu-id="98c39-207">若要編輯已經與此語音原則建立關聯的 PSTN 使用方式記錄，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="98c39-207">To edit a PSTN usage record that is already associated with this voice policy, do the following:</span></span>
            
            1.  <span data-ttu-id="98c39-208">反白顯示您想要編輯的 PSTN 使用方式記錄，然後按一下 [ **顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="98c39-208">Highlight the PSTN usage record you want to edit and click **Show details**.</span></span>
            
            2.  <span data-ttu-id="98c39-209">使用下列任一方法針對此 PSTN 使用方式記錄建立關聯及設定路由：</span><span class="sxs-lookup"><span data-stu-id="98c39-209">Use any of the following methods to associate and configure routes for this PSTN usage record:</span></span>
                
                  - <span data-ttu-id="98c39-210">若要從您 Enterprise Voice 部署中所有可用的路由清單中選擇一或多個路由，請按一下 **[選取]**，反白顯示您想要與此 PSTN 使用方式記錄關聯的路由，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="98c39-210">To choose one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**, highlight the routes that you want to associate with this PSTN usage record, and then click **OK**.</span></span>
                
                  - <span data-ttu-id="98c39-211">若要從此 PSTN 使用記錄移除路由，請反白顯示路由，然後按一下 **[移除]**。</span><span class="sxs-lookup"><span data-stu-id="98c39-211">To remove a route from this PSTN usage record, highlight the route and click **Remove**.</span></span>
                
                  - <span data-ttu-id="98c39-212">若要定義新的路由，並將它與此 PSTN 使用方式記錄關聯，請按一下 **[新增]**。</span><span class="sxs-lookup"><span data-stu-id="98c39-212">To define a new route and associate it with this PSTN usage record, click **New**.</span></span> <span data-ttu-id="98c39-213">如需詳細資訊，請參閱 [Create a voice route In Lync Server 2013](lync-server-2013-create-a-voice-route.md)。</span><span class="sxs-lookup"><span data-stu-id="98c39-213">For details, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>
                
                  - <span data-ttu-id="98c39-214">若要編輯已與此 PSTN 使用方式記錄關聯的路由，請反白顯示路由，然後按一下 **[顯示詳細資料]**。</span><span class="sxs-lookup"><span data-stu-id="98c39-214">To edit a route that is already associated with this PSTN usage record, highlight the route and click **Show details**.</span></span> <span data-ttu-id="98c39-215">如需詳細資訊，請參閱 [Modify a voice route In Lync Server 2013](lync-server-2013-modify-a-voice-route.md)。</span><span class="sxs-lookup"><span data-stu-id="98c39-215">For details, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span></span>
            
            3.  <span data-ttu-id="98c39-216">按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="98c39-216">Click **OK**.</span></span>

11. <span data-ttu-id="98c39-p133">(選用) 輸入號碼以測試語音原則，然後按一下 **[執行]**。測試結果會顯示在 **[要測試的轉譯號碼]** 下方。</span><span class="sxs-lookup"><span data-stu-id="98c39-p133">(Optional) Enter a number to test the voice policy and click **Go**. The test results are displayed under **Translated number to test**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="98c39-219">您可以儲存尚未通過測試的語音原則，稍後再加以重新設定。</span><span class="sxs-lookup"><span data-stu-id="98c39-219">You can save a voice policy that does not yet pass the test and then reconfigure it later.</span></span> <span data-ttu-id="98c39-220">如需詳細資訊，請參閱 <A href="lync-server-2013-test-voice-routing.md">Test voice routing In Lync Server 2013</A>。</span><span class="sxs-lookup"><span data-stu-id="98c39-220">For details, see <A href="lync-server-2013-test-voice-routing.md">Test voice routing in Lync Server 2013</A>.</span></span>

    
    </div>

12. <span data-ttu-id="98c39-221">按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="98c39-221">Click **OK**.</span></span>

13. <span data-ttu-id="98c39-222">在 **[語音原則]** 頁面上，依序按一下 **[認可]** 和 **[全部認可]**。</span><span class="sxs-lookup"><span data-stu-id="98c39-222">On the **Voice Policy** page, click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="98c39-223">任何時候建立或修改語音原則時，都必須執行「 <STRONG>認可全部</STRONG> 」命令，才能發佈設定變更。</span><span class="sxs-lookup"><span data-stu-id="98c39-223">Any time you create or modify a voice policy, you must run the <STRONG>Commit all</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="98c39-224">如需詳細資訊，請參閱 Operations 檔中的在 <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Lync Server 2013 中發佈擱置的變更至語音路由</A> 設定。</span><span class="sxs-lookup"><span data-stu-id="98c39-224">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

14. <span data-ttu-id="98c39-225">(選用) [語音信箱] 逸出會偵測使用者的行動電話語音信箱是否立即接聽來電，並中斷與行動電話語音信箱的連線。</span><span class="sxs-lookup"><span data-stu-id="98c39-225">(Optional) Voicemail Escape detects that a call was immediately answered by the user’s mobile phone voice mail, and disconnects the call to the mobile phone voice mail.</span></span> <span data-ttu-id="98c39-226">這樣可讓來電繼續在使用者的其他端點上響鈴，讓使用者有機會接聽來電。</span><span class="sxs-lookup"><span data-stu-id="98c39-226">This allows the call to continue to ring on the user’s other endpoints giving the user the opportunity to answer the call.</span></span> <span data-ttu-id="98c39-227">如需如何設定語音信箱原則的詳細資訊，請參閱 [在 Lync Server 2013 中設定語音信箱轉義](lync-server-2013-configuring-voice-mail-escape.md)。</span><span class="sxs-lookup"><span data-stu-id="98c39-227">For details on how to configure a voice mail policy, see [Configuring voice mail escape in Lync Server 2013](lync-server-2013-configuring-voice-mail-escape.md).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="98c39-228">另請參閱</span><span class="sxs-lookup"><span data-stu-id="98c39-228">See Also</span></span>


[<span data-ttu-id="98c39-229">在 Lync Server 2013 中修改語音原則和設定 PSTN 使用方式記錄</span><span class="sxs-lookup"><span data-stu-id="98c39-229">Modify a voice policy and configure PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md)  
[<span data-ttu-id="98c39-230">在 Lync Server 2013 中查看 PSTN 使用方式記錄</span><span class="sxs-lookup"><span data-stu-id="98c39-230">View PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-view-pstn-usage-records.md)  
[<span data-ttu-id="98c39-231">在 Lync Server 2013 中建立語音路由</span><span class="sxs-lookup"><span data-stu-id="98c39-231">Create a voice route in Lync Server 2013</span></span>](lync-server-2013-create-a-voice-route.md)  
[<span data-ttu-id="98c39-232">在 Lync Server 2013 中修改語音路由</span><span class="sxs-lookup"><span data-stu-id="98c39-232">Modify a voice route in Lync Server 2013</span></span>](lync-server-2013-modify-a-voice-route.md)  
[<span data-ttu-id="98c39-233">在 Lync Server 2013 中將擱置的變更發佈至語音路由設定</span><span class="sxs-lookup"><span data-stu-id="98c39-233">Publish pending changes to the voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  
[<span data-ttu-id="98c39-234">在 Lync Server 2013 中設定語音信箱轉義</span><span class="sxs-lookup"><span data-stu-id="98c39-234">Configuring voice mail escape in Lync Server 2013</span></span>](lync-server-2013-configuring-voice-mail-escape.md)  


[<span data-ttu-id="98c39-235">在 Lync Server 2013 中測試語音路由</span><span class="sxs-lookup"><span data-stu-id="98c39-235">Test voice routing in Lync Server 2013</span></span>](lync-server-2013-test-voice-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

