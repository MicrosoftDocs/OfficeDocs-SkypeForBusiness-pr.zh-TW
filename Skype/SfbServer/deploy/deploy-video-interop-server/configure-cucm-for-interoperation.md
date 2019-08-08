---
title: 設定 CUCM 以與商務用 Skype 伺服器進行交互操作
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: eab3d9f6-ec40-49bf-9162-1a7f5a59451f
description: '摘要: 設定 CUCM 以搭配商務用 Skype 伺服器使用。'
ms.openlocfilehash: 8324e146147480bb682c2cc18c62a96e95a130e3
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/07/2019
ms.locfileid: "36235649"
---
# <a name="configure-cucm-for-interoperation-with-skype-for-business-server"></a><span data-ttu-id="ce64b-103">設定 CUCM 以與商務用 Skype 伺服器進行交互操作</span><span class="sxs-lookup"><span data-stu-id="ce64b-103">Configure CUCM for Interoperation with Skype for Business Server</span></span>
 
<span data-ttu-id="ce64b-104">**摘要:** 將 CUCM 設定為與商務用 Skype 伺服器搭配使用。</span><span class="sxs-lookup"><span data-stu-id="ce64b-104">**Summary:** Configure CUCM to work with Skype for Business Server.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="ce64b-105">這個功能是透過 Cisco 整合通訊管理員 (CallManager 或 CUCM) 版本10.5 使用 Trunks 安裝程式 (僅限 TCP) 來測試。</span><span class="sxs-lookup"><span data-stu-id="ce64b-105">This capability is tested with Cisco Unified Communications Manager (CallManager, or CUCM) version 10.5 using Trunks setup over TCP only.</span></span> <span data-ttu-id="ce64b-106">在繼續之前, 請確認 CUCM 環境符合這些準則。</span><span class="sxs-lookup"><span data-stu-id="ce64b-106">Verify that the CUCM environment meets these criteria before proceeding.</span></span> 
  
<span data-ttu-id="ce64b-107">此處所述的設定僅做為如何設定 CUCM 以搭配 VIS 使用的範例。</span><span class="sxs-lookup"><span data-stu-id="ce64b-107">The settings described here are meant only as examples of how CUCM can be configured to work with a VIS.</span></span> <span data-ttu-id="ce64b-108">您也可以使用替代 CUCM 功能的其他設定和/或用法來達到相同的結果。</span><span class="sxs-lookup"><span data-stu-id="ce64b-108">Other settings and/or usages of alternate CUCM functionality could also be used to achieve the same result.</span></span> <span data-ttu-id="ce64b-109">針對特定案例, 不建議使用最佳配置。</span><span class="sxs-lookup"><span data-stu-id="ce64b-109">No recommendation is implied as to the optimal configuration for a particular scenario.</span></span>
  
<span data-ttu-id="ce64b-110">若要與 VIS 進行交互操作, 必須確認或變更許多 CUCM 設定。</span><span class="sxs-lookup"><span data-stu-id="ce64b-110">A number of CUCM settings need to be confirmed or changed for interoperation with the VIS.</span></span> <span data-ttu-id="ce64b-111">請依照下列程式來避免遺失必要的設定。</span><span class="sxs-lookup"><span data-stu-id="ce64b-111">Follow the procedures below in order to avoid missing required settings.</span></span>
  
### <a name="configure-the-cucm"></a><span data-ttu-id="ce64b-112">設定 CUCM</span><span class="sxs-lookup"><span data-stu-id="ce64b-112">Configure the CUCM</span></span>

1. <span data-ttu-id="ce64b-113">登入 CUCM 並流覽至 Cisco 整合 CM 管理-\>呼叫路由-\>控制\>分區的類別。</span><span class="sxs-lookup"><span data-stu-id="ce64b-113">Log in to CUCM and navigate to Cisco Unified CM Administration-\>Call Routing-\>Class of Control-\>Partition.</span></span>
    
2. <span data-ttu-id="ce64b-114">在 [分區配置] 畫面中, 輸入分區名稱和描述, 然後按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="ce64b-114">In the Partition Configuration screen, enter the partition name and description and click on **Add New**.</span></span>
    
