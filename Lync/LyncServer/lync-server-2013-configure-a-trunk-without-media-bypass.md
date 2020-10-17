---
title: Lync Server 2013：設定無媒體旁路的主幹
description: Lync Server 2013：設定不含媒體旁路的主幹。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure a trunk without media bypass
ms:assetid: 3422e93e-7bd2-4470-968c-dc38345b18ca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425831(v=OCS.15)
ms:contentKeyID: 48183825
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 586ab4f283034c94bd7cb0179d73a963cad88347
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555959"
---
# <a name="configure-a-trunk-without-media-bypass-in-lync-server-2013"></a><span data-ttu-id="08962-103">在 Lync Server 2013 中設定無媒體旁路的主幹</span><span class="sxs-lookup"><span data-stu-id="08962-103">Configure a trunk without media bypass in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="08962-104">_**主題上次修改日期：** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="08962-104">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="08962-105">如果您想將主幹設定為停用媒體旁路，請遵循下列步驟。</span><span class="sxs-lookup"><span data-stu-id="08962-105">If you want to configure a trunk with media bypass disabled, follow these steps.</span></span> <span data-ttu-id="08962-106">如果您想要設定主幹以啟用媒體旁路，請參閱 [在 Lync Server 2013 中使用媒體旁路設定主幹](lync-server-2013-configure-a-trunk-with-media-bypass.md)。</span><span class="sxs-lookup"><span data-stu-id="08962-106">If you want to configure a trunk with media bypass enabled, see [Configure a trunk with media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md).</span></span>

<span data-ttu-id="08962-p102">如以下所述，主幹組態會將一組參數群組在一起，該組參數適用於指派此主幹組態的主幹。特定的主幹組態可涵蓋全域 (涵蓋至不具更明確網站或集區組態的所有主幹)，或涵蓋至網站或集區。集區層級組態是用於將明確主幹組態涵蓋至單一主幹。</span><span class="sxs-lookup"><span data-stu-id="08962-p102">A trunk configuration, as described below, groups a set of parameters that are applied to trunks assigned this trunk configuration. A particular trunk configuration can be scoped globally (to all trunks that do not have more specific site or pool configuration), or to a site, or to a pool. The pool-level trunk configuration is used to scope a specific trunk configuration to a single trunk.</span></span>

<span id="BKMK_ConfigTrunkGenericSteps"></span>

<div>

## <a name="to-configure-a-trunk-without-media-bypass"></a><span data-ttu-id="08962-110">設定沒有媒體旁路的主幹</span><span class="sxs-lookup"><span data-stu-id="08962-110">To configure a trunk without media bypass</span></span>

