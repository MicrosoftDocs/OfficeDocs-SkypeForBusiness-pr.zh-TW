---
title: 在商務用 Skype Server 中設定無媒體旁路的主幹
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 3422e93e-7bd2-4470-968c-dc38345b18ca
description: 摘要：設定不啟用商務用 Skype 伺服器的媒體旁路的主幹。
ms.openlocfilehash: ff1c34e36906c8b9f5c88495e3c24239f572184a
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51106379"
---
# <a name="configure-a-trunk-without-media-bypass-in-skype-for-business-server"></a><span data-ttu-id="027ad-103">在商務用 Skype Server 中設定無媒體旁路的主幹</span><span class="sxs-lookup"><span data-stu-id="027ad-103">Configure a trunk without media bypass in Skype for Business Server</span></span>

<span data-ttu-id="027ad-104">**摘要：** 設定不啟用商務用 Skype 伺服器的媒體旁路的主幹。</span><span class="sxs-lookup"><span data-stu-id="027ad-104">**Summary:** Configure a trunk without media bypass enabled for Skype for Business Server.</span></span>

<span data-ttu-id="027ad-105">如果您想將主幹設定為停用媒體旁路，請遵循下列步驟。</span><span class="sxs-lookup"><span data-stu-id="027ad-105">If you want to configure a trunk with media bypass disabled, follow these steps.</span></span> <span data-ttu-id="027ad-106">如果您想要設定具有媒體旁路功能的主幹，請參閱 [在商務用 Skype Server 中設定具有媒體旁路的主幹](configure-trunk-with-media-bypass.md)。</span><span class="sxs-lookup"><span data-stu-id="027ad-106">If you want to configure a trunk with media bypass enabled, see [Configure a trunk with media bypass in Skype for Business Server](configure-trunk-with-media-bypass.md).</span></span>

<span data-ttu-id="027ad-p102">如以下所述，主幹組態會將一組參數群組在一起，該組參數適用於指派此主幹組態的主幹。特定的主幹組態可涵蓋全域 (涵蓋至不具更明確網站或集區組態的所有主幹)，或涵蓋至網站或集區。集區層級組態是用於將明確主幹組態涵蓋至單一主幹。</span><span class="sxs-lookup"><span data-stu-id="027ad-p102">A trunk configuration, as described below, groups a set of parameters that are applied to trunks assigned this trunk configuration. A particular trunk configuration can be scoped globally (to all trunks that do not have more specific site or pool configuration), or to a site, or to a pool. The pool-level trunk configuration is used to scope a specific trunk configuration to a single trunk.</span></span>

### <a name="to-configure-a-trunk-without-media-bypass"></a><span data-ttu-id="027ad-110">設定沒有媒體旁路的主幹</span><span class="sxs-lookup"><span data-stu-id="027ad-110">To configure a trunk without media bypass</span></span>

1. <span data-ttu-id="027ad-111">開啟商務用 Skype Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="027ad-111">Open Skype for Business Server Control Panel.</span></span>

2. <span data-ttu-id="027ad-112">在左導覽列中，按一下 **[語音路由]**，再按一下 **[主幹組態]**。</span><span class="sxs-lookup"><span data-stu-id="027ad-112">In the left navigation bar, click **Voice Routing**, and then click **Trunk Configuration**.</span></span>