3. <span data-ttu-id="ce64b-115">流覽至 Cisco 整合 CM 管理-\>呼叫路由-\>控制\>呼叫搜尋空間的類別。</span><span class="sxs-lookup"><span data-stu-id="ce64b-115">Navigate to Cisco Unified CM Administration-\>Call Routing-\>Class of Control-\>Calling Search Space.</span></span>
    
4. <span data-ttu-id="ce64b-116">在 [呼叫搜尋空間設定] 畫面中, 輸入通話搜尋空間的名稱, 然後在 [選取的磁碟分割] 中輸入您剛建立的磁碟分割名稱。</span><span class="sxs-lookup"><span data-stu-id="ce64b-116">In the Calling Search Space Configuration screen, enter the name for the calling search space, and in Selected Partitions, enter the name of the partition you just created.</span></span> <span data-ttu-id="ce64b-117">完成後, 按一下 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="ce64b-117">Click **Save** when done.</span></span>
    
5. <span data-ttu-id="ce64b-118">流覽至 Cisco 一體化 CM 管理-\>系統\>安全性-\>SIP 主幹安全設定檔。</span><span class="sxs-lookup"><span data-stu-id="ce64b-118">Navigate to Cisco Unified CM Administration-\>System-\>Security-\>SIP Trunk Security Profile.</span></span>
    
6. <span data-ttu-id="ce64b-119">在 [SIP 中繼安全設定檔設定] 畫面中, 設定 SIP 中繼安全設定檔資訊選項, 如所示, 然後按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="ce64b-119">In the SIP Trunk Security Profile Configuration screen, set the SIP Trunk Security Profile Information options as shown, and click on **Add New**.</span></span>
    
   |<span data-ttu-id="ce64b-120">**參數**</span><span class="sxs-lookup"><span data-stu-id="ce64b-120">**Parameter**</span></span>|<span data-ttu-id="ce64b-121">**建議的設定**</span><span class="sxs-lookup"><span data-stu-id="ce64b-121">**Recommended setting**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="ce64b-122">名稱</span><span class="sxs-lookup"><span data-stu-id="ce64b-122">Name</span></span>  <br/> |<span data-ttu-id="ce64b-123">SfBVideoInterop_SecurityProfile</span><span class="sxs-lookup"><span data-stu-id="ce64b-123">SfBVideoInterop_SecurityProfile</span></span>  <br/> |
   |<span data-ttu-id="ce64b-124">裝置安全模式</span><span class="sxs-lookup"><span data-stu-id="ce64b-124">Device Security Mode</span></span>  <br/> |<span data-ttu-id="ce64b-125">不安全</span><span class="sxs-lookup"><span data-stu-id="ce64b-125">Non Secure</span></span>  <br/> |
   |<span data-ttu-id="ce64b-126">傳入傳輸類型</span><span class="sxs-lookup"><span data-stu-id="ce64b-126">Incoming Transport Type</span></span>  <br/> |<span data-ttu-id="ce64b-127">TCP + UDP</span><span class="sxs-lookup"><span data-stu-id="ce64b-127">TCP + UDP</span></span>  <br/> |
   |<span data-ttu-id="ce64b-128">外寄運輸類型</span><span class="sxs-lookup"><span data-stu-id="ce64b-128">Outgoing Transport Type</span></span>  <br/> |<span data-ttu-id="ce64b-129">TCP-OUT</span><span class="sxs-lookup"><span data-stu-id="ce64b-129">TCP</span></span>  <br/> |
   |<span data-ttu-id="ce64b-130">入站埠</span><span class="sxs-lookup"><span data-stu-id="ce64b-130">Incoming Port</span></span>  <br/> |<span data-ttu-id="ce64b-131">5060</span><span class="sxs-lookup"><span data-stu-id="ce64b-131">5060</span></span>  <br/> |
   
7. <span data-ttu-id="ce64b-132">流覽至 Cisco 整合 CM 管理-\>裝置-\>裝置設定-\>SIP 設定檔。</span><span class="sxs-lookup"><span data-stu-id="ce64b-132">Navigate to Cisco Unified CM Administration-\>Device-\>Device Settings-\>SIP Profile.</span></span>
    