1.  <span data-ttu-id="08962-111">以 RTCUniversalServerAdmins 群組成員的身分，或是 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色的成員身分登入電腦。</span><span class="sxs-lookup"><span data-stu-id="08962-111">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="08962-112">如需詳細資訊，請參閱 [在 Lync Server 2013 中委派設定許可權](lync-server-2013-delegate-setup-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="08962-112">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="08962-113">開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="08962-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="08962-114">如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="08962-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="08962-115">在左導覽列中，按一下 **[語音路由]**，再按一下 **[主幹組態]**。</span><span class="sxs-lookup"><span data-stu-id="08962-115">In the left navigation bar, click **Voice Routing**, and then click **Trunk Configuration**.</span></span>

4.  <span data-ttu-id="08962-116">在 **[主幹組態]** 頁面上，使用下列其中一個方法設定主幹：</span><span class="sxs-lookup"><span data-stu-id="08962-116">On the **Trunk Configuration** page, use one of the following methods to configure a trunk:</span></span>
    
      - <span data-ttu-id="08962-117">按兩下現有主幹 (例如 **[通用]** 主幹)，顯示 **[編輯主幹組態]** 對話方塊。</span><span class="sxs-lookup"><span data-stu-id="08962-117">Double-click an existing trunk (for example, the **Global** trunk) to display the **Edit Trunk Configuration** dialog box.</span></span>
    
      - <span data-ttu-id="08962-118">按一下 **[新增]**，然後選取新主幹組態：</span><span class="sxs-lookup"><span data-stu-id="08962-118">Click **New**, and then select a scope for the new trunk configuration:</span></span>
        
          - <span data-ttu-id="08962-119">**網站主幹：** 在 [ **選取網站** ] 中選擇此主幹設定的網站，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="08962-119">**Site trunk:** Choose the site for this trunk configuration in **Select a Site** , and then click **OK**.</span></span> <span data-ttu-id="08962-120">請注意，如果已為某個網站建立主幹組態，則該網站不會出現在 **[選取站台]** 中。</span><span class="sxs-lookup"><span data-stu-id="08962-120">Note that if a trunk configuration has already been created for a site, the site does not appear in **Select a Site**.</span></span> <span data-ttu-id="08962-121">此主幹組態將套用至網站中的所有主幹。</span><span class="sxs-lookup"><span data-stu-id="08962-121">This trunk configuration will be applied to all trunks in the site.</span></span>
        
          - <span data-ttu-id="08962-122">**集區主幹：** 在 [ **選取服務** ] 中選擇此主幹設定所套用的主幹名稱，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="08962-122">**Pool trunk:** Choose the name of the trunk that this trunk configuration applies to in **Select a Service** and click **OK**.</span></span> <span data-ttu-id="08962-123">這個主幹可以是根主幹，或在拓撲產生器中定義的任何其他主幹。</span><span class="sxs-lookup"><span data-stu-id="08962-123">This trunk can be the root trunk, or any additional trunks defined in Topology Builder.</span></span> <span data-ttu-id="08962-124">請注意，如果已經針對特定主幹建立主幹組態，則該主幹就不會顯示在 **[選取服務]** 中。</span><span class="sxs-lookup"><span data-stu-id="08962-124">Note that if a trunk configuration has already been created for a specific trunk, the trunk does not appear in **Select a Service**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="08962-125">一旦選取主幹組態的範圍後，就無法變更。</span><span class="sxs-lookup"><span data-stu-id="08962-125">After you select the scope of the trunk configuration, it cannot be changed.</span></span><BR><span data-ttu-id="08962-126"><STRONG>[名稱]</STRONG> 欄位會預先填入主幹組態所關聯之網站或服務的名稱，此名稱無法變更。</span><span class="sxs-lookup"><span data-stu-id="08962-126">The <STRONG>Name</STRONG> field is prepopulated with the name of the trunk configuration’s associated site or service and cannot be changed.</span></span>

    
    </div>

5.  <span data-ttu-id="08962-127">選取下列其中一個 **[加密支援等級]** 選項：</span><span class="sxs-lookup"><span data-stu-id="08962-127">Select one of the following **Encryption support level** options:</span></span>
    
      - <span data-ttu-id="08962-128">**必要：** 安全即時傳輸通訊協定 (SRTP) 加密必須用來協助保護轉送伺服器和閘道或專用交換機 (PBX) 之間的流量。</span><span class="sxs-lookup"><span data-stu-id="08962-128">**Required:** Secure real-time transport protocol (SRTP) encryption must be used to help protect traffic between the Mediation Server and the gateway or private branch exchange (PBX).</span></span>
    
      - <span data-ttu-id="08962-129">**選用：** 如果服務提供者或設備製造商支援，就會使用 SRTP 加密。</span><span class="sxs-lookup"><span data-stu-id="08962-129">**Optional:** SRTP encryption will be used if the service provider or equipment manufacturer supports it.</span></span>
    
      - <span data-ttu-id="08962-130">**不支援：** SRTP 不支援服務提供者或設備製造商的加密，因此不會使用此加密。</span><span class="sxs-lookup"><span data-stu-id="08962-130">**Not Supported:** SRTP encryption is not supported by the service provider or equipment manufacturer and therefore will not be used.</span></span>

6.  <span data-ttu-id="08962-131">確定清除 **[啟用媒體旁路]** 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="08962-131">Be sure that the **Enable media bypass** check box is cleared.</span></span>

7.  <span data-ttu-id="08962-p107">如果有已知的媒體終端點 (例如公用交換電話網路 (PSTN) 閘道，因為媒體終端的 IP 與訊號終端相同)，則選取 **[集中式媒體處理]** 核取方塊。如果主幹沒有已知的媒體終端點，請清除此核取方塊。</span><span class="sxs-lookup"><span data-stu-id="08962-p107">Select the **Centralized media processing** check box if there is a well-known media termination point (for example, a public switched telephone network (PSTN) gateway where the media termination has the same IP as the signaling termination). Clear this check box if the trunk does not have a well-known media termination point.</span></span>

8.  <span data-ttu-id="08962-134">如果主幹對等支援從轉送伺服器接收 SIP 參考要求，請選取 [ **啟用傳送參照至閘道** ] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="08962-134">If the trunk peer supports receiving SIP REFER requests from the Mediation Server, select the **Enable sending refer to the gateway** check box.</span></span>

9.  <span data-ttu-id="08962-p108">(選用) 若要啟用主幹間的路由，請關聯至此主幹組態並設定其 PSTN 使用方式記錄。與此主幹組態相關聯的 PSTN 使用方式，將會套用至整個主幹中並非由 Lync 端點產生的所有來電。若要管理與主幹組態關聯的 PSTN 使用方式記錄，請使用下列其中一種方法：</span><span class="sxs-lookup"><span data-stu-id="08962-p108">(Optional) To enable inter-trunk routing, associate and configure PSTN usage records to this trunk configuration. The PSTN usages associated to this trunk configuration will be applied for all incoming calls through the trunk that is not originating from a Lync endpoint. To manage PSTN usage records associated to a trunk configuration, use one of the following methods:</span></span>
    
      - <span data-ttu-id="08962-138">若要從 Enterprise Voice 部署中所有可用的 PSTN 使用方式記錄清單中選取一或多筆記錄，請按一下 [ **選取**]。</span><span class="sxs-lookup"><span data-stu-id="08962-138">To select one or more records from a list of all PSTN usage records available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="08962-139">反白顯示您要與此主幹組態建立關聯的記錄，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="08962-139">Highlight the records you want to associate with this trunk configuration and then click **OK**.</span></span>
    
      - <span data-ttu-id="08962-140">若要從此主幹組態移除 PSTN 使用方式記錄，請選取該記錄然後按一下 **[移除]**。</span><span class="sxs-lookup"><span data-stu-id="08962-140">To remove a PSTN usage record from this trunk configuration, select the record and click **Remove**.</span></span>
    
      - <span data-ttu-id="08962-141">若要定義新的 PSTN 使用方式記錄，並建立與此主幹組態的關聯，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="08962-141">To define a new PSTN usage record and associate it with this trunk configuration, do the following:</span></span>
        
        1.  <span data-ttu-id="08962-142">按一下 **[新增]**。</span><span class="sxs-lookup"><span data-stu-id="08962-142">Click **New**.</span></span>
        
        2.  <span data-ttu-id="08962-143">在 **[名稱]** 欄位中，指定該記錄的唯一描述性名稱。</span><span class="sxs-lookup"><span data-stu-id="08962-143">In the **Name** field, specify a descriptive name for the record that is unique.</span></span>
            
            <div>
            

            > [!NOTE]  
            > <span data-ttu-id="08962-p110">PSTN 使用方式記錄名稱必須是 Enterprise Voice 部署內的唯一名稱。儲存記錄之後，就無法編輯 <STRONG>[名稱]</STRONG> 欄位。</span><span class="sxs-lookup"><span data-stu-id="08962-p110">The PSTN usage record name must be unique within the Enterprise Voice deployment. After the record is saved, the <STRONG>Name</STRONG> field cannot be edited.</span></span>

            
            </div>
        
        3.  <span data-ttu-id="08962-146">使用下列其中一種方法，關聯至此 PSTN 使用方式記錄並設定其路由：</span><span class="sxs-lookup"><span data-stu-id="08962-146">Use one of the following methods to associate and configure routes for this PSTN usage record:</span></span>
            
              - <span data-ttu-id="08962-147">若要從 Enterprise Voice 部署中所有可用路由的清單中選取一個或多個路由，請按一下 [ **選取**]。</span><span class="sxs-lookup"><span data-stu-id="08962-147">To select one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="08962-148">反白顯示您要與此 PSTN 使用方式記錄相關聯的路由，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="08962-148">Highlight the routes you want to associate with this PSTN usage record, and click **OK**.</span></span>
            
              - <span data-ttu-id="08962-149">若要從 PSTN 使用方式記錄移除路由，請選取該路由，然後按一下 **[移除]**。</span><span class="sxs-lookup"><span data-stu-id="08962-149">To remove a route from the PSTN usage record, select the route, and click **Remove**.</span></span>
            
              - <span data-ttu-id="08962-150">若要定義新路由，並將其關聯至此 PSTN 使用記錄，請按一下 **[新增]**。</span><span class="sxs-lookup"><span data-stu-id="08962-150">To define a new route and associate it to this PSTN usage record, click **New**.</span></span> <span data-ttu-id="08962-151">如需詳細資訊，請參閱 [Create a voice route In Lync Server 2013](lync-server-2013-create-a-voice-route.md)。</span><span class="sxs-lookup"><span data-stu-id="08962-151">For details, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>
            
              - <span data-ttu-id="08962-152">若要編輯與此 PSTN 使用方式記錄相關聯的路由，請選取該路由，然後按一下 **[顯示詳細資料]**。</span><span class="sxs-lookup"><span data-stu-id="08962-152">To edit a route that is associated with this PSTN usage record, select the route, and click **Show details**.</span></span> <span data-ttu-id="08962-153">如需詳細資訊，請參閱 [Modify a voice route In Lync Server 2013](lync-server-2013-modify-a-voice-route.md)。</span><span class="sxs-lookup"><span data-stu-id="08962-153">For details, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span></span>
        
        4.  <span data-ttu-id="08962-154">按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="08962-154">Click **OK**.</span></span>
    
      - <span data-ttu-id="08962-155">若要編輯已經與此主幹組態建立關聯的 PSTN 使用方式記錄，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="08962-155">To edit a PSTN usage record that is already associated with this trunk configuration, do the following:</span></span>
        
        1.  <span data-ttu-id="08962-156">選取您要編輯的 PSTN 使用方式記錄，然後按一下 **[顯示詳細資料]**。</span><span class="sxs-lookup"><span data-stu-id="08962-156">Select the PSTN usage record you want to edit, and click **Show details**.</span></span>
        
        2.  <span data-ttu-id="08962-157">使用下列其中一種方法，關聯至此 PSTN 使用方式記錄並設定其路由：</span><span class="sxs-lookup"><span data-stu-id="08962-157">Use one of the following methods to associate and configure routes for this PSTN usage record:</span></span>
            
              - <span data-ttu-id="08962-158">若要從 Enterprise Voice 部署中所有可用路由的清單中選取一個或多個路由，請按一下 [ **選取**]。</span><span class="sxs-lookup"><span data-stu-id="08962-158">To select one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="08962-159">反白顯示您要與此 PSTN 使用方式記錄相關聯的路由，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="08962-159">Highlight the routes you want to associate with this PSTN usage record, and click **OK**.</span></span>
            
              - <span data-ttu-id="08962-160">若要從 PSTN 使用方式記錄移除路由，請選取該路由，然後按一下 **[移除]**。</span><span class="sxs-lookup"><span data-stu-id="08962-160">To remove a route from the PSTN usage record, select the route, and click **Remove**.</span></span>
            
              - <span data-ttu-id="08962-161">若要定義新路由，並將其關聯至此 PSTN 使用記錄，請按一下 **[新增]**。</span><span class="sxs-lookup"><span data-stu-id="08962-161">To define a new route and associate it to this PSTN usage record, click **New**.</span></span> <span data-ttu-id="08962-162">如需詳細資訊，請參閱 [Create a voice route In Lync Server 2013](lync-server-2013-create-a-voice-route.md)。</span><span class="sxs-lookup"><span data-stu-id="08962-162">For details, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>
            
              - <span data-ttu-id="08962-163">若要編輯與此 PSTN 使用方式記錄相關聯的路由，請選取該路由，然後按一下 **[顯示詳細資料]**。</span><span class="sxs-lookup"><span data-stu-id="08962-163">To edit a route that is associated with this PSTN usage record, select the route, and click **Show details**.</span></span> <span data-ttu-id="08962-164">如需詳細資訊，請參閱 [Modify a voice route In Lync Server 2013](lync-server-2013-modify-a-voice-route.md)。</span><span class="sxs-lookup"><span data-stu-id="08962-164">For details, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span></span>
        
        3.  <span data-ttu-id="08962-165">按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="08962-165">Click **OK**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="08962-166">將 PSTN 使用方式記錄與所設定之主幹相關聯的轉送伺服器對等相關聯是很重要的。</span><span class="sxs-lookup"><span data-stu-id="08962-166">It important to associate PSTN usage records according to the Mediation Server peer that is associated to the trunk being configured.</span></span> <span data-ttu-id="08962-167">若轉送伺服器對等是 PSTN 閘道或會話邊界控制器 (SBC) ，強烈建議您不要將主幹設定相關聯至 PSTN 使用方式記錄，該記錄會路由傳送至 PSTN 目的地或透過 Lync Server 連接的任何其他下游系統。</span><span class="sxs-lookup"><span data-stu-id="08962-167">If the Mediation Server peer is a PSTN gateway or a Session Border Controller (SBC), it is strongly recommended that the trunk configuration is not associated to a PSTN usage record that routes to a PSTN destination or any other downstream systems connected via Lync Server.</span></span>

    
    </div>

10. <span data-ttu-id="08962-p118">請排列 PSTN 使用方式記錄以達到最佳效能。若要變更記錄在清單中的位置，請選取 PSTN 使用記錄，然後按一下向上或向下箭號。</span><span class="sxs-lookup"><span data-stu-id="08962-p118">Arrange the PSTN usage records for optimum performance. To change a record’s position in the list, select the PSTN usage record, and click the up or down arrows.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="08962-170">PSTN 使用方式記錄列示在主幹組態中的順序非常重要。</span><span class="sxs-lookup"><span data-stu-id="08962-170">The order in which PSTN usage records are listed in the trunk configuration is significant.</span></span> <span data-ttu-id="08962-171">Lync Server 從上到上，從上到上的遍歷清單。</span><span class="sxs-lookup"><span data-stu-id="08962-171">Lync Server traverses the list from top to down.</span></span>

    
    </div>

11. <span data-ttu-id="08962-172">您應該選取 **[啟用 RTP 栓]** 才能啟用位於 NAT 或防火牆後方的用戶端旁路媒體，以及支援栓的 SBC。</span><span class="sxs-lookup"><span data-stu-id="08962-172">**Enable RTP Latching** should be selected to enable bypass media for clients behind a NAT or firewall and an SBC that supports latching.</span></span>

12. <span data-ttu-id="08962-173">應該選取 [**啟用轉接來電記錄**]，以啟用將通話記錄資訊傳送至轉送伺服器的閘道對等功能。</span><span class="sxs-lookup"><span data-stu-id="08962-173">**Enable forward call history** should be selected to enable sending of call history information to the gateway peer of the Mediation Server.</span></span>

13. <span data-ttu-id="08962-174">[**啟用轉寄 P-Asserted-Identity 資料**] 選取此選項，即可啟用 PAI 呼叫發起者資訊，以便在轉送伺服器端與閘道端 (之間轉送，反之亦然) （如有）。</span><span class="sxs-lookup"><span data-stu-id="08962-174">**Enable forward P-Asserted-Identity data** should be selected to enable PAI call originator information to be forwarded between the Mediation Server side and gateway side (and vice versa), when present.</span></span>

14. <span data-ttu-id="08962-175">您應選取 **[啟用輸出路由容錯移轉計時器]** 才能啟用快速容錯移轉。</span><span class="sxs-lookup"><span data-stu-id="08962-175">**Enable outbound routing failover timer** should be selected to enable fast failover.</span></span> <span data-ttu-id="08962-176">由於與此主幹相關聯的閘道正在處理撥出電話，所以可以在 10 秒內發出通知。</span><span class="sxs-lookup"><span data-stu-id="08962-176">The gateway associated with this trunk can give notification within 10 seconds that it is processing an outbound call.</span></span> <span data-ttu-id="08962-177">若轉送伺服器未收到此通知，則會進行重新路由至另一個主幹。</span><span class="sxs-lookup"><span data-stu-id="08962-177">Rerouting to another trunk will occur if this notification is not received by the Mediation Server.</span></span> <span data-ttu-id="08962-178">在延遲可能遞延回應時間的網路上或是閘道回應時間在 10 秒以上者，應停用快速容錯移轉。</span><span class="sxs-lookup"><span data-stu-id="08962-178">On networks where latency may delay the response time or the gateway takes longer than 10 seconds to respond, the fast failover should be disabled.</span></span>

15. <span data-ttu-id="08962-179">(選用) 建立與主幹的關聯並設定其 **[撥號轉譯規則]**。</span><span class="sxs-lookup"><span data-stu-id="08962-179">(Optional) Associate and configure **calling number translation rules** for the trunk.</span></span> <span data-ttu-id="08962-180">這些轉譯規則適用於撥出電話的撥打號碼</span><span class="sxs-lookup"><span data-stu-id="08962-180">These translation rules apply to the calling number for outbound calls</span></span>
    
      - <span data-ttu-id="08962-181">若要從 Enterprise Voice 部署中所有可用轉譯規則的清單中選擇一個或多個規則，請按一下 [ **選取**]。</span><span class="sxs-lookup"><span data-stu-id="08962-181">To choose one or more rules from a list of all translation rules that are available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="08962-182">在 **[選取轉譯規則]** 中，按一下您要建立關聯的主幹，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="08962-182">In **Select Translation Rules**, click the rules that you want to associate with the trunk, and then click **OK**.</span></span>
    
      - <span data-ttu-id="08962-183">若要定義新的轉譯規則並建立其與主幹的關聯，請按一下 **[新增]**。</span><span class="sxs-lookup"><span data-stu-id="08962-183">To define a new translation rule and associate it with the trunk, click **New**.</span></span> <span data-ttu-id="08962-184">如需定義新規則的詳細資訊，請參閱部署檔中的在 [Lync Server 2013 中定義轉譯規則](lync-server-2013-defining-translation-rules.md) 。</span><span class="sxs-lookup"><span data-stu-id="08962-184">For details about defining a new rule, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="08962-185">若要編輯已與主幹建立關聯的轉譯規則，按一下規則名稱，然後按一下 **[顯示詳細資料]**。</span><span class="sxs-lookup"><span data-stu-id="08962-185">To edit a translation rule that is already associated with the trunk, click the rule name, and then click **Show details**.</span></span> <span data-ttu-id="08962-186">如需詳細資訊，請參閱部署檔中的在 [Lync Server 2013 中定義轉譯規則](lync-server-2013-defining-translation-rules.md) 。</span><span class="sxs-lookup"><span data-stu-id="08962-186">For details, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="08962-187">若要複製現有轉譯規則，以用來作為定義新規則時的起點，請按一下規則名稱，再按一下 **[複製]**，然後按一下 **[貼上]**。</span><span class="sxs-lookup"><span data-stu-id="08962-187">To copy an existing translation rule to use as a starting point for defining a new rule, click the rule name and click **Copy**, and then click **Paste**.</span></span> <span data-ttu-id="08962-188">如需詳細資訊，請參閱 [在 Lync Server 2013 中定義轉譯規則](lync-server-2013-defining-translation-rules.md)。</span><span class="sxs-lookup"><span data-stu-id="08962-188">For details, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md).</span></span>
    
      - <span data-ttu-id="08962-189">若要從主幹移除轉譯規則，請反白顯示該規則名稱並按一下 **[移除]**。</span><span class="sxs-lookup"><span data-stu-id="08962-189">To remove a translation rule from the trunk, highlight the rule name and click **Remove**.</span></span>
    
    <div>
    
    <table>
    <thead>
    <tr class="header">
    <th><img src="images/Gg398321.security(OCS.15).gif" title="安全" alt="security" /><span data-ttu-id="08962-191">安全性附注：</span><span class="sxs-lookup"><span data-stu-id="08962-191">Security Note:</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><span data-ttu-id="08962-192">如果您已在關聯的主幹對等上設定轉譯規則，請勿再將轉譯規則與主幹建立關聯，因為這兩個規則可能會產生衝突。</span><span class="sxs-lookup"><span data-stu-id="08962-192">Do not associate translation rules with a trunk if you have configured translation rules on the associated trunk peer, because the two rules might conflict.</span></span></td>
    </tr>
    </tbody>
    </table>
    
    </div>