3. <span data-ttu-id="027ad-113">在 **[主幹組態]** 頁面上，使用下列其中一個方法設定主幹：</span><span class="sxs-lookup"><span data-stu-id="027ad-113">On the **Trunk Configuration** page, use one of the following methods to configure a trunk:</span></span>

   - <span data-ttu-id="027ad-114">按兩下現有主幹 (例如 **[通用]** 主幹)，顯示 **[編輯主幹組態]** 對話方塊。</span><span class="sxs-lookup"><span data-stu-id="027ad-114">Double-click an existing trunk (for example, the **Global** trunk) to display the **Edit Trunk Configuration** dialog box.</span></span>

   - <span data-ttu-id="027ad-115">按一下 **[新增]**，然後選取新主幹組態：</span><span class="sxs-lookup"><span data-stu-id="027ad-115">Click **New**, and then select a scope for the new trunk configuration:</span></span>

   - <span data-ttu-id="027ad-116">**網站主幹**：在 [ **選取網站**] 中選擇此主幹設定的網站，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="027ad-116">**Site trunk**: Choose the site for this trunk configuration in **Select a Site**, and then click **OK**.</span></span> <span data-ttu-id="027ad-117">請注意，如果已為某個網站建立主幹組態，則該網站不會出現在 **[選取站台]** 中。</span><span class="sxs-lookup"><span data-stu-id="027ad-117">Note that if a trunk configuration has already been created for a site, the site does not appear in **Select a Site**.</span></span> <span data-ttu-id="027ad-118">此主幹組態將套用至網站中的所有主幹。</span><span class="sxs-lookup"><span data-stu-id="027ad-118">This trunk configuration will be applied to all trunks in the site.</span></span>

   - <span data-ttu-id="027ad-119">**集區主幹**：在 **[選取服務]** 中選擇此主幹組態適用的主幹名稱，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="027ad-119">**Pool trunk**: Choose the name of the trunk that this trunk configuration applies to in **Select a Service** and click **OK**.</span></span> <span data-ttu-id="027ad-120">這個主幹可以是根主幹，或在拓撲產生器中定義的任何其他主幹。</span><span class="sxs-lookup"><span data-stu-id="027ad-120">This trunk can be the root trunk, or any additional trunks defined in Topology Builder.</span></span> <span data-ttu-id="027ad-121">請注意，如果已經針對特定主幹建立主幹組態，則該主幹就不會顯示在 **[選取服務]** 中。</span><span class="sxs-lookup"><span data-stu-id="027ad-121">Note that if a trunk configuration has already been created for a specific trunk, the trunk does not appear in **Select a Service**.</span></span>

     > [!NOTE]
     > <span data-ttu-id="027ad-122">一旦選取主幹組態的範圍後，就無法變更。</span><span class="sxs-lookup"><span data-stu-id="027ad-122">After you select the scope of the trunk configuration, it cannot be changed.</span></span> <span data-ttu-id="027ad-123">> [ **名稱** ] 欄位會預先填入主幹設定之相關網站或服務的名稱，而且無法變更。</span><span class="sxs-lookup"><span data-stu-id="027ad-123">> The **Name** field is pre-populated with the name of the trunk configuration's associated site or service and cannot be changed.</span></span>

4. <span data-ttu-id="027ad-124">選取下列其中一個 **[加密支援等級]** 選項：</span><span class="sxs-lookup"><span data-stu-id="027ad-124">Select one of the following **Encryption support level** options:</span></span>

   - <span data-ttu-id="027ad-125">**必要**：安全即時傳輸通訊協定 (SRTP) 加密必須用來協助保護轉送伺服器和閘道或專用交換機 (PBX) 之間的流量。</span><span class="sxs-lookup"><span data-stu-id="027ad-125">**Required**: Secure Realtime Transport Protocol (SRTP) encryption must be used to help protect traffic between the Mediation Server and the gateway or Private Branch eXchange (PBX).</span></span>

   - <span data-ttu-id="027ad-126">**選用**：如果服務提供者或設備製造商支援 SRTP，則使用 SRTP 加密。</span><span class="sxs-lookup"><span data-stu-id="027ad-126">**Optional**: SRTP encryption will be used if the service provider or equipment manufacturer supports it.</span></span>

   - <span data-ttu-id="027ad-127">**不支援**：服務提供者或設備製造商不支援 SRTP 加密，因此不使用 SRTP 加密。</span><span class="sxs-lookup"><span data-stu-id="027ad-127">**Not Supported**: SRTP encryption is not supported by the service provider or equipment manufacturer and therefore will not be used.</span></span>

5. <span data-ttu-id="027ad-128">確定清除 **[啟用媒體旁路]** 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="027ad-128">Be sure that the **Enable media bypass** check box is cleared.</span></span>