8. <span data-ttu-id="ce64b-133">在 [SIP 設定檔設定] 畫面中, 設定 SIP 設定檔資訊選項, 如所示。</span><span class="sxs-lookup"><span data-stu-id="ce64b-133">In the SIP Profile Configuration screen, set the SIP Profile Information options as shown.</span></span> 
    
   |<span data-ttu-id="ce64b-134">**參數**</span><span class="sxs-lookup"><span data-stu-id="ce64b-134">**Parameter**</span></span>|<span data-ttu-id="ce64b-135">**建議的設定**</span><span class="sxs-lookup"><span data-stu-id="ce64b-135">**Recommended setting**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="ce64b-136">名稱</span><span class="sxs-lookup"><span data-stu-id="ce64b-136">Name</span></span>  <br/> |<span data-ttu-id="ce64b-137">SfBVideoInterop_SIPProfile</span><span class="sxs-lookup"><span data-stu-id="ce64b-137">SfBVideoInterop_SIPProfile</span></span>  <br/> |
   |<span data-ttu-id="ce64b-138">說明</span><span class="sxs-lookup"><span data-stu-id="ce64b-138">Description</span></span>  <br/> |<span data-ttu-id="ce64b-139">SfBVideoInterop_SIPProfile</span><span class="sxs-lookup"><span data-stu-id="ce64b-139">SfBVideoInterop_SIPProfile</span></span>  <br/> |
   
9. <span data-ttu-id="ce64b-140">在同一個畫面上, 向下滾動至 SDP 設定檔資訊區段。</span><span class="sxs-lookup"><span data-stu-id="ce64b-140">On the same screen, scroll down to the SDP Profile Information section.</span></span> <span data-ttu-id="ce64b-141">[**早期方案] 和 [重新邀請] 選項的 SDP 工作階段層級頻寬修正**程式預設會設定為 TIAS 和 AS。</span><span class="sxs-lookup"><span data-stu-id="ce64b-141">The **SDP Session-level Bandwidth Modifier for Early Offer and Re-invites** option is set by default to TIAS and AS.</span></span> <span data-ttu-id="ce64b-142">將此選項變更為 [僅供 TIAS]。</span><span class="sxs-lookup"><span data-stu-id="ce64b-142">Change this option to TIAS only.</span></span> <span data-ttu-id="ce64b-143">如果您保留此選項的預設設定, 商務用 Skype 伺服器將無法瞭解 SIP 訊息中的頻寬修正資訊。</span><span class="sxs-lookup"><span data-stu-id="ce64b-143">If you leave this option at its default setting, Skype for Business Server will not understand the bandwidth modifier information in the SIP message.</span></span> <span data-ttu-id="ce64b-144">TIAS 代表特定的傳輸獨立應用程式, 而不是指特定應用程式。</span><span class="sxs-lookup"><span data-stu-id="ce64b-144">TIAS means Transport Independent Application Specific while AS means Application Specific.</span></span> <span data-ttu-id="ce64b-145">這些是在 RFC3890 中指定的 SIP 選項。</span><span class="sxs-lookup"><span data-stu-id="ce64b-145">These are SIP options specified in RFC3890.</span></span>
    
10. <span data-ttu-id="ce64b-146">在同一個畫面上, 進一步向下滾動。</span><span class="sxs-lookup"><span data-stu-id="ce64b-146">On the same screen, scroll down further.</span></span> <span data-ttu-id="ce64b-147">在 SIP 設定檔的 [中繼專用設定] 底下, 選取 [**提供語音及視頻通話的早期支援**], 將它設為 [必要**時插入 MTP** ] 選項。</span><span class="sxs-lookup"><span data-stu-id="ce64b-147">Under the SIP Profile's Trunk Specific Configuration, select **Early Offer Support for voice and video calls** and set it to the **Mandatory (insert MTP if needed)** option.</span></span> <span data-ttu-id="ce64b-148">這會讓 CUCM 使用早期優惠設定傳出 SIP 通話。</span><span class="sxs-lookup"><span data-stu-id="ce64b-148">This will enable CUCM to set up an outgoing SIP call with Early Offer.</span></span> <span data-ttu-id="ce64b-149">CUCM 8.5 中的一項新功能是支援不需要媒體端接點 (MTP) 的撥出電話設定與早期優惠。</span><span class="sxs-lookup"><span data-stu-id="ce64b-149">One new feature in CUCM 8.5 and beyond is that it supports outgoing call setup with Early Offer without requiring Media Termination Point (MTP).</span></span>
    
