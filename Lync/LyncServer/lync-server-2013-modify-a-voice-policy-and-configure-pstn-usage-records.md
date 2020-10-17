---
title: Lync Server 2013：修改語音原則和設定 PSTN 使用方式記錄
description: Lync Server 2013：修改語音原則和設定 PSTN 使用方式記錄。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify a voice policy and configure PSTN usage records
ms:assetid: 6c53aaf5-218b-4bd4-8cea-31bc9d53f1bd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398511(v=OCS.15)
ms:contentKeyID: 48184419
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e26d6c8654ebf758f8b5a185c21468443e0451a9
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559369"
---
# <a name="modify-a-voice-policy-and-configure-pstn-usage-records-in-lync-server-2013"></a><span data-ttu-id="faf1c-103">在 Lync Server 2013 中修改語音原則和設定 PSTN 使用方式記錄</span><span class="sxs-lookup"><span data-stu-id="faf1c-103">Modify a voice policy and configure PSTN usage records in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="faf1c-104">_**主題上次修改日期：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="faf1c-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="faf1c-105">如果您想要修改語音原則，請遵循下列步驟。</span><span class="sxs-lookup"><span data-stu-id="faf1c-105">Follow these steps if you want to modify a voice policy.</span></span> <span data-ttu-id="faf1c-106">如果您想要建立新的語音原則，請參閱 [在 Lync Server 2013 中建立語音原則和設定 PSTN 使用方式記錄](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md) ，以取得此過程。</span><span class="sxs-lookup"><span data-stu-id="faf1c-106">If you want to create a new voice policy, see [Create a voice policy and configure PSTN usage records in Lync Server 2013](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md) for the procedure.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="faf1c-107">如果將使用者指派給沒有相關聯公用交換電話網路 (PSTN) 使用方式記錄的語音原則，則該使用者無法撥出電話。</span><span class="sxs-lookup"><span data-stu-id="faf1c-107">If a user is assigned to a voice policy has no associated public switched telephone network (PSTN) usage records, the user cannot place outbound calls.</span></span> <span data-ttu-id="faf1c-108">如需您 Enterprise Voice 部署中所有可用的 PSTN 使用方式記錄清單，並查看其屬性，請參閱 <A href="lync-server-2013-view-pstn-usage-records.md">在 Lync Server 2013 中查看 PSTN 使用方式記錄</A>。</span><span class="sxs-lookup"><span data-stu-id="faf1c-108">For a listing of all PSTN usage records available in your Enterprise Voice deployment and view their properties, see <A href="lync-server-2013-view-pstn-usage-records.md">View PSTN usage records in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-modify-a-voice-policy"></a><span data-ttu-id="faf1c-109">若要修改語音原則</span><span class="sxs-lookup"><span data-stu-id="faf1c-109">To modify a voice policy</span></span>