6. <span data-ttu-id="027ad-129">如果有已知的媒體終端 (點，請選取 **集中式媒體處理** 核取方塊。例如，一部公用交換電話網路 (PSTN) 閘道，其媒體終端與「終止」) 的 IP 位址相同。</span><span class="sxs-lookup"><span data-stu-id="027ad-129">Select the **Centralized media processing** check box if there is a well-known media termination point (for example, a Public Switched Telephone Network (PSTN) gateway where the media termination has the same IP as the signaling termination).</span></span> <span data-ttu-id="027ad-130">如果主幹沒有已知的媒體終端點，請清除此核取方塊。</span><span class="sxs-lookup"><span data-stu-id="027ad-130">Clear this check box if the trunk does not have a well-known media termination point.</span></span>

7. <span data-ttu-id="027ad-131">如果主幹對等支援從轉送伺服器接收 SIP 參考要求，請選取 [ **啟用傳送參照至閘道** ] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="027ad-131">If the trunk peer supports receiving SIP REFER requests from the Mediation Server, select the **Enable sending refer to the gateway** check box.</span></span>

8. <span data-ttu-id="027ad-132">(選用) 若要啟用主幹間的路由，請關聯至此主幹組態並設定其 PSTN 使用方式記錄。</span><span class="sxs-lookup"><span data-stu-id="027ad-132">(Optional) To enable inter-trunk routing, associate and configure PSTN usage records to this trunk configuration.</span></span> <span data-ttu-id="027ad-133">與此主幹設定相關聯的 PSTN 使用方式，會透過主幹（並非來自商務用 Skype 伺服器端點）進行所有來電的應用程式。</span><span class="sxs-lookup"><span data-stu-id="027ad-133">The PSTN usages associated to this trunk configuration will be applied for all incoming calls through the trunk that is not originating from a Skype for Business Server endpoint.</span></span> <span data-ttu-id="027ad-134">若要管理與主幹組態關聯的 PSTN 使用方式記錄，請使用下列其中一種方法：</span><span class="sxs-lookup"><span data-stu-id="027ad-134">To manage PSTN usage records associated to a trunk configuration, use one of the following methods:</span></span>

   - <span data-ttu-id="027ad-135">若要從 Enterprise Voice 部署中所有可用的 PSTN 使用方式記錄清單中選取一或多筆記錄，請按一下 [ **選取**]。</span><span class="sxs-lookup"><span data-stu-id="027ad-135">To select one or more records from a list of all PSTN usage records available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="027ad-136">反白顯示您要與此主幹組態建立關聯的記錄，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="027ad-136">Highlight the records you want to associate with this trunk configuration and then click **OK**.</span></span>

   - <span data-ttu-id="027ad-137">若要從此主幹組態移除 PSTN 使用方式記錄，請選取該記錄然後按一下 **[移除]**。</span><span class="sxs-lookup"><span data-stu-id="027ad-137">To remove a PSTN usage record from this trunk configuration, select the record and click **Remove**.</span></span>

   - <span data-ttu-id="027ad-138">若要定義新的 PSTN 使用方式記錄，並建立與此主幹組態的關聯，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="027ad-138">To define a new PSTN usage record and associate it with this trunk configuration, do the following:</span></span>

     <span data-ttu-id="027ad-139">a.</span><span class="sxs-lookup"><span data-stu-id="027ad-139">a.</span></span> <span data-ttu-id="027ad-140">按一下 [ **新增**]。</span><span class="sxs-lookup"><span data-stu-id="027ad-140">Click **New**.</span></span>

     <span data-ttu-id="027ad-141">b.</span><span class="sxs-lookup"><span data-stu-id="027ad-141">b.</span></span> <span data-ttu-id="027ad-142">在 **[名稱]** 欄位中，指定該記錄的唯一描述性名稱。</span><span class="sxs-lookup"><span data-stu-id="027ad-142">In the **Name** field, specify a descriptive name for the record that is unique.</span></span>

     > [!NOTE]
     > <span data-ttu-id="027ad-p111">PSTN 使用方式記錄名稱必須是 Enterprise Voice 部署內的唯一名稱。儲存記錄之後，就無法編輯 **[名稱]** 欄位。</span><span class="sxs-lookup"><span data-stu-id="027ad-p111">The PSTN usage record name must be unique within the Enterprise Voice deployment. After the record is saved, the **Name** field cannot be edited.</span></span>

     <span data-ttu-id="027ad-145">c.</span><span class="sxs-lookup"><span data-stu-id="027ad-145">c.</span></span> <span data-ttu-id="027ad-146">使用下列其中一種方法，關聯至此 PSTN 使用方式記錄並設定其路由：</span><span class="sxs-lookup"><span data-stu-id="027ad-146">Use one of the following methods to associate and configure routes for this PSTN usage record:</span></span>

     - <span data-ttu-id="027ad-147">若要從 Enterprise Voice 部署中所有可用路由的清單中選取一個或多個路由，請按一下 [ **選取**]。</span><span class="sxs-lookup"><span data-stu-id="027ad-147">To select one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="027ad-148">反白顯示您要與此 PSTN 使用方式記錄相關聯的路由，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="027ad-148">Highlight the routes you want to associate with this PSTN usage record, and click **OK**.</span></span>

     - <span data-ttu-id="027ad-149">若要從 PSTN 使用方式記錄移除路由，請選取該路由，然後按一下 **[移除]**。</span><span class="sxs-lookup"><span data-stu-id="027ad-149">To remove a route from the PSTN usage record, select the route, and click **Remove**.</span></span>

     - <span data-ttu-id="027ad-150">若要定義新路由，並將其關聯至此 PSTN 使用記錄，請按一下 **[新增]**。</span><span class="sxs-lookup"><span data-stu-id="027ad-150">To define a new route and associate it to this PSTN usage record, click **New**.</span></span> <span data-ttu-id="027ad-151">如需詳細資訊，請參閱 [Create or modify voice route In 商務用 Skype](create-or-modify-a-voice-route.md)。</span><span class="sxs-lookup"><span data-stu-id="027ad-151">For details, see [Create or modify a voice route in Skype for Business](create-or-modify-a-voice-route.md).</span></span>

     - <span data-ttu-id="027ad-152">若要編輯與此 PSTN 使用方式記錄相關聯的路由，請選取該路由，然後按一下 **[顯示詳細資料]**。</span><span class="sxs-lookup"><span data-stu-id="027ad-152">To edit a route that is associated with this PSTN usage record, select the route, and click **Show details**.</span></span>

     <span data-ttu-id="027ad-153">d.</span><span class="sxs-lookup"><span data-stu-id="027ad-153">d.</span></span> <span data-ttu-id="027ad-154">按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="027ad-154">Click **OK**.</span></span>

   - <span data-ttu-id="027ad-155">若要編輯已經與此主幹組態建立關聯的 PSTN 使用方式記錄，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="027ad-155">To edit a PSTN usage record that is already associated with this trunk configuration, do the following:</span></span>

     <span data-ttu-id="027ad-156">a.</span><span class="sxs-lookup"><span data-stu-id="027ad-156">a.</span></span> <span data-ttu-id="027ad-157">選取您要編輯的 PSTN 使用方式記錄，然後按一下 **[顯示詳細資料]**。</span><span class="sxs-lookup"><span data-stu-id="027ad-157">Select the PSTN usage record you want to edit, and click **Show details**.</span></span>

     <span data-ttu-id="027ad-158">b.</span><span class="sxs-lookup"><span data-stu-id="027ad-158">b.</span></span> <span data-ttu-id="027ad-159">使用下列其中一種方法，關聯至此 PSTN 使用方式記錄並設定其路由：</span><span class="sxs-lookup"><span data-stu-id="027ad-159">Use one of the following methods to associate and configure routes for this PSTN usage record:</span></span>

     - <span data-ttu-id="027ad-160">若要從 Enterprise Voice 部署中所有可用路由的清單中選取一個或多個路由，請按一下 [ **選取**]。</span><span class="sxs-lookup"><span data-stu-id="027ad-160">To select one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="027ad-161">反白顯示您要與此 PSTN 使用方式記錄相關聯的路由，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="027ad-161">Highlight the routes you want to associate with this PSTN usage record, and click **OK**.</span></span>

     - <span data-ttu-id="027ad-162">若要從 PSTN 使用方式記錄移除路由，請選取該路由，然後按一下 **[移除]**。</span><span class="sxs-lookup"><span data-stu-id="027ad-162">To remove a route from the PSTN usage record, select the route, and click **Remove**.</span></span>

     - <span data-ttu-id="027ad-163">若要定義新路由，並將其關聯至此 PSTN 使用記錄，請按一下 **[新增]**。</span><span class="sxs-lookup"><span data-stu-id="027ad-163">To define a new route and associate it to this PSTN usage record, click **New**.</span></span> <span data-ttu-id="027ad-164">如需詳細資訊，請參閱 [Create or modify voice route In 商務用 Skype](create-or-modify-a-voice-route.md)。</span><span class="sxs-lookup"><span data-stu-id="027ad-164">For details, see [Create or modify a voice route in Skype for Business](create-or-modify-a-voice-route.md).</span></span>

     - <span data-ttu-id="027ad-165">若要編輯與此 PSTN 使用方式記錄相關聯的路由，請選取該路由，然後按一下 **[顯示詳細資料]**。</span><span class="sxs-lookup"><span data-stu-id="027ad-165">To edit a route that is associated with this PSTN usage record, select the route, and click **Show details**.</span></span>

     <span data-ttu-id="027ad-166">c.</span><span class="sxs-lookup"><span data-stu-id="027ad-166">c.</span></span> <span data-ttu-id="027ad-167">按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="027ad-167">Click **OK**.</span></span>

     > [!IMPORTANT]
     > <span data-ttu-id="027ad-168">請務必將 PSTN 使用方式記錄與所設定之主幹相關聯的轉送伺服器對等相關聯。</span><span class="sxs-lookup"><span data-stu-id="027ad-168">It is important to associate PSTN usage records according to the Mediation Server peer that is associated to the trunk being configured.</span></span> <span data-ttu-id="027ad-169">若轉送伺服器對等是 PSTN 閘道或會話邊界控制器 (SBC) ，強烈建議您不要將主幹設定相關聯至 pstn 使用方式記錄，該記錄會路由傳送至 PSTN 目的地或透過商務用 Skype Server 所連接的任何其他下游系統。</span><span class="sxs-lookup"><span data-stu-id="027ad-169">If the Mediation Server peer is a PSTN gateway or a Session Border Controller (SBC), it is strongly recommended that the trunk configuration is not associated to a PSTN usage record that routes to a PSTN destination or any other downstream systems connected via Skype for Business Server.</span></span>