11. <span data-ttu-id="ce64b-150">確認在 [SIP 選項] [ping] 區段中, 選取 [啟用選項 Ping 以監視 Trunks 的目的地狀態] 旁邊的方塊, 然後服務類型為「無 (預設)」。」</span><span class="sxs-lookup"><span data-stu-id="ce64b-150">Verify that in the SIP Options ping section, the box is checked next to "Enable OPTIONS Ping to monitor destination status for Trunks with Service Type 'None (Default)'."</span></span>
    
12. <span data-ttu-id="ce64b-151">完成後, 請按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="ce64b-151">When you are finished, click on **Add New**.</span></span>
    
13. <span data-ttu-id="ce64b-152">流覽至 Cisco 一體化 CM 管理-\>裝置-\>幹線。</span><span class="sxs-lookup"><span data-stu-id="ce64b-152">Navigate to Cisco Unified CM Administration-\>Device-\>Trunk.</span></span> 
    
14. <span data-ttu-id="ce64b-153">將裝置通訊協定設定為 SIP, 然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="ce64b-153">Set the Device Protocol to SIP and press **Next**.</span></span>
    
15. <span data-ttu-id="ce64b-154">在 [裝置資訊] 底下, 設定裝置名稱和描述 (可能是例如 SfBVideoInterop_SIPTrunk), 並將媒體資源群組清單設定為包含合適媒體資源的 MRGL。</span><span class="sxs-lookup"><span data-stu-id="ce64b-154">Under Device Information, Set the Device Name and Description (probably to something like SfBVideoInterop_SIPTrunk), and set the Media Resource Group List to an MRGL that contains the right media resources.</span></span> 
    
16. <span data-ttu-id="ce64b-155">進一步向下滾動。</span><span class="sxs-lookup"><span data-stu-id="ce64b-155">Scroll down further.</span></span> <span data-ttu-id="ce64b-156">如果視頻通話沒有取消核取, 就不需要媒體端接點 (MTP), 請取消核取。</span><span class="sxs-lookup"><span data-stu-id="ce64b-156">Media Termination Point (MTP) is not required for Video Calls, if it is not already unchecked, uncheck it.</span></span> <span data-ttu-id="ce64b-157">選取 [**在所有使用中整合的 CM 節點上執行**] 選項。</span><span class="sxs-lookup"><span data-stu-id="ce64b-157">Check the option to **Run on all active Unified CM Nodes**.</span></span> <span data-ttu-id="ce64b-158">請注意, 您應該將所有 CUCM 節點新增至商務用 Skype 伺服器設定。</span><span class="sxs-lookup"><span data-stu-id="ce64b-158">Please note that you should add all CUCM nodes to the Skype for Business Server configuration.</span></span>
    
17. <span data-ttu-id="ce64b-159">進一步向下滾動。</span><span class="sxs-lookup"><span data-stu-id="ce64b-159">Scroll down further.</span></span> <span data-ttu-id="ce64b-160">設定 [撥入通話] 和 [連線的通訊錄設定] 選項, 如所示。</span><span class="sxs-lookup"><span data-stu-id="ce64b-160">Set the Inbound Calls and Connected Party Settings options as shown.</span></span>
    
    |<span data-ttu-id="ce64b-161">**參數**</span><span class="sxs-lookup"><span data-stu-id="ce64b-161">**Parameter**</span></span>|<span data-ttu-id="ce64b-162">**建議的設定**</span><span class="sxs-lookup"><span data-stu-id="ce64b-162">**Recommended setting**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="ce64b-163">呼叫搜尋空間</span><span class="sxs-lookup"><span data-stu-id="ce64b-163">Calling Search Space</span></span>  <br/> |<span data-ttu-id="ce64b-164">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="ce64b-164">CSS_SfBVideoInterop</span></span>  <br/> |
    |<span data-ttu-id="ce64b-165">呼叫搜尋空間 AAR</span><span class="sxs-lookup"><span data-stu-id="ce64b-165">AAR Calling Search Space</span></span>  <br/> |<span data-ttu-id="ce64b-166">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="ce64b-166">CSS_SfBVideoInterop</span></span>  <br/> |
    |<span data-ttu-id="ce64b-167">已連線的參與方轉換 CSS</span><span class="sxs-lookup"><span data-stu-id="ce64b-167">Connected Party Transformation CSS</span></span>  <br/> |<span data-ttu-id="ce64b-168">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="ce64b-168">CSS_SfBVideoInterop</span></span>  <br/> |
   