1.  <span data-ttu-id="faf1c-110">以 RTCUniversalServerAdmins 群組成員的身分，或是 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色的成員身分登入電腦。</span><span class="sxs-lookup"><span data-stu-id="faf1c-110">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="faf1c-111">如需詳細資訊，請參閱 [在 Lync Server 2013 中委派設定許可權](lync-server-2013-delegate-setup-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="faf1c-111">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="faf1c-112">開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="faf1c-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="faf1c-113">如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="faf1c-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="faf1c-114">在左導覽列中，依序按一下 **[語音路由]** 和 **[語音原則]**。</span><span class="sxs-lookup"><span data-stu-id="faf1c-114">In the left navigation bar, click **Voice Routing**, and then click **Voice Policy**.</span></span>

4.  <span data-ttu-id="faf1c-115">在 **[語音原則]** 頁面上，按兩下語音原則名稱。</span><span class="sxs-lookup"><span data-stu-id="faf1c-115">On the **Voice Policy** page, double-click a voice policy name.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="faf1c-p105">範圍和名稱在語音原則建立時就已設定。您無法加以變更。</span><span class="sxs-lookup"><span data-stu-id="faf1c-p105">The scope and name were set when the voice policy was created. They cannot be changed.</span></span>

    
    </div>

5.  <span data-ttu-id="faf1c-118">(選用) 在 **[編輯語音原則]** 中，輸入語音原則的其他描述性資訊。</span><span class="sxs-lookup"><span data-stu-id="faf1c-118">(Optional) In **Edit Voice Policy**, enter additional descriptive information for the voice policy.</span></span>

6.  <span data-ttu-id="faf1c-119">選取或清除下列核取方塊以啟用或停用每個 **[撥號功能]**：</span><span class="sxs-lookup"><span data-stu-id="faf1c-119">Select or clear the following check boxes to enable or disable each of the **Calling features**:</span></span>
    
      - <span data-ttu-id="faf1c-120">**[語音信箱逸出]** 可在設定為同時響鈴，且手機在關機、電池電力耗盡或在收訊範圍之外時，防止通話立即路由傳送至使用者的行動電話語音信箱系統。</span><span class="sxs-lookup"><span data-stu-id="faf1c-120">**Voice mail escape** prevents calls from being immediately routed to the user’s mobile phone voice mail system when simultaneous ringing is configured and the phone is turned off, out of battery, or out of range.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="faf1c-121">此功能僅可透過 Lync Server 管理命令介面進行設定</span><span class="sxs-lookup"><span data-stu-id="faf1c-121">This feature is only configurable through the Lync Server Management Shell</span></span>

        
        </div>
    
      - <span data-ttu-id="faf1c-122">**[來電轉接]** 可讓使用者將來電轉接到其他電話和用戶端裝置。</span><span class="sxs-lookup"><span data-stu-id="faf1c-122">**Call forwarding** enables users to forward calls to other phones and client devices.</span></span> <span data-ttu-id="faf1c-123">Lync Server 2013 為來電轉接提供更為廣泛的設定選項。</span><span class="sxs-lookup"><span data-stu-id="faf1c-123">Lync Server 2013 provides a significantly wider range of configuration options for call forwarding.</span></span> <span data-ttu-id="faf1c-124">例如，如果組織不想讓來電向外轉接到 PSTN，系統管理員可套用特殊語音原則以部署此限制。</span><span class="sxs-lookup"><span data-stu-id="faf1c-124">For example, if an organization does not want to allow incoming calls to be forwarded externally to the PSTN, an administrator can apply a special voice policy to deploy this restriction.</span></span> <span data-ttu-id="faf1c-125">預設為啟用。</span><span class="sxs-lookup"><span data-stu-id="faf1c-125">Enabled by default.</span></span>
    
      - <span data-ttu-id="faf1c-126">**[委派]** 可讓使用者指定其他使用者，來代表他們撥號和接聽電話。</span><span class="sxs-lookup"><span data-stu-id="faf1c-126">**Delegation** enables users to specify other users to send and receive calls on their behalf.</span></span> <span data-ttu-id="faf1c-127">在 Lync Server 2013 中，代理人可以設定同時震鈴，讓來電者能夠撥打所有代理人同時震鈴的目標。</span><span class="sxs-lookup"><span data-stu-id="faf1c-127">In Lync Server 2013, a delegate can configure simultaneous ringing that enables incoming calls to his or her manager to ring all of the delegate’s simultaneous ringing targets.</span></span> <span data-ttu-id="faf1c-128">這樣可在回應撥至主管的通話時給予代理人更大的彈性。</span><span class="sxs-lookup"><span data-stu-id="faf1c-128">This provides the delegate with greater flexibility in responding to calls directed to the manager.</span></span> <span data-ttu-id="faf1c-129">預設為啟用。</span><span class="sxs-lookup"><span data-stu-id="faf1c-129">Enabled by default.</span></span>
    
      - <span data-ttu-id="faf1c-p108">**[通話轉接]** 可讓使用者將通話轉接給其他使用者。預設為啟用。</span><span class="sxs-lookup"><span data-stu-id="faf1c-p108">**Call transfer** enables users to transfer calls to other users. Enabled by default.</span></span>
    
      - <span data-ttu-id="faf1c-p109">**[通話駐留]** 可讓使用者將通話駐留成保留狀態，然後由不同電話或用戶端接聽通話。預設為停用。</span><span class="sxs-lookup"><span data-stu-id="faf1c-p109">**Call park** enables users to park calls on hold, and then pick up the call from a different phone or client. Disabled by default.</span></span>
    
      - <span data-ttu-id="faf1c-134">**[同時響鈴]** 可讓來電在更多電話 (例如，行動電話) 或其他端點裝置上發出鈴聲。</span><span class="sxs-lookup"><span data-stu-id="faf1c-134">**Simultaneous ringing** enables incoming calls to ring on additional phones (for example, a mobile phone) or other endpoint devices.</span></span> <span data-ttu-id="faf1c-135">Lync Server 2013 為同時震鈴的設定選項提供了極大範圍的設定。</span><span class="sxs-lookup"><span data-stu-id="faf1c-135">Lync Server 2013 provides a significantly wider range of configuration options for simultaneous ringing.</span></span> <span data-ttu-id="faf1c-136">預設為啟用。</span><span class="sxs-lookup"><span data-stu-id="faf1c-136">Enabled by default.</span></span>
    
      - <span data-ttu-id="faf1c-p111">**[小組通話]** 可讓所定義小組的使用者接聽該小組其他成員的通話。預設為啟用。</span><span class="sxs-lookup"><span data-stu-id="faf1c-p111">**Team call** enables users on a defined team to answer calls for other members of the team. Enabled by default.</span></span>
    
      - <span data-ttu-id="faf1c-p112">**[PSTN 重新路由]** 可在 WAN 擁塞或無法使用時，將被指派此原則的使用者撥打給其他企業使用者的電話，以公用交換電話網路 (PSTN) 重新路由。預設為啟用。</span><span class="sxs-lookup"><span data-stu-id="faf1c-p112">**PSTN re-route** enables calls made by users who are assigned this policy to other enterprise users to be rerouted on the public switched telephone network (PSTN) if the WAN is congested or unavailable. Enabled by default.</span></span>
    
      - <span data-ttu-id="faf1c-p113">**[頻寬原則覆寫]** 可讓系統管理員覆寫特定使用者的通話許可控制 (CAC) 原則決策。預設為停用。</span><span class="sxs-lookup"><span data-stu-id="faf1c-p113">**Bandwidth policy override** enables administrators to override call admission control (CAC) policy decisions for a particular user. Disabled by default.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="faf1c-p114">系統只會針對撥入給使用者的來電，而不會針對使用者撥出的電話覆寫此原則。工作階段建立之後，便可準確地記錄頻寬使用量。請謹慎使用此設定。</span><span class="sxs-lookup"><span data-stu-id="faf1c-p114">The policy will be overridden only for incoming calls to the user and not for outgoing calls that are placed by the user. After the session is established, the bandwidth consumption will be accurately recorded. This setting should be used sparingly.</span></span>

        
        </div>
    
      - <span data-ttu-id="faf1c-p115">**[惡意通話追蹤]** 可讓使用者使用用戶端 UI 來回報惡意通話 (如炸彈威脅)，此舉會在詳細通話記錄 (CDR) 中以旗標標記通話。預設為停用。</span><span class="sxs-lookup"><span data-stu-id="faf1c-p115">**Malicious call tracing** enables users to report malicious calls (such as bomb threats) using the client UI, which in turn flags the calls in the call detail records (CDRs). Disabled by default.</span></span>

7.  <span data-ttu-id="faf1c-148">若要為此語音原則來關聯及設定 PSTN 使用方式記錄，請執行下列任何一項動作：</span><span class="sxs-lookup"><span data-stu-id="faf1c-148">To associate and configure PSTN usage records for this voice policy, do any of the following:</span></span>
    
      - <span data-ttu-id="faf1c-p116">若要從您 Enterprise Voice 部署中所有可用的 PSTN 使用方式記錄清單中選擇一或多個記錄，請按一下 **[選取]**。反白顯示您想要與此語音原則關聯的記錄，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="faf1c-p116">To choose one or more records from a list of all PSTN usage records available in your Enterprise Voice deployment, click **Select**. Highlight the records that you want to associate with this voice policy, and then click **OK**.</span></span>
    
      - <span data-ttu-id="faf1c-151">若要從此語音原則中移除 PSTN 使用方式記錄，請反白顯示記錄，然後按一下 **[移除]**。</span><span class="sxs-lookup"><span data-stu-id="faf1c-151">To remove a PSTN usage record from this voice policy, highlight the record and click **Remove**.</span></span>
    
      - <span data-ttu-id="faf1c-152">若要定義新的 PSTN 使用方式記錄，並將它與此語音原則關聯，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="faf1c-152">To define a new PSTN usage record and associate it with this voice policy, do the following:</span></span>
        
        1.  <span data-ttu-id="faf1c-153">按一下 **[新增]**。</span><span class="sxs-lookup"><span data-stu-id="faf1c-153">Click **New**.</span></span>
        
        2.  <span data-ttu-id="faf1c-p117">在 **[名稱]** 欄位中，輸入記錄的唯一描述性名稱。例如，您可能會想要針對 Redmond 的全職員工建立一個名為 **Redmond** 的 PSTN 使用方式記錄，並針對臨時員工建立另一個名為 **RedmondTemps** 的記錄。</span><span class="sxs-lookup"><span data-stu-id="faf1c-p117">In the **Name** field, enter a unique descriptive name for the record. For example, you may want to create a PSTN usage record named **Redmond** for full-time employees located in Redmond, and another record named **RedmondTemps** for temporary employees.</span></span>
            
            <div>
            

            > [!NOTE]  
            > <span data-ttu-id="faf1c-p118">在 Enterprise Voice 部署內，PSTN 使用方式記錄名稱必須是唯一的。儲存記錄之後，就無法編輯 <STRONG>[名稱]</STRONG> 欄位。</span><span class="sxs-lookup"><span data-stu-id="faf1c-p118">The PSTN usage record name must be unique within the Enterprise Voice deployment. After the record is saved, the <STRONG>Name</STRONG> field cannot be edited.</span></span>

            
            </div>
        
        3.  <span data-ttu-id="faf1c-158">使用下列任一方法針對此 PSTN 使用方式記錄建立關聯及設定路由：</span><span class="sxs-lookup"><span data-stu-id="faf1c-158">Use any of the following methods to associate and configure routes for this PSTN usage record:</span></span>
            
              - <span data-ttu-id="faf1c-159">若要從 Enterprise Voice 部署中所有可用路由的清單中選擇一個或多個路由，請按一下 **[選取]**，並反白顯示想要與此 PSTN 使用方式記錄建立關聯的路由，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="faf1c-159">To choose one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**, highlight the routes that you want to associate with this PSTN usage record, and then click **OK**.</span></span>
            
              - <span data-ttu-id="faf1c-160">若要從 PSTN 使用方式記錄中移除路由，請反白顯示路由，然後按一下 **[移除]**。</span><span class="sxs-lookup"><span data-stu-id="faf1c-160">To remove a route from the PSTN usage record, highlight the route and click **Remove**.</span></span>
            
              - <span data-ttu-id="faf1c-161">若要定義新的路由，並將它與此 PSTN 使用方式記錄關聯，請按一下 **[新增]**。</span><span class="sxs-lookup"><span data-stu-id="faf1c-161">To define a new route and associate it with this PSTN usage record, click **New**.</span></span> <span data-ttu-id="faf1c-162">如需詳細資訊，請參閱 [Create a voice route In Lync Server 2013](lync-server-2013-create-a-voice-route.md)。</span><span class="sxs-lookup"><span data-stu-id="faf1c-162">For details, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>
            
              - <span data-ttu-id="faf1c-163">若要編輯已與此 PSTN 使用方式記錄關聯的路由，請反白顯示路由，然後按一下 **[顯示詳細資料]**。</span><span class="sxs-lookup"><span data-stu-id="faf1c-163">To edit a route that is already associated with this PSTN usage record, highlight the route and click **Show details**.</span></span> <span data-ttu-id="faf1c-164">如需詳細資訊，請參閱 [Modify a voice route In Lync Server 2013](lync-server-2013-modify-a-voice-route.md)。</span><span class="sxs-lookup"><span data-stu-id="faf1c-164">For details, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span></span>
        
        4.  <span data-ttu-id="faf1c-165">按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="faf1c-165">Click **OK**.</span></span>
    
      - <span data-ttu-id="faf1c-166">若要編輯已經與此語音原則建立關聯的 PSTN 使用方式記錄，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="faf1c-166">To edit a PSTN usage record that is already associated with this voice policy, do the following:</span></span>
        
        1.  <span data-ttu-id="faf1c-167">反白顯示希望編輯的 PSTN 使用方式記錄，然後按一下 **[顯示詳細資料]**。</span><span class="sxs-lookup"><span data-stu-id="faf1c-167">Highlight the PSTN usage record that you want to edit and click **Show details**.</span></span>
        
        2.  <span data-ttu-id="faf1c-168">使用下列任何一種方法來關聯及設定此 PSTN 使用方式記錄的路由：</span><span class="sxs-lookup"><span data-stu-id="faf1c-168">Use any of the following methods to associate and configure routes for this PSTN usage record:</span></span>
            
              - <span data-ttu-id="faf1c-169">若要從您 Enterprise Voice 部署中所有可用的路由清單中選擇一或多個路由，請按一下 **[選取]**，反白顯示您想要與此 PSTN 使用方式記錄關聯的路由，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="faf1c-169">To choose one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**, highlight the routes that you want to associate with this PSTN usage record, and then click **OK**.</span></span>
            
              - <span data-ttu-id="faf1c-170">若要從此 PSTN 使用記錄移除路由，請反白顯示路由，然後按一下 **[移除]**。</span><span class="sxs-lookup"><span data-stu-id="faf1c-170">To remove a route from this PSTN usage record, highlight the route and click **Remove**.</span></span>
            
              - <span data-ttu-id="faf1c-171">若要定義新的路由，並將它與此 PSTN 使用方式記錄關聯，請按一下 **[新增]**。</span><span class="sxs-lookup"><span data-stu-id="faf1c-171">To define a new route and associate it with this PSTN usage record, click **New**.</span></span> <span data-ttu-id="faf1c-172">如需詳細資訊，請參閱 [Create a voice route In Lync Server 2013](lync-server-2013-create-a-voice-route.md)。</span><span class="sxs-lookup"><span data-stu-id="faf1c-172">For details, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>
            
              - <span data-ttu-id="faf1c-173">若要編輯已與此 PSTN 使用方式記錄關聯的路由，請反白顯示路由，然後按一下 **[顯示詳細資料]**。</span><span class="sxs-lookup"><span data-stu-id="faf1c-173">To edit a route that is already associated with this PSTN usage record, highlight the route and click **Show details**.</span></span> <span data-ttu-id="faf1c-174">如需詳細資訊，請參閱 [Modify a voice route In Lync Server 2013](lync-server-2013-modify-a-voice-route.md)。</span><span class="sxs-lookup"><span data-stu-id="faf1c-174">For details, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span></span>
        
        3.  <span data-ttu-id="faf1c-175">按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="faf1c-175">Click **OK**.</span></span>

8.  <span data-ttu-id="faf1c-p123">排列 PSTN 使用方式記錄，以獲得最佳效能。若要變更清單中某筆記錄的位置，請反白顯示記錄名稱，然後按一下向上或向下箭頭。</span><span class="sxs-lookup"><span data-stu-id="faf1c-p123">Arrange the PSTN usage records for optimum performance. To change a record’s position in the list, highlight the record name and click the up or down arrow.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="faf1c-178">PSTN 使用方式記錄列在語音原則中的順序十分重要。</span><span class="sxs-lookup"><span data-stu-id="faf1c-178">The order in which PSTN usage records are listed in the voice policy is significant.</span></span> <span data-ttu-id="faf1c-179">Lync Server 會從上而往上，遍歷清單。</span><span class="sxs-lookup"><span data-stu-id="faf1c-179">Lync Server traverses the list from the top down.</span></span> <span data-ttu-id="faf1c-180">建議您依使用頻率來組織清單，例如：RedmondLocal、RedmondLongDist、RedmondInternational 和 RedmondBackup。</span><span class="sxs-lookup"><span data-stu-id="faf1c-180">We recommend that you organize the list by frequency of use, for example: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup.</span></span>

    
    </div>

9.  <span data-ttu-id="faf1c-181">若要針對此語音原則中的來電轉接和同時鈴響建立關聯並設定 PSTN 使用方式記錄，請執行下列其中一項作業：</span><span class="sxs-lookup"><span data-stu-id="faf1c-181">To associate and configure PSTN usage records for call forwarding and simultaneous ringing in this voice policy, do any of the following:</span></span>
    
      - <span data-ttu-id="faf1c-182">若要依據此語音原則針對來電轉接和同時響鈴使用相同的 PSTN 使用方式記錄，請從下拉式功能表中選取 **[使用通話 PSTN 使用方式的路由]** 選項。</span><span class="sxs-lookup"><span data-stu-id="faf1c-182">To use the same PSTN usage records for call forwarding and simultaneous ringing as this voice policy, select the option **Route using the call PSTN usages** from the drop-down menu.</span></span>
    
      - <span data-ttu-id="faf1c-183">若要僅允許對內部 Lync 使用者進行來電轉接和同時響鈴，請選取 [僅從下拉式功能表 **傳送至內部 lync 使用者** ]。</span><span class="sxs-lookup"><span data-stu-id="faf1c-183">To allow call forwarding and simultaneous ringing to internal Lync users only, select **Route to internal Lync users only** from the drop-down menu.</span></span> <span data-ttu-id="faf1c-184">通話不會轉接至外部 PSTN 號碼。</span><span class="sxs-lookup"><span data-stu-id="faf1c-184">Calls will not be forwarded to external PSTN numbers.</span></span>
    
      - <span data-ttu-id="faf1c-p126">若要針對用於此語音原則之外的來電轉接和同時響鈴指定其他 PSTN 使用方式記錄，請從下拉式功能表中選取 **[使用自訂 PSTN 使用方式的路由]** 選項。此選項會特別針對來電轉接和同時響鈴顯示控制項，用來選取現有 PSTN 使用方式記錄或建立新的 PSTN 使用方式記錄。</span><span class="sxs-lookup"><span data-stu-id="faf1c-p126">To specify different PSTN usage records for call forwarding and simultaneous ringing than those used for this voice policy, select the option **Route using custom PSTN usages** from the drop-down menu. This option displays a control to select existing PSTN usage records or to create new PSTN usage records, specifically for call forwarding and simultaneous ringing.</span></span>
        
          - <span data-ttu-id="faf1c-p127">若要針對來電轉接和同時響鈴從所有可用的 PSTN 使用方式記錄清單中選擇一筆或多筆記錄，請按一下 **[選取]**。反白顯示想要與此來電轉接和同時鈴響原則關聯的記錄，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="faf1c-p127">To choose one or more records from a list of PSTN usage records for call forwarding and simultaneous ringing, click **Select**. Highlight the records that you want to associate with this call forwarding and simultaneous ringing policy, and then click **OK**.</span></span>
        
          - <span data-ttu-id="faf1c-189">若要從此來電轉接和同時鈴響原則移除 PSTN 使用方式記錄，請反白顯示記錄，然後按一下 **[移除]**。</span><span class="sxs-lookup"><span data-stu-id="faf1c-189">To remove a PSTN usage record from this call forwarding and simultaneous ringing policy, highlight the record and click **Remove**.</span></span>
        
          - <span data-ttu-id="faf1c-190">若要定義新的 PSTN 使用方式記錄，並建立其與此來電轉接和同時鈴響的關聯，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="faf1c-190">To define a new PSTN usage record and associate it with this call forwarding and simultaneous ringing policy, do the following:</span></span>
            
            1.  <span data-ttu-id="faf1c-191">按一下 **[新增]**。</span><span class="sxs-lookup"><span data-stu-id="faf1c-191">Click **New**.</span></span>
            
            2.  <span data-ttu-id="faf1c-192">在 **[名稱]** 欄位中，輸入記錄的唯一描述性名稱。</span><span class="sxs-lookup"><span data-stu-id="faf1c-192">In the **Name** field, enter a unique descriptive name for the record.</span></span>
                
                <div>
                

                > [!NOTE]  
                > <span data-ttu-id="faf1c-p128">PSTN 使用方式記錄名稱必須是 Enterprise Voice 部署內的唯一名稱。儲存記錄之後，就無法編輯 <STRONG>[名稱]</STRONG> 欄位。</span><span class="sxs-lookup"><span data-stu-id="faf1c-p128">The PSTN usage record name must be unique within the Enterprise Voice deployment. After the record is saved, the <STRONG>Name</STRONG> field cannot be edited.</span></span>

                
                </div>
            
            3.  <span data-ttu-id="faf1c-195">使用下列任一方法針對此 PSTN 使用方式記錄建立關聯及設定路由：</span><span class="sxs-lookup"><span data-stu-id="faf1c-195">Use any of the following methods to associate and configure routes for this PSTN usage record:</span></span>
                
                  - <span data-ttu-id="faf1c-196">若要從 Enterprise Voice 部署中所有可用路由的清單中選擇一個或多個路由，請按一下 **[選取]**，並反白顯示想要與此 PSTN 使用方式記錄建立關聯的路由，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="faf1c-196">To choose one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**, highlight the routes that you want to associate with this PSTN usage record, and then click **OK**.</span></span>
                
                  - <span data-ttu-id="faf1c-197">若要從 PSTN 使用方式記錄中移除路由，請反白顯示路由，然後按一下 **[移除]**。</span><span class="sxs-lookup"><span data-stu-id="faf1c-197">To remove a route from the PSTN usage record, highlight the route and click **Remove**.</span></span>
                
                  - <span data-ttu-id="faf1c-198">若要定義新的路由，並將它與此 PSTN 使用方式記錄關聯，請按一下 **[新增]**。</span><span class="sxs-lookup"><span data-stu-id="faf1c-198">To define a new route and associate it with this PSTN usage record, click **New**.</span></span> <span data-ttu-id="faf1c-199">如需詳細資訊，請參閱 [Create a voice route In Lync Server 2013](lync-server-2013-create-a-voice-route.md)。</span><span class="sxs-lookup"><span data-stu-id="faf1c-199">For details, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>
                
                  - <span data-ttu-id="faf1c-200">若要編輯已經與此 PSTN 使用方式記錄建立關聯的路由，請反白顯示路由，然後按一下 **[顯示詳細資料]**。</span><span class="sxs-lookup"><span data-stu-id="faf1c-200">To edit a route that is already associated with this PSTN usage record, highlight the route, and then click **Show details**.</span></span> <span data-ttu-id="faf1c-201">如需詳細資訊，請參閱 [Modify a voice route In Lync Server 2013](lync-server-2013-modify-a-voice-route.md)。</span><span class="sxs-lookup"><span data-stu-id="faf1c-201">For details, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span></span>
            
            4.  <span data-ttu-id="faf1c-202">按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="faf1c-202">Click **OK**.</span></span>
        
          - <span data-ttu-id="faf1c-203">若要編輯已經與此語音原則建立關聯的 PSTN 使用方式記錄，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="faf1c-203">To edit a PSTN usage record that is already associated with this voice policy, do the following:</span></span>
            
            1.  <span data-ttu-id="faf1c-204">反白顯示希望編輯的 PSTN 使用方式記錄，然後按一下 **[顯示詳細資料]**。</span><span class="sxs-lookup"><span data-stu-id="faf1c-204">Highlight the PSTN usage record that you want to edit and click **Show details**.</span></span>
            
            2.  <span data-ttu-id="faf1c-205">使用下列任一方法，針對此 PSTN 使用方式記錄來建立關聯及設定路由：</span><span class="sxs-lookup"><span data-stu-id="faf1c-205">Use any of the following methods to associate and configure routes for this PSTN usage record:</span></span>
                
                  - <span data-ttu-id="faf1c-206">若要從 Enterprise Voice 部署中所有可用路由的清單中選擇一個或多個路由，請按一下 **[選取]**，並反白顯示想要與此 PSTN 使用方式記錄關聯的路由，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="faf1c-206">To choose one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**, highlight the routes you want to associate with this PSTN usage record, and then click **OK**.</span></span>
                
                  - <span data-ttu-id="faf1c-207">若要從此 PSTN 使用方式記錄中移除路由，請反白顯示路由，然後按一下 **[移除]**。</span><span class="sxs-lookup"><span data-stu-id="faf1c-207">To remove a route from this PSTN usage record, highlight the route and click **Remove**.</span></span>
                
                  - <span data-ttu-id="faf1c-208">若要定義新的路由，並將它與此 PSTN 使用方式記錄關聯，請按一下 **[新增]**。</span><span class="sxs-lookup"><span data-stu-id="faf1c-208">To define a new route and associate it with this PSTN usage record, click **New**.</span></span> <span data-ttu-id="faf1c-209">如需詳細資訊，請參閱 [Create a voice route In Lync Server 2013](lync-server-2013-create-a-voice-route.md)。</span><span class="sxs-lookup"><span data-stu-id="faf1c-209">For details, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>
                
                  - <span data-ttu-id="faf1c-210">若要編輯已與此 PSTN 使用方式記錄關聯的路由，請反白顯示路由，然後按一下 **[顯示詳細資料]**。</span><span class="sxs-lookup"><span data-stu-id="faf1c-210">To edit a route that is already associated with this PSTN usage record, highlight the route and click **Show details**.</span></span> <span data-ttu-id="faf1c-211">如需詳細資訊，請參閱 [Modify a voice route In Lync Server 2013](lync-server-2013-modify-a-voice-route.md)。</span><span class="sxs-lookup"><span data-stu-id="faf1c-211">For details, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span></span>
            
            3.  <span data-ttu-id="faf1c-212">按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="faf1c-212">Click **OK**.</span></span>

10. <span data-ttu-id="faf1c-p133">(選用) 輸入號碼以測試語音原則，然後按一下 **[執行]**。測試結果會顯示在 **[要測試的轉譯號碼]** 下方。</span><span class="sxs-lookup"><span data-stu-id="faf1c-p133">(Optional) Enter a number to test the voice policy and click **Go**. The test results are displayed under **Translated number to test**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="faf1c-215">您可以儲存尚未通過測試的語音原則，稍後再加以重新設定。</span><span class="sxs-lookup"><span data-stu-id="faf1c-215">You can save a voice policy that does not yet pass the test and then reconfigure it later.</span></span> <span data-ttu-id="faf1c-216">如需詳細資訊，請參閱 <A href="lync-server-2013-test-voice-routing.md">Test voice routing In Lync Server 2013</A>。</span><span class="sxs-lookup"><span data-stu-id="faf1c-216">For details, see <A href="lync-server-2013-test-voice-routing.md">Test voice routing in Lync Server 2013</A>.</span></span>

    
    </div>

11. <span data-ttu-id="faf1c-217">按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="faf1c-217">Click **OK**.</span></span>

12. <span data-ttu-id="faf1c-218">在 **[語音原則]** 頁面上，依序按一下 **[認可]** 和 **[全部認可]**。</span><span class="sxs-lookup"><span data-stu-id="faf1c-218">On the **Voice Policy** page, click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="faf1c-219">只要建立或修改語音原則，就必須執行 <STRONG>[全部認可]</STRONG> 命令來發行設定變更。</span><span class="sxs-lookup"><span data-stu-id="faf1c-219">Whenever you create or modify a voice policy, you must run the <STRONG>Commit all</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="faf1c-220">如需詳細資訊，請參閱 Operations 檔中的在 <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Lync Server 2013 中發佈擱置的變更至語音路由</A> 設定。</span><span class="sxs-lookup"><span data-stu-id="faf1c-220">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

13. <span data-ttu-id="faf1c-221">(選用) [語音信箱] 逸出會偵測使用者的行動電話語音信箱是否立即接聽來電，並中斷與行動電話語音信箱的連線。</span><span class="sxs-lookup"><span data-stu-id="faf1c-221">(Optional) Voicemail Escape detects that a call was immediately answered by the user’s mobile phone voice mail, and disconnects the call to the mobile phone voice mail.</span></span> <span data-ttu-id="faf1c-222">這樣可讓來電繼續在使用者的其他端點上響鈴，讓使用者有機會接聽來電。</span><span class="sxs-lookup"><span data-stu-id="faf1c-222">This allows the call to continue to ring on the user’s other endpoints giving the user the opportunity to answer the call.</span></span> <span data-ttu-id="faf1c-223">如需如何設定語音信箱原則的詳細資訊，請參閱 [在 Lync Server 2013 中設定語音信箱轉義](lync-server-2013-configuring-voice-mail-escape.md)。</span><span class="sxs-lookup"><span data-stu-id="faf1c-223">For details about how to configure a voice mail policy, see [Configuring voice mail escape in Lync Server 2013](lync-server-2013-configuring-voice-mail-escape.md).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="faf1c-224">另請參閱</span><span class="sxs-lookup"><span data-stu-id="faf1c-224">See Also</span></span>


[<span data-ttu-id="faf1c-225">在 Lync Server 2013 中建立語音原則和設定 PSTN 使用方式記錄</span><span class="sxs-lookup"><span data-stu-id="faf1c-225">Create a voice policy and configure PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)  
[<span data-ttu-id="faf1c-226">在 Lync Server 2013 中查看 PSTN 使用方式記錄</span><span class="sxs-lookup"><span data-stu-id="faf1c-226">View PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-view-pstn-usage-records.md)  
[<span data-ttu-id="faf1c-227">在 Lync Server 2013 中建立語音路由</span><span class="sxs-lookup"><span data-stu-id="faf1c-227">Create a voice route in Lync Server 2013</span></span>](lync-server-2013-create-a-voice-route.md)  
[<span data-ttu-id="faf1c-228">在 Lync Server 2013 中修改語音路由</span><span class="sxs-lookup"><span data-stu-id="faf1c-228">Modify a voice route in Lync Server 2013</span></span>](lync-server-2013-modify-a-voice-route.md)  
[<span data-ttu-id="faf1c-229">在 Lync Server 2013 中將擱置的變更發佈至語音路由設定</span><span class="sxs-lookup"><span data-stu-id="faf1c-229">Publish pending changes to the voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  
[<span data-ttu-id="faf1c-230">在 Lync Server 2013 中設定語音信箱轉義</span><span class="sxs-lookup"><span data-stu-id="faf1c-230">Configuring voice mail escape in Lync Server 2013</span></span>](lync-server-2013-configuring-voice-mail-escape.md)  


[<span data-ttu-id="faf1c-231">在 Lync Server 2013 中測試語音路由</span><span class="sxs-lookup"><span data-stu-id="faf1c-231">Test voice routing in Lync Server 2013</span></span>](lync-server-2013-test-voice-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