9. <span data-ttu-id="027ad-170">排列 PSTN 使用方式記錄，以獲得最佳效能。</span><span class="sxs-lookup"><span data-stu-id="027ad-170">Arrange the PSTN usage records for optimum performance.</span></span> <span data-ttu-id="027ad-171">若要變更記錄在清單中的位置，請選取 PSTN 使用方式記錄，然後按一下向上或向下箭號。</span><span class="sxs-lookup"><span data-stu-id="027ad-171">To change a record's position in the list, select the PSTN usage record, and click the up or down arrows.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="027ad-172">PSTN 使用方式記錄列示在主幹組態中的順序非常重要。</span><span class="sxs-lookup"><span data-stu-id="027ad-172">The order in which PSTN usage records are listed in the trunk configuration is significant.</span></span> <span data-ttu-id="027ad-173">商務用 Skype 伺服器從上到上，從上到上來遍歷清單。</span><span class="sxs-lookup"><span data-stu-id="027ad-173">Skype for Business Server traverses the list from top to down.</span></span>

10. <span data-ttu-id="027ad-174">您應該選取 **[啟用 RTP 栓]** 才能啟用位於 NAT 或防火牆後方的用戶端旁路媒體，以及支援栓的 SBC。</span><span class="sxs-lookup"><span data-stu-id="027ad-174">**Enable RTP Latching** should be selected to enable bypass media for clients behind a NAT or firewall and an SBC that supports latching.</span></span>