18. <span data-ttu-id="ce64b-169">進一步向下滾動。</span><span class="sxs-lookup"><span data-stu-id="ce64b-169">Scroll down further.</span></span> <span data-ttu-id="ce64b-170">在 SIP 中繼設定的 [SIP 資訊目標] 區段底下, 指定 VIS 池的 FQDN 或池中個別 VIS 伺服器的 IP 位址 (新增多個專案)。</span><span class="sxs-lookup"><span data-stu-id="ce64b-170">Under the SIP Information Destination section of the SIP Trunk configuration, specify the VIS Pool's FQDN or the IP address of individual VIS servers in the pool (adding multiple entries).</span></span> <span data-ttu-id="ce64b-171">在 [目的地埠] 中, 指定 VIS 正在接聽的埠, 以取得從 CUCM 的連線 (預設值為 6001)。</span><span class="sxs-lookup"><span data-stu-id="ce64b-171">In the Destination Port specify the Port that VIS is listening at for connections from CUCM (the default is 6001).</span></span> <span data-ttu-id="ce64b-172">另外, 請指定您先前建立的 SIP 幹線安全設定檔和 SIP 設定檔, 如所示。</span><span class="sxs-lookup"><span data-stu-id="ce64b-172">Also specify the SIP Trunk security profile and SIP profile you created earlier, as shown.</span></span>
    
    |<span data-ttu-id="ce64b-173">**參數**</span><span class="sxs-lookup"><span data-stu-id="ce64b-173">**Parameter**</span></span>|<span data-ttu-id="ce64b-174">**建議的設定**</span><span class="sxs-lookup"><span data-stu-id="ce64b-174">**Recommended setting**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="ce64b-175">SIP 中繼安全設定檔</span><span class="sxs-lookup"><span data-stu-id="ce64b-175">SIP Trunk Security Profile</span></span>  <br/> |<span data-ttu-id="ce64b-176">SfBVideoInterop_SecurityProfile</span><span class="sxs-lookup"><span data-stu-id="ce64b-176">SfBVideoInterop_SecurityProfile</span></span>  <br/> |
    |<span data-ttu-id="ce64b-177">重新路由呼叫搜尋空間</span><span class="sxs-lookup"><span data-stu-id="ce64b-177">Rerouting Calling Search Space</span></span>  <br/> |<span data-ttu-id="ce64b-178">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="ce64b-178">CSS_SfBVideoInterop</span></span>  <br/> |
    |<span data-ttu-id="ce64b-179">[離開] 對話方塊請參閱呼叫搜尋空間</span><span class="sxs-lookup"><span data-stu-id="ce64b-179">Out-of-Dialog Refer Calling Search Space</span></span>  <br/> |<span data-ttu-id="ce64b-180">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="ce64b-180">CSS_SfBVideoInterop</span></span>  <br/> |
    |<span data-ttu-id="ce64b-181">訂閱通話搜尋空間</span><span class="sxs-lookup"><span data-stu-id="ce64b-181">Subscribe Calling Search Space</span></span>  <br/> |<span data-ttu-id="ce64b-182">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="ce64b-182">CSS_SfBVideoInterop</span></span>  <br/> |
    |<span data-ttu-id="ce64b-183">SIP 設定檔</span><span class="sxs-lookup"><span data-stu-id="ce64b-183">SIP Profile</span></span>  <br/> |<span data-ttu-id="ce64b-184">SfBVideoInterop_SIPProfile</span><span class="sxs-lookup"><span data-stu-id="ce64b-184">SfBVideoInterop_SIPProfile</span></span>  <br/> |
    |<span data-ttu-id="ce64b-185">DTMF 信號方法</span><span class="sxs-lookup"><span data-stu-id="ce64b-185">DTMF Signaling Method</span></span>  <br/> |<span data-ttu-id="ce64b-186">RFC 2833</span><span class="sxs-lookup"><span data-stu-id="ce64b-186">RFC 2833</span></span>  <br/> |
   