16. <span data-ttu-id="08962-p126">(選用) 建立與主幹的關聯並設定其 **[撥號轉譯規則]**。這些轉譯規則適用於撥出電話的撥打號碼。</span><span class="sxs-lookup"><span data-stu-id="08962-p126">(Optional) Associate and configure **called number translation rules** for the trunk. The translation rules apply to the called number in an outbound call.</span></span>
    
      - <span data-ttu-id="08962-195">若要從 Enterprise Voice 部署中所有可用轉譯規則的清單中選擇一個或多個規則，請按一下 [ **選取**]。</span><span class="sxs-lookup"><span data-stu-id="08962-195">To choose one or more rules from a list of all translation rules that are available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="08962-196">在 **[選取轉譯規則]** 中，按一下您要建立關聯的主幹，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="08962-196">In **Select Translation Rules**, click the rules that you want to associate with the trunk, and then click **OK**.</span></span>
    
      - <span data-ttu-id="08962-197">若要定義新的轉譯規則並建立其與主幹的關聯，請按一下 **[新增]**。</span><span class="sxs-lookup"><span data-stu-id="08962-197">To define a new translation rule and associate it with the trunk, click **New**.</span></span> <span data-ttu-id="08962-198">如需定義新規則的詳細資訊，請參閱部署檔中的在 [Lync Server 2013 中定義轉譯規則](lync-server-2013-defining-translation-rules.md) 。</span><span class="sxs-lookup"><span data-stu-id="08962-198">For details about defining a new rule, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="08962-199">若要編輯已與主幹建立關聯的轉譯規則，按一下規則名稱，然後按一下 **[顯示詳細資料]**。</span><span class="sxs-lookup"><span data-stu-id="08962-199">To edit a translation rule that is already associated with the trunk, click the rule name, and then click **Show details**.</span></span> <span data-ttu-id="08962-200">如需詳細資訊，請參閱部署檔中的在 [Lync Server 2013 中定義轉譯規則](lync-server-2013-defining-translation-rules.md) 。</span><span class="sxs-lookup"><span data-stu-id="08962-200">For details, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="08962-201">若要複製現有轉譯規則，以用來作為定義新規則時的起點，請按一下規則名稱，再按一下 **[複製]**，然後按一下 **[貼上]**。</span><span class="sxs-lookup"><span data-stu-id="08962-201">To copy an existing translation rule to use as a starting point for defining a new rule, click the rule name and click **Copy**, and then click **Paste**.</span></span> <span data-ttu-id="08962-202">如需詳細資訊，請參閱 [在 Lync Server 2013 中定義轉譯規則](lync-server-2013-defining-translation-rules.md)。</span><span class="sxs-lookup"><span data-stu-id="08962-202">For details, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md).</span></span>
    
      - <span data-ttu-id="08962-203">若要從主幹移除轉譯規則，請反白顯示該規則名稱並按一下 **[移除]**。</span><span class="sxs-lookup"><span data-stu-id="08962-203">To remove a translation rule from the trunk, highlight the rule name and click **Remove**.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="08962-204">如果您已在相關聯的主幹對等上設定轉譯規則，則請勿將轉譯規則與主幹建立關聯，因為兩種規則可能會衝突。</span><span class="sxs-lookup"><span data-stu-id="08962-204">Do not associate translation rules with a trunk if you have configured translation rules on the associated trunk peer, because the two rules might conflict.</span></span>

    
    </div>