11. <span data-ttu-id="027ad-175">應該選取 [**啟用轉接來電記錄**]，以啟用將通話記錄資訊傳送至轉送伺服器的閘道對等功能。</span><span class="sxs-lookup"><span data-stu-id="027ad-175">**Enable forward call history** should be selected to enable sending of call history information to the gateway peer of the Mediation Server.</span></span>

12. <span data-ttu-id="027ad-176">[**啟用轉寄 P-Asserted-Identity 資料**] 選取此選項，即可啟用 PAI 呼叫發起者資訊，以便在轉送伺服器端與閘道端 (之間轉送，反之亦然) （如有）。</span><span class="sxs-lookup"><span data-stu-id="027ad-176">**Enable forward P-Asserted-Identity data** should be selected to enable PAI call originator information to be forwarded between the Mediation Server side and gateway side (and vice versa), when present.</span></span>

13. <span data-ttu-id="027ad-177">您應選取 **[啟用輸出路由容錯移轉計時器]** 才能啟用快速容錯移轉。</span><span class="sxs-lookup"><span data-stu-id="027ad-177">**Enable outbound routing failover timer** should be selected to enable fast failover.</span></span> <span data-ttu-id="027ad-178">由於與此主幹相關聯的閘道正在處理撥出電話，所以可以在 10 秒內發出通知。</span><span class="sxs-lookup"><span data-stu-id="027ad-178">The gateway associated with this trunk can give notification within 10 seconds that it is processing an outbound call.</span></span> <span data-ttu-id="027ad-179">若轉送伺服器未收到此通知，則會進行重新路由至另一個主幹。</span><span class="sxs-lookup"><span data-stu-id="027ad-179">Rerouting to another trunk will occur if this notification is not received by the Mediation Server.</span></span> <span data-ttu-id="027ad-180">在延遲可能遞延回應時間的網路上或是閘道回應時間在 10 秒以上者，應停用快速容錯移轉。</span><span class="sxs-lookup"><span data-stu-id="027ad-180">On networks where latency may delay the response time or the gateway takes longer than 10 seconds to respond, the fast failover should be disabled.</span></span>