19.  <span data-ttu-id="ce64b-187">進一步向下滾動。</span><span class="sxs-lookup"><span data-stu-id="ce64b-187">Scroll down further.</span></span> <span data-ttu-id="ce64b-188">根據您的系統設定錄製資訊。</span><span class="sxs-lookup"><span data-stu-id="ce64b-188">Set the Recording Information as appropriate for your system.</span></span> <span data-ttu-id="ce64b-189">您可以將它設為 [**無**]。</span><span class="sxs-lookup"><span data-stu-id="ce64b-189">It's fine to leave it set to **None**.</span></span> 
    
20. <span data-ttu-id="ce64b-190">完成後, 請按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="ce64b-190">When you are finished, click on **Add New**.</span></span>
    
21. <span data-ttu-id="ce64b-191">流覽至 Cisco 整合 CM 管理-\>呼叫路由-\>路由/查尋\>路由模式。</span><span class="sxs-lookup"><span data-stu-id="ce64b-191">Navigate to Cisco Unified CM Administration-\>Call Routing-\>Route/Hunt-\>Route pattern.</span></span>
    
22. <span data-ttu-id="ce64b-192">在 [路由模式設定] 畫面中, 輸入如下所示的模式定義參數。</span><span class="sxs-lookup"><span data-stu-id="ce64b-192">In the Route Pattern Configuration screen, enter the Pattern definition parameters shown below.</span></span> <span data-ttu-id="ce64b-193">向下滾動至 [呼叫方轉換] 區段, 並設定遮罩, 如圖所示, 然後按一下 [完成時**新增**]。</span><span class="sxs-lookup"><span data-stu-id="ce64b-193">Scroll down to the Called Party Transformations section and set the mask as shown, and then click on **Add New** when finished.</span></span>
    
    |<span data-ttu-id="ce64b-194">**參數**</span><span class="sxs-lookup"><span data-stu-id="ce64b-194">**Parameter**</span></span>|<span data-ttu-id="ce64b-195">**建議的設定**</span><span class="sxs-lookup"><span data-stu-id="ce64b-195">**Recommended setting**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="ce64b-196">路線模式</span><span class="sxs-lookup"><span data-stu-id="ce64b-196">Route Pattern</span></span>  <br/> |<span data-ttu-id="ce64b-197">7779999</span><span class="sxs-lookup"><span data-stu-id="ce64b-197">7779999</span></span>  <br/> |
    |<span data-ttu-id="ce64b-198">路由分區</span><span class="sxs-lookup"><span data-stu-id="ce64b-198">Route Partition</span></span>  <br/> |<span data-ttu-id="ce64b-199">SfBVideoInterop_RoutePartition</span><span class="sxs-lookup"><span data-stu-id="ce64b-199">SfBVideoInterop_RoutePartition</span></span>  <br/> |
    |<span data-ttu-id="ce64b-200">說明</span><span class="sxs-lookup"><span data-stu-id="ce64b-200">Description</span></span>  <br/> |<span data-ttu-id="ce64b-201">SfBVideoInterop 的磁碟分割</span><span class="sxs-lookup"><span data-stu-id="ce64b-201">Partition for SfBVideoInterop</span></span>  <br/> |
    |<span data-ttu-id="ce64b-202">閘道/路由清單</span><span class="sxs-lookup"><span data-stu-id="ce64b-202">Gateway/Route List</span></span>  <br/> |<span data-ttu-id="ce64b-203">SfBVideoInterop_SIPTrunk</span><span class="sxs-lookup"><span data-stu-id="ce64b-203">SfBVideoInterop_SIPTrunk</span></span>  <br/> |
    |<span data-ttu-id="ce64b-204">已呼叫參與方轉換遮罩</span><span class="sxs-lookup"><span data-stu-id="ce64b-204">Called Party Transform Mask</span></span>  <br/> |<span data-ttu-id="ce64b-205">+ 14257779999</span><span class="sxs-lookup"><span data-stu-id="ce64b-205">+14257779999</span></span>  <br/> |
   
23. <span data-ttu-id="ce64b-206">流覽至 Cisco 整合 CM 管理-\>呼叫路由-\>SIP 路由模式。</span><span class="sxs-lookup"><span data-stu-id="ce64b-206">Navigate to Cisco Unified CM Administration-\>Call Routing-\>SIP Route Pattern.</span></span>
    