17. <span data-ttu-id="08962-205">請確定主幹的轉譯規則依正確的順序排列。</span><span class="sxs-lookup"><span data-stu-id="08962-205">Make sure that the trunk’s translation rules are arranged in the correct order.</span></span> <span data-ttu-id="08962-206">若要變更規則在清單中的位置，請反白規則名稱，然後按向上或向下箭頭。</span><span class="sxs-lookup"><span data-stu-id="08962-206">To change a rule’s position in the list, highlight the rule name, and then click the up or down arrow.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="08962-207">Lync Server 會從左上部開始轉譯轉譯規則清單，並使用符合撥號號碼的第一個規則。</span><span class="sxs-lookup"><span data-stu-id="08962-207">Lync Server traverses the translation rule list from the top down and uses the first rule that matches the dialed number.</span></span> <span data-ttu-id="08962-208">如果您設定的主幹會使撥號號碼符合不只一個轉譯規則，請確定限制較多的規則排在限制較少的規則上方。</span><span class="sxs-lookup"><span data-stu-id="08962-208">If you configure a trunk so that a dialed number can match more than one translation rule, be sure that the more restrictive rules are sorted above the less restrictive rules.</span></span> <span data-ttu-id="08962-209">例如，如果您包含的轉譯規則中有一個規則符合所有 11 位數號碼，另有一個轉譯規則僅符合開頭為 +1425 的 11 位數號碼，則請確定符合所有 11 位數號碼的規則排在另一個限制較多規則的<EM>下方</EM>。</span><span class="sxs-lookup"><span data-stu-id="08962-209">For example, if you have included a translation rule that matches any 11-digit number and a translation rule that matches only 11-digit numbers that start with +1425, be sure that the rule that matches any 11-digit number is sorted <EM>below</EM> the more restrictive rule.</span></span>

    
    </div>