14. <span data-ttu-id="027ad-181">(選用) 建立與主幹的關聯並設定其 **[撥號轉譯規則]**。</span><span class="sxs-lookup"><span data-stu-id="027ad-181">(Optional) Associate and configure **calling number translation rules** for the trunk.</span></span> <span data-ttu-id="027ad-182">這些轉譯規則適用於撥出電話的撥打號碼</span><span class="sxs-lookup"><span data-stu-id="027ad-182">These translation rules apply to the calling number for outbound calls</span></span>

    - <span data-ttu-id="027ad-183">若要從 Enterprise Voice 部署中所有可用轉譯規則的清單中選擇一個或多個規則，請按一下 [ **選取**]。</span><span class="sxs-lookup"><span data-stu-id="027ad-183">To choose one or more rules from a list of all translation rules that are available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="027ad-184">在 **[選取轉譯規則]** 中，按一下您要建立關聯的主幹，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="027ad-184">In **Select Translation Rules**, click the rules that you want to associate with the trunk, and then click **OK**.</span></span>

    - <span data-ttu-id="027ad-185">若要定義新的轉譯規則並建立其與主幹的關聯，請按一下 **[新增]**。</span><span class="sxs-lookup"><span data-stu-id="027ad-185">To define a new translation rule and associate it with the trunk, click **New**.</span></span> <span data-ttu-id="027ad-186">如需有關轉譯規則的詳細資訊，請參閱 [商務用 Skype Server 中的轉譯規則](../../plan-your-deployment/enterprise-voice-solution/translation-rules.md)。</span><span class="sxs-lookup"><span data-stu-id="027ad-186">For details about translation rules, see [Translation rules in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/translation-rules.md).</span></span>

    - <span data-ttu-id="027ad-187">若要編輯已與主幹建立關聯的轉譯規則，按一下規則名稱，然後按一下 **[顯示詳細資料]**。</span><span class="sxs-lookup"><span data-stu-id="027ad-187">To edit a translation rule that is already associated with the trunk, click the rule name, and then click **Show details**.</span></span>

    - <span data-ttu-id="027ad-188">若要複製現有轉譯規則，以用來作為定義新規則時的起點，請按一下規則名稱，再按一下 **[複製]**，然後按一下 **[貼上]**。</span><span class="sxs-lookup"><span data-stu-id="027ad-188">To copy an existing translation rule to use as a starting point for defining a new rule, click the rule name and click **Copy**, and then click **Paste**.</span></span>

    - <span data-ttu-id="027ad-189">若要從主幹移除轉譯規則，請反白顯示該規則名稱並按一下 **[移除]**。</span><span class="sxs-lookup"><span data-stu-id="027ad-189">To remove a translation rule from the trunk, highlight the rule name and click **Remove**.</span></span>

      > [!CAUTION]
      > <span data-ttu-id="027ad-190">如果您已在關聯的主幹對等上設定轉譯規則，請勿再將轉譯規則與主幹建立關聯，因為這兩個規則可能會產生衝突。</span><span class="sxs-lookup"><span data-stu-id="027ad-190">Do not associate translation rules with a trunk if you have configured translation rules on the associated trunk peer, because the two rules might conflict.</span></span>