24. <span data-ttu-id="ce64b-207">在 [SIP 路由模式設定] 畫面中, 設定 [模式定義] 選項, 如圖所示, 然後按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="ce64b-207">In the SIP Route Pattern Configuration screen, set the Pattern Definition options as shown, and click on **Add New**.</span></span>
    
    |<span data-ttu-id="ce64b-208">**參數**</span><span class="sxs-lookup"><span data-stu-id="ce64b-208">**Parameter**</span></span>|<span data-ttu-id="ce64b-209">**建議的設定**</span><span class="sxs-lookup"><span data-stu-id="ce64b-209">**Recommended setting**</span></span>|
    |:-----|:-----|
    | <span data-ttu-id="ce64b-210">模式用法</span><span class="sxs-lookup"><span data-stu-id="ce64b-210">Pattern Usage</span></span> <br/> |<span data-ttu-id="ce64b-211">網域路由</span><span class="sxs-lookup"><span data-stu-id="ce64b-211">Domain Routing</span></span>  <br/> |
    |<span data-ttu-id="ce64b-212">IPv4 模式</span><span class="sxs-lookup"><span data-stu-id="ce64b-212">IPv4 Pattern</span></span>  <br/> |<span data-ttu-id="ce64b-213">contoso.com (如果使用 IPv6, 請保留空白)</span><span class="sxs-lookup"><span data-stu-id="ce64b-213">contoso.com (leave blank if using IPv6)</span></span>  <br/> |
    |<span data-ttu-id="ce64b-214">IPv6 模式</span><span class="sxs-lookup"><span data-stu-id="ce64b-214">IPv6 Pattern</span></span>  <br/> |<span data-ttu-id="ce64b-215">contoso.com (如果使用 IPv4, 則留空)</span><span class="sxs-lookup"><span data-stu-id="ce64b-215">contoso.com (leave blank if using IPv4)</span></span>  <br/> |
    |<span data-ttu-id="ce64b-216">說明</span><span class="sxs-lookup"><span data-stu-id="ce64b-216">Description</span></span>  <br/> |<span data-ttu-id="ce64b-217">SIPRoute 模式至 mediarv</span><span class="sxs-lookup"><span data-stu-id="ce64b-217">SIPRoute Pattern to mediarv</span></span>  <br/> |
    |<span data-ttu-id="ce64b-218">路由分區</span><span class="sxs-lookup"><span data-stu-id="ce64b-218">Route Partition</span></span>  <br/> |<span data-ttu-id="ce64b-219">SfBVideoInterop_RoutePartition</span><span class="sxs-lookup"><span data-stu-id="ce64b-219">SfBVideoInterop_RoutePartition</span></span>  <br/> |
    |<span data-ttu-id="ce64b-220">SIP 幹線/路由清單</span><span class="sxs-lookup"><span data-stu-id="ce64b-220">SIP Trunk/Route List</span></span>  <br/> |<span data-ttu-id="ce64b-221">SfBVideoInterop_SIPTrunk</span><span class="sxs-lookup"><span data-stu-id="ce64b-221">SfBVideoInterop_SIPTrunk</span></span>  <br/> |
    |<span data-ttu-id="ce64b-222">[封鎖模式] 核取方塊</span><span class="sxs-lookup"><span data-stu-id="ce64b-222">Block Pattern checkbox</span></span>  <br/> |<span data-ttu-id="ce64b-223">保持未選取狀態</span><span class="sxs-lookup"><span data-stu-id="ce64b-223">leave unchecked</span></span>  <br/> |
   