18. <span data-ttu-id="08962-210">完成主幹的設定時，請按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="08962-210">When you are finished configuring the trunk, click **OK**.</span></span>

19. <span data-ttu-id="08962-211">在 **[主幹組態]** 頁面上，按一下 **[認可]**，再按一下 **[全部認可]**。</span><span class="sxs-lookup"><span data-stu-id="08962-211">On the **Trunk Configuration** page, click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="08962-212">只要建立或修改主幹組態後，都應執行 <STRONG>[全部認可]</STRONG> 命令以發行組態變更。</span><span class="sxs-lookup"><span data-stu-id="08962-212">Whenever you create or modify a trunk configuration, you must run the <STRONG>Commit all</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="08962-213">如需詳細資訊，請參閱 Operations 檔中的在 <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Lync Server 2013 中發佈擱置的變更至語音路由</A> 設定。</span><span class="sxs-lookup"><span data-stu-id="08962-213">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="08962-214">另請參閱</span><span class="sxs-lookup"><span data-stu-id="08962-214">See Also</span></span>


[<span data-ttu-id="08962-215">在 Lync Server 2013 中設定含媒體旁路的主幹</span><span class="sxs-lookup"><span data-stu-id="08962-215">Configure a trunk with media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-with-media-bypass.md)  


[<span data-ttu-id="08962-216">在 Lync Server 2013 中定義轉譯規則</span><span class="sxs-lookup"><span data-stu-id="08962-216">Defining translation rules in Lync Server 2013</span></span>](lync-server-2013-defining-translation-rules.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