15. <span data-ttu-id="027ad-p128">(選用) 建立與主幹的關聯並設定其 **[撥號轉譯規則]**。這些轉譯規則適用於撥出電話的撥打號碼。</span><span class="sxs-lookup"><span data-stu-id="027ad-p128">(Optional) Associate and configure **called number translation rules** for the trunk. The translation rules apply to the called number in an outbound call.</span></span>

    - <span data-ttu-id="027ad-193">若要從 Enterprise Voice 部署中所有可用轉譯規則的清單中選擇一個或多個規則，請按一下 [ **選取**]。</span><span class="sxs-lookup"><span data-stu-id="027ad-193">To choose one or more rules from a list of all translation rules that are available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="027ad-194">在 **[選取轉譯規則]** 中，按一下您要建立關聯的主幹，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="027ad-194">In **Select Translation Rules**, click the rules that you want to associate with the trunk, and then click **OK**.</span></span>

    - <span data-ttu-id="027ad-195">若要定義新的轉譯規則並建立其與主幹的關聯，請按一下 **[新增]**。</span><span class="sxs-lookup"><span data-stu-id="027ad-195">To define a new translation rule and associate it with the trunk, click **New**.</span></span> <span data-ttu-id="027ad-196">如需有關轉譯規則的詳細資訊，請參閱 [商務用 Skype Server 中的轉譯規則](../../plan-your-deployment/enterprise-voice-solution/translation-rules.md)。</span><span class="sxs-lookup"><span data-stu-id="027ad-196">For details about translation rules, see [Translation rules in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/translation-rules.md).</span></span>

    - <span data-ttu-id="027ad-197">若要編輯已與主幹建立關聯的轉譯規則，按一下規則名稱，然後按一下 **[顯示詳細資料]**。</span><span class="sxs-lookup"><span data-stu-id="027ad-197">To edit a translation rule that is already associated with the trunk, click the rule name, and then click **Show details**.</span></span>

    - <span data-ttu-id="027ad-198">若要複製現有轉譯規則，以用來作為定義新規則時的起點，請按一下規則名稱，再按一下 **[複製]**，然後按一下 **[貼上]**。</span><span class="sxs-lookup"><span data-stu-id="027ad-198">To copy an existing translation rule to use as a starting point for defining a new rule, click the rule name and click **Copy**, and then click **Paste**.</span></span>

    - <span data-ttu-id="027ad-199">若要從主幹移除轉譯規則，請反白顯示該規則名稱並按一下 **[移除]**。</span><span class="sxs-lookup"><span data-stu-id="027ad-199">To remove a translation rule from the trunk, highlight the rule name and click **Remove**.</span></span>

      > [!CAUTION]
      > <span data-ttu-id="027ad-200">如果您已在相關聯的主幹對等上設定轉譯規則，則請勿將轉譯規則與主幹建立關聯，因為兩種規則可能會衝突。</span><span class="sxs-lookup"><span data-stu-id="027ad-200">Do not associate translation rules with a trunk if you have configured translation rules on the associated trunk peer, because the two rules might conflict.</span></span>