25. <span data-ttu-id="ce64b-224">如果您已從預設設定變更音訊或影片位元速率, 您必須將它們傳回預設值。</span><span class="sxs-lookup"><span data-stu-id="ce64b-224">If you have changed the audio or video bit rates from the default settings, you will need to return them to the defaults.</span></span> <span data-ttu-id="ce64b-225">若要設定音訊/視頻通話的位元速率, 請流覽至 Cisco 一體化 CM 管理\>-系統\>區域資訊\>區域。</span><span class="sxs-lookup"><span data-stu-id="ce64b-225">To set the bit rate for Audio/Video calls, navigate to Cisco Unified CM Administration-\>System-\>Region Information-\>Region.</span></span> <span data-ttu-id="ce64b-226">預設值如下所示:</span><span class="sxs-lookup"><span data-stu-id="ce64b-226">The defaults are shown below for reference:</span></span>
    
    |<span data-ttu-id="ce64b-227">**參數**</span><span class="sxs-lookup"><span data-stu-id="ce64b-227">**Parameter**</span></span>|<span data-ttu-id="ce64b-228">**建議的設定**</span><span class="sxs-lookup"><span data-stu-id="ce64b-228">**Recommended setting**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="ce64b-229">國家</span><span class="sxs-lookup"><span data-stu-id="ce64b-229">Region</span></span>  <br/> |<span data-ttu-id="ce64b-230">設置</span><span class="sxs-lookup"><span data-stu-id="ce64b-230">Default</span></span>  <br/> |
    |<span data-ttu-id="ce64b-231">音訊編解碼器喜好設定清單</span><span class="sxs-lookup"><span data-stu-id="ce64b-231">Audio Codec Preference List</span></span>  <br/> |<span data-ttu-id="ce64b-232">系統預設值</span><span class="sxs-lookup"><span data-stu-id="ce64b-232">System Default</span></span>  <br/> |
    |<span data-ttu-id="ce64b-233">音訊位元速率上限</span><span class="sxs-lookup"><span data-stu-id="ce64b-233">Maximum Audio Bit Rate</span></span>  <br/> |<span data-ttu-id="ce64b-234">64 kbps (722, 711)</span><span class="sxs-lookup"><span data-stu-id="ce64b-234">64 kbps (G.722, G.711)</span></span>  <br/> |
    |<span data-ttu-id="ce64b-235">針對視頻通話的最大會話位元速率</span><span class="sxs-lookup"><span data-stu-id="ce64b-235">Maximum Session Bit Rate for Video Calls</span></span>  <br/> |<span data-ttu-id="ce64b-236">200000 kbps</span><span class="sxs-lookup"><span data-stu-id="ce64b-236">200000 kbps</span></span>  <br/> |
    |<span data-ttu-id="ce64b-237">會話位元速率上限</span><span class="sxs-lookup"><span data-stu-id="ce64b-237">Maximum Session Bit Rate</span></span>  <br/> |<span data-ttu-id="ce64b-238">2000000000 kbps</span><span class="sxs-lookup"><span data-stu-id="ce64b-238">2000000000 kbps</span></span>  <br/> |
   
<span data-ttu-id="ce64b-239">此時, CUCM 視頻閘道設定為與 VIS 搭配使用。</span><span class="sxs-lookup"><span data-stu-id="ce64b-239">At this point the CUCM video gateway is configured to work with the VIS.</span></span> <span data-ttu-id="ce64b-240">相對應的設定將需要在您想要整合的每個 VTC 上執行。</span><span class="sxs-lookup"><span data-stu-id="ce64b-240">Corresponding configuration will need to be done on each VTC you wish to integrate.</span></span>
> [!NOTE]
> <span data-ttu-id="ce64b-241">若要改善復原能力, 您可能會想要將此 CUCM 閘道設定為使用第二個視頻交互操作伺服器或 VIS 池來運作。</span><span class="sxs-lookup"><span data-stu-id="ce64b-241">To improve resiliency, you may want to configure this CUCM gateway to work with a second Video Interop Server or VIS pool.</span></span> <span data-ttu-id="ce64b-242">如需詳細資訊, 請參閱[復原機制](../../plan-your-deployment/video-interop-server.md#resiliency)。</span><span class="sxs-lookup"><span data-stu-id="ce64b-242">See [Resiliency mechanisms](../../plan-your-deployment/video-interop-server.md#resiliency) for more information.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="ce64b-243">另請參閱</span><span class="sxs-lookup"><span data-stu-id="ce64b-243">See also</span></span>

[<span data-ttu-id="ce64b-244">設定與商務用 Skype 伺服器交互操作的 VTC</span><span class="sxs-lookup"><span data-stu-id="ce64b-244">Configure a VTC for Interoperation with Skype for Business Server</span></span>](configure-a-vtc-for-interoperation.md)