16. <span data-ttu-id="027ad-201">請確定主幹的轉譯規則依正確的順序排列。</span><span class="sxs-lookup"><span data-stu-id="027ad-201">Make sure that the trunk's translation rules are arranged in the correct order.</span></span> <span data-ttu-id="027ad-202">若要變更規則在清單中的位置，請反白顯示規則名稱，然後按一下向上或向下箭號。</span><span class="sxs-lookup"><span data-stu-id="027ad-202">To change a rule's position in the list, highlight the rule name, and then click the up or down arrow.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="027ad-203">商務用 Skype 伺服器會從左上部開始轉譯規則清單，並使用符合撥號號碼的第一個規則。</span><span class="sxs-lookup"><span data-stu-id="027ad-203">Skype for Business Server traverses the translation rule list from the top down and uses the first rule that matches the dialed number.</span></span> <span data-ttu-id="027ad-204">如果您設定的主幹會使撥號號碼符合不只一個轉譯規則，請確定限制較多的規則排在限制較少的規則上方。</span><span class="sxs-lookup"><span data-stu-id="027ad-204">If you configure a trunk so that a dialed number can match more than one translation rule, be sure that the more restrictive rules are sorted above the less restrictive rules.</span></span> <span data-ttu-id="027ad-205">例如，如果您已包含符合任何11位數的轉譯規則和轉譯規則，且符合以 + 1425 開頭的11位數，請確定符合任何11位數數位的規則，會依限制性更為嚴格的 *規則排序。*</span><span class="sxs-lookup"><span data-stu-id="027ad-205">For example, if you have included a translation rule that matches any 11-digit number and a translation rule that matches only 11-digit numbers that start with +1425, be sure that the rule that matches any 11-digit number is sorted  *below*  the more restrictive rule.</span></span>

17. <span data-ttu-id="027ad-206">完成主幹的設定時，請按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="027ad-206">When you are finished configuring the trunk, click **OK**.</span></span>

18. <span data-ttu-id="027ad-207">在 **[主幹組態]** 頁面上，按一下 **[認可]**，再按一下 **[全部認可]**。</span><span class="sxs-lookup"><span data-stu-id="027ad-207">On the **Trunk Configuration** page, click **Commit**, and then click **Commit all**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="027ad-208">只要建立或修改主幹組態後，都應執行 **[全部認可]** 命令以發行組態變更。</span><span class="sxs-lookup"><span data-stu-id="027ad-208">Whenever you create or modify a trunk configuration, you must run the **Commit all** command to publish the configuration change.</span></span> <span data-ttu-id="027ad-209">如需詳細資訊，請參閱 Operations 檔中的在 [商務用 Skype 中發佈待定的變更至語音路由](voice-route-config-changes.md) 設定。</span><span class="sxs-lookup"><span data-stu-id="027ad-209">For details, see [Publish pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md) in the Operations documentation.</span></span>

## <a name="see-also"></a><span data-ttu-id="027ad-210">另請參閱</span><span class="sxs-lookup"><span data-stu-id="027ad-210">See also</span></span>

[<span data-ttu-id="027ad-211">在商務用 Skype Server 中設定含媒體旁路的主幹</span><span class="sxs-lookup"><span data-stu-id="027ad-211">Configure a trunk with media bypass in Skype for Business Server</span></span>](configure-trunk-with-media-bypass.md)

[<span data-ttu-id="027ad-212">定義轉譯規則</span><span class="sxs-lookup"><span data-stu-id="027ad-212">Defining Translation Rules</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-defining-translation-rules)