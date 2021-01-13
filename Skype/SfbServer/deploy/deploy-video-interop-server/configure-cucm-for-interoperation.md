---
title: 設定 CUCM 以搭配商務用 Skype 伺服器進行交互操作
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
ms.collection: IT_Skype16
ms.assetid: eab3d9f6-ec40-49bf-9162-1a7f5a59451f
description: 摘要：設定 CUCM 以搭配商務用 Skype Server 使用。
ms.openlocfilehash: 82fa48a185b22973d35bc19484e733e6436ba43e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49837113"
---
# <a name="configure-cucm-for-interoperation-with-skype-for-business-server"></a><span data-ttu-id="4c20f-103">設定 CUCM 以搭配商務用 Skype 伺服器進行交互操作</span><span class="sxs-lookup"><span data-stu-id="4c20f-103">Configure CUCM for Interoperation with Skype for Business Server</span></span>
 
<span data-ttu-id="4c20f-104">**摘要：** 設定 CUCM 以與商務用 Skype Server 搭配使用。</span><span class="sxs-lookup"><span data-stu-id="4c20f-104">**Summary:** Configure CUCM to work with Skype for Business Server.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="4c20f-105">這項功能是透過 Cisco 整合通訊管理員 (CallManager，或是 CUCM) 版本10.5，只使用主幹安裝 over TCP 進行測試。</span><span class="sxs-lookup"><span data-stu-id="4c20f-105">This capability is tested with Cisco Unified Communications Manager (CallManager, or CUCM) version 10.5 using Trunks setup over TCP only.</span></span> <span data-ttu-id="4c20f-106">在繼續之前，請確認 CUCM 環境符合這些準則。</span><span class="sxs-lookup"><span data-stu-id="4c20f-106">Verify that the CUCM environment meets these criteria before proceeding.</span></span> 
  
<span data-ttu-id="4c20f-107">這裡所述的設定只是 CUCM 如何設定為搭配 VIS 使用的範例。</span><span class="sxs-lookup"><span data-stu-id="4c20f-107">The settings described here are meant only as examples of how CUCM can be configured to work with a VIS.</span></span> <span data-ttu-id="4c20f-108">其他設定和/或替代 CUCM 功能的使用方式也可以用來達到相同的結果。</span><span class="sxs-lookup"><span data-stu-id="4c20f-108">Other settings and/or usages of alternate CUCM functionality could also be used to achieve the same result.</span></span> <span data-ttu-id="4c20f-109">不建議使用特定案例的最佳設定。</span><span class="sxs-lookup"><span data-stu-id="4c20f-109">No recommendation is implied as to the optimal configuration for a particular scenario.</span></span>
  
<span data-ttu-id="4c20f-110">若要與 VIS 進行交互操作，必須確認或變更 CUCM 設定的數目。</span><span class="sxs-lookup"><span data-stu-id="4c20f-110">A number of CUCM settings need to be confirmed or changed for interoperation with the VIS.</span></span> <span data-ttu-id="4c20f-111">請遵循下列程式，以避免遺失必要的設定。</span><span class="sxs-lookup"><span data-stu-id="4c20f-111">Follow the procedures below in order to avoid missing required settings.</span></span>
  
### <a name="configure-the-cucm"></a><span data-ttu-id="4c20f-112">設定 CUCM</span><span class="sxs-lookup"><span data-stu-id="4c20f-112">Configure the CUCM</span></span>

1. <span data-ttu-id="4c20f-113">登入 CUCM 並流覽至 Cisco 統一 CM 管理- \> 呼叫路由 \> 類別的控制 \> 分割區。</span><span class="sxs-lookup"><span data-stu-id="4c20f-113">Log in to CUCM and navigate to Cisco Unified CM Administration-\>Call Routing-\>Class of Control-\>Partition.</span></span>
    
2. <span data-ttu-id="4c20f-114">在 [磁碟分割設定] 畫面中，輸入磁碟分割名稱和描述，然後按一下 [ **新增**]。</span><span class="sxs-lookup"><span data-stu-id="4c20f-114">In the Partition Configuration screen, enter the partition name and description and click on **Add New**.</span></span>
    
3. <span data-ttu-id="4c20f-115">流覽至 Cisco 統一 CM 管理- \> 呼叫路由 \> 類別的 Control- \> 呼叫搜尋空間。</span><span class="sxs-lookup"><span data-stu-id="4c20f-115">Navigate to Cisco Unified CM Administration-\>Call Routing-\>Class of Control-\>Calling Search Space.</span></span>
    
4. <span data-ttu-id="4c20f-116">在 [呼叫搜尋空間設定] 畫面中，輸入呼叫搜尋空間的名稱，然後在 [選取的磁碟分割] 中輸入剛才建立之磁碟分割的名稱。</span><span class="sxs-lookup"><span data-stu-id="4c20f-116">In the Calling Search Space Configuration screen, enter the name for the calling search space, and in Selected Partitions, enter the name of the partition you just created.</span></span> <span data-ttu-id="4c20f-117">完成後，按一下 [ **儲存** ]。</span><span class="sxs-lookup"><span data-stu-id="4c20f-117">Click **Save** when done.</span></span>
    
5. <span data-ttu-id="4c20f-118">流覽 Cisco 統一 CM 管理- \> 系統 \> 安全性- \> SIP 主幹安全性設定檔。</span><span class="sxs-lookup"><span data-stu-id="4c20f-118">Navigate to Cisco Unified CM Administration-\>System-\>Security-\>SIP Trunk Security Profile.</span></span>
    
6. <span data-ttu-id="4c20f-119">在 [SIP 主幹安全性設定檔設定] 畫面中，設定 SIP 主幹安全性設定檔資訊選項（如圖所示），然後按一下 [ **新增**]。</span><span class="sxs-lookup"><span data-stu-id="4c20f-119">In the SIP Trunk Security Profile Configuration screen, set the SIP Trunk Security Profile Information options as shown, and click on **Add New**.</span></span>
    
   |<span data-ttu-id="4c20f-120">**參數**</span><span class="sxs-lookup"><span data-stu-id="4c20f-120">**Parameter**</span></span>|<span data-ttu-id="4c20f-121">**建議的設定**</span><span class="sxs-lookup"><span data-stu-id="4c20f-121">**Recommended setting**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="4c20f-122">姓名</span><span class="sxs-lookup"><span data-stu-id="4c20f-122">Name</span></span>  <br/> |<span data-ttu-id="4c20f-123">SfBVideoInterop_SecurityProfile</span><span class="sxs-lookup"><span data-stu-id="4c20f-123">SfBVideoInterop_SecurityProfile</span></span>  <br/> |
   |<span data-ttu-id="4c20f-124">裝置安全性模式</span><span class="sxs-lookup"><span data-stu-id="4c20f-124">Device Security Mode</span></span>  <br/> |<span data-ttu-id="4c20f-125">不安全</span><span class="sxs-lookup"><span data-stu-id="4c20f-125">Non Secure</span></span>  <br/> |
   |<span data-ttu-id="4c20f-126">傳入傳輸類型</span><span class="sxs-lookup"><span data-stu-id="4c20f-126">Incoming Transport Type</span></span>  <br/> |<span data-ttu-id="4c20f-127">TCP + UDP</span><span class="sxs-lookup"><span data-stu-id="4c20f-127">TCP + UDP</span></span>  <br/> |
   |<span data-ttu-id="4c20f-128">外寄傳輸類型</span><span class="sxs-lookup"><span data-stu-id="4c20f-128">Outgoing Transport Type</span></span>  <br/> |<span data-ttu-id="4c20f-129">TCP</span><span class="sxs-lookup"><span data-stu-id="4c20f-129">TCP</span></span>  <br/> |
   |<span data-ttu-id="4c20f-130">傳入埠</span><span class="sxs-lookup"><span data-stu-id="4c20f-130">Incoming Port</span></span>  <br/> |<span data-ttu-id="4c20f-131">5060</span><span class="sxs-lookup"><span data-stu-id="4c20f-131">5060</span></span>  <br/> |
   
7. <span data-ttu-id="4c20f-132">流覽 Cisco 統一 CM 管理- \> 裝置- \> 裝置設定- \> SIP 設定檔。</span><span class="sxs-lookup"><span data-stu-id="4c20f-132">Navigate to Cisco Unified CM Administration-\>Device-\>Device Settings-\>SIP Profile.</span></span>
    
8. <span data-ttu-id="4c20f-133">在 [SIP 設定檔設定] 畫面中，設定 SIP 設定檔資訊選項（如圖所示）。</span><span class="sxs-lookup"><span data-stu-id="4c20f-133">In the SIP Profile Configuration screen, set the SIP Profile Information options as shown.</span></span> 
    
   |<span data-ttu-id="4c20f-134">**參數**</span><span class="sxs-lookup"><span data-stu-id="4c20f-134">**Parameter**</span></span>|<span data-ttu-id="4c20f-135">**建議的設定**</span><span class="sxs-lookup"><span data-stu-id="4c20f-135">**Recommended setting**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="4c20f-136">姓名</span><span class="sxs-lookup"><span data-stu-id="4c20f-136">Name</span></span>  <br/> |<span data-ttu-id="4c20f-137">SfBVideoInterop_SIPProfile</span><span class="sxs-lookup"><span data-stu-id="4c20f-137">SfBVideoInterop_SIPProfile</span></span>  <br/> |
   |<span data-ttu-id="4c20f-138">描述</span><span class="sxs-lookup"><span data-stu-id="4c20f-138">Description</span></span>  <br/> |<span data-ttu-id="4c20f-139">SfBVideoInterop_SIPProfile</span><span class="sxs-lookup"><span data-stu-id="4c20f-139">SfBVideoInterop_SIPProfile</span></span>  <br/> |
   
9. <span data-ttu-id="4c20f-140">在同一個畫面上，向下滾動至 [SDP 設定檔資訊] 區段。</span><span class="sxs-lookup"><span data-stu-id="4c20f-140">On the same screen, scroll down to the SDP Profile Information section.</span></span> <span data-ttu-id="4c20f-141">「 **早期提供」和「重新邀請」選項的 SDP 工作階段層級頻寬修正** 程式預設會設定為 TIAS 和 AS。</span><span class="sxs-lookup"><span data-stu-id="4c20f-141">The **SDP Session-level Bandwidth Modifier for Early Offer and Re-invites** option is set by default to TIAS and AS.</span></span> <span data-ttu-id="4c20f-142">將此選項改為 [僅限 TIAS]。</span><span class="sxs-lookup"><span data-stu-id="4c20f-142">Change this option to TIAS only.</span></span> <span data-ttu-id="4c20f-143">如果您保留此選項的預設值，則商務用 Skype 伺服器將不會瞭解 SIP 郵件中的頻寬修正資訊。</span><span class="sxs-lookup"><span data-stu-id="4c20f-143">If you leave this option at its default setting, Skype for Business Server will not understand the bandwidth modifier information in the SIP message.</span></span> <span data-ttu-id="4c20f-144">TIAS 表示特定的傳輸獨立應用程式，也就是應用程式特定的應用程式。</span><span class="sxs-lookup"><span data-stu-id="4c20f-144">TIAS means Transport Independent Application Specific while AS means Application Specific.</span></span> <span data-ttu-id="4c20f-145">這些是 RFC3890 中指定的 SIP 選項。</span><span class="sxs-lookup"><span data-stu-id="4c20f-145">These are SIP options specified in RFC3890.</span></span>
    
10. <span data-ttu-id="4c20f-146">在同一個畫面上，再向下滾動。</span><span class="sxs-lookup"><span data-stu-id="4c20f-146">On the same screen, scroll down further.</span></span> <span data-ttu-id="4c20f-147">在 [SIP 設定檔的主幹特定設定] 底下，選取 [ **為語音和影片通話預先提供支援** ]，並將其設定為 **強制 (在必要時插入 MTP)** ] 選項。</span><span class="sxs-lookup"><span data-stu-id="4c20f-147">Under the SIP Profile's Trunk Specific Configuration, select **Early Offer Support for voice and video calls** and set it to the **Mandatory (insert MTP if needed)** option.</span></span> <span data-ttu-id="4c20f-148">這可讓 CUCM 使用早期的提供來設定外寄的 SIP 呼叫。</span><span class="sxs-lookup"><span data-stu-id="4c20f-148">This will enable CUCM to set up an outgoing SIP call with Early Offer.</span></span> <span data-ttu-id="4c20f-149">CUCM 8.5 中的一項新功能是支援外寄通話設定，但不需要 (MTP) 的媒體終止點。</span><span class="sxs-lookup"><span data-stu-id="4c20f-149">One new feature in CUCM 8.5 and beyond is that it supports outgoing call setup with Early Offer without requiring Media Termination Point (MTP).</span></span>
    
11. <span data-ttu-id="4c20f-150">確認在 [SIP 選項 ping] 區段中，選取 [啟用選項 Ping 以監視目標狀態的主幹，且服務類型為 ' None (預設) '] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="4c20f-150">Verify that in the SIP Options ping section, the box is checked next to "Enable OPTIONS Ping to monitor destination status for Trunks with Service Type 'None (Default)'."</span></span>
    
12. <span data-ttu-id="4c20f-151">完成後，按一下 [ **新增**]。</span><span class="sxs-lookup"><span data-stu-id="4c20f-151">When you are finished, click on **Add New**.</span></span>
    
13. <span data-ttu-id="4c20f-152">流覽 Cisco 統一 CM 管理- \> 裝置- \> 主幹。</span><span class="sxs-lookup"><span data-stu-id="4c20f-152">Navigate to Cisco Unified CM Administration-\>Device-\>Trunk.</span></span> 
    
14. <span data-ttu-id="4c20f-153">將裝置通訊協定設定為 SIP，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="4c20f-153">Set the Device Protocol to SIP and press **Next**.</span></span>
    
15. <span data-ttu-id="4c20f-154">在 [裝置資訊] 底下，將裝置名稱和描述設定 (可能是 SfBVideoInterop_SIPTrunk) 之類的專案，並將媒體資源群組清單設為包含適當媒體資源的 MRGL。</span><span class="sxs-lookup"><span data-stu-id="4c20f-154">Under Device Information, Set the Device Name and Description (probably to something like SfBVideoInterop_SIPTrunk), and set the Media Resource Group List to an MRGL that contains the right media resources.</span></span> 
    
16. <span data-ttu-id="4c20f-155">進一步向下方滾動。</span><span class="sxs-lookup"><span data-stu-id="4c20f-155">Scroll down further.</span></span> <span data-ttu-id="4c20f-156">不需要 (MTP) 的媒體終止點，如果尚未取消核取，請將其取消勾選。</span><span class="sxs-lookup"><span data-stu-id="4c20f-156">Media Termination Point (MTP) is not required for Video Calls, if it is not already unchecked, uncheck it.</span></span> <span data-ttu-id="4c20f-157">請選取在所有使用中的 **整合 CM 節點上執行** 的選項。</span><span class="sxs-lookup"><span data-stu-id="4c20f-157">Check the option to **Run on all active Unified CM Nodes**.</span></span> <span data-ttu-id="4c20f-158">請注意，您應該將所有的 CUCM 節點新增至商務用 Skype 伺服器設定。</span><span class="sxs-lookup"><span data-stu-id="4c20f-158">Please note that you should add all CUCM nodes to the Skype for Business Server configuration.</span></span>
    
17. <span data-ttu-id="4c20f-159">進一步向下方滾動。</span><span class="sxs-lookup"><span data-stu-id="4c20f-159">Scroll down further.</span></span> <span data-ttu-id="4c20f-160">如圖所示，設定來電和連接的通訊雙方設定選項。</span><span class="sxs-lookup"><span data-stu-id="4c20f-160">Set the Inbound Calls and Connected Party Settings options as shown.</span></span>
    
    |<span data-ttu-id="4c20f-161">**參數**</span><span class="sxs-lookup"><span data-stu-id="4c20f-161">**Parameter**</span></span>|<span data-ttu-id="4c20f-162">**建議的設定**</span><span class="sxs-lookup"><span data-stu-id="4c20f-162">**Recommended setting**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="4c20f-163">呼叫搜尋空間</span><span class="sxs-lookup"><span data-stu-id="4c20f-163">Calling Search Space</span></span>  <br/> |<span data-ttu-id="4c20f-164">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="4c20f-164">CSS_SfBVideoInterop</span></span>  <br/> |
    |<span data-ttu-id="4c20f-165">呼叫搜尋空間 AAR</span><span class="sxs-lookup"><span data-stu-id="4c20f-165">AAR Calling Search Space</span></span>  <br/> |<span data-ttu-id="4c20f-166">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="4c20f-166">CSS_SfBVideoInterop</span></span>  <br/> |
    |<span data-ttu-id="4c20f-167">連接的當事方轉換 CSS</span><span class="sxs-lookup"><span data-stu-id="4c20f-167">Connected Party Transformation CSS</span></span>  <br/> |<span data-ttu-id="4c20f-168">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="4c20f-168">CSS_SfBVideoInterop</span></span>  <br/> |
   
18. <span data-ttu-id="4c20f-169">進一步向下方滾動。</span><span class="sxs-lookup"><span data-stu-id="4c20f-169">Scroll down further.</span></span> <span data-ttu-id="4c20f-170">在 SIP 主幹設定的 [SIP 資訊目的] 區段中，指定 VIS 集區的 FQDN 或集區中個別 VIS 伺服器的 IP 位址 (新增多個專案) 。</span><span class="sxs-lookup"><span data-stu-id="4c20f-170">Under the SIP Information Destination section of the SIP Trunk configuration, specify the VIS Pool's FQDN or the IP address of individual VIS servers in the pool (adding multiple entries).</span></span> <span data-ttu-id="4c20f-171">在 [目的地埠] 中，指定 VIS 正在接聽的埠，以供來自 CUCM 的連線 (預設值為 6001) 。</span><span class="sxs-lookup"><span data-stu-id="4c20f-171">In the Destination Port specify the Port that VIS is listening at for connections from CUCM (the default is 6001).</span></span> <span data-ttu-id="4c20f-172">此外，請指定您先前建立的 SIP 主幹安全性設定檔和 SIP 設定檔（如圖所示）。</span><span class="sxs-lookup"><span data-stu-id="4c20f-172">Also specify the SIP Trunk security profile and SIP profile you created earlier, as shown.</span></span>
    
    |<span data-ttu-id="4c20f-173">**參數**</span><span class="sxs-lookup"><span data-stu-id="4c20f-173">**Parameter**</span></span>|<span data-ttu-id="4c20f-174">**建議的設定**</span><span class="sxs-lookup"><span data-stu-id="4c20f-174">**Recommended setting**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="4c20f-175">SIP 主幹安全性設定檔</span><span class="sxs-lookup"><span data-stu-id="4c20f-175">SIP Trunk Security Profile</span></span>  <br/> |<span data-ttu-id="4c20f-176">SfBVideoInterop_SecurityProfile</span><span class="sxs-lookup"><span data-stu-id="4c20f-176">SfBVideoInterop_SecurityProfile</span></span>  <br/> |
    |<span data-ttu-id="4c20f-177">重新路由呼叫搜尋空間</span><span class="sxs-lookup"><span data-stu-id="4c20f-177">Rerouting Calling Search Space</span></span>  <br/> |<span data-ttu-id="4c20f-178">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="4c20f-178">CSS_SfBVideoInterop</span></span>  <br/> |
    |<span data-ttu-id="4c20f-179">對話方塊外參考呼叫搜尋空間</span><span class="sxs-lookup"><span data-stu-id="4c20f-179">Out-of-Dialog Refer Calling Search Space</span></span>  <br/> |<span data-ttu-id="4c20f-180">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="4c20f-180">CSS_SfBVideoInterop</span></span>  <br/> |
    |<span data-ttu-id="4c20f-181">訂閱通話搜尋空間</span><span class="sxs-lookup"><span data-stu-id="4c20f-181">Subscribe Calling Search Space</span></span>  <br/> |<span data-ttu-id="4c20f-182">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="4c20f-182">CSS_SfBVideoInterop</span></span>  <br/> |
    |<span data-ttu-id="4c20f-183">SIP 設定檔</span><span class="sxs-lookup"><span data-stu-id="4c20f-183">SIP Profile</span></span>  <br/> |<span data-ttu-id="4c20f-184">SfBVideoInterop_SIPProfile</span><span class="sxs-lookup"><span data-stu-id="4c20f-184">SfBVideoInterop_SIPProfile</span></span>  <br/> |
    |<span data-ttu-id="4c20f-185">DTMF 信號方法</span><span class="sxs-lookup"><span data-stu-id="4c20f-185">DTMF Signaling Method</span></span>  <br/> |<span data-ttu-id="4c20f-186">RFC 2833</span><span class="sxs-lookup"><span data-stu-id="4c20f-186">RFC 2833</span></span>  <br/> |
   
19.  <span data-ttu-id="4c20f-187">進一步向下方滾動。</span><span class="sxs-lookup"><span data-stu-id="4c20f-187">Scroll down further.</span></span> <span data-ttu-id="4c20f-188">視您的系統設定記錄資訊。</span><span class="sxs-lookup"><span data-stu-id="4c20f-188">Set the Recording Information as appropriate for your system.</span></span> <span data-ttu-id="4c20f-189">將其保留為 [ **無**] 是很好的方式。</span><span class="sxs-lookup"><span data-stu-id="4c20f-189">It's fine to leave it set to **None**.</span></span> 
    
20. <span data-ttu-id="4c20f-190">完成後，按一下 [ **新增**]。</span><span class="sxs-lookup"><span data-stu-id="4c20f-190">When you are finished, click on **Add New**.</span></span>
    
21. <span data-ttu-id="4c20f-191">流覽至 Cisco 統一 CM 管理- \> 通話路由 \> 傳送/尋找路由 \> 模式。</span><span class="sxs-lookup"><span data-stu-id="4c20f-191">Navigate to Cisco Unified CM Administration-\>Call Routing-\>Route/Hunt-\>Route pattern.</span></span>
    
22. <span data-ttu-id="4c20f-192">在 [路由模式設定] 畫面中，輸入如下所示的模式定義參數。</span><span class="sxs-lookup"><span data-stu-id="4c20f-192">In the Route Pattern Configuration screen, enter the Pattern definition parameters shown below.</span></span> <span data-ttu-id="4c20f-193">向下滾動至「所叫的協力廠商轉換」區段，然後設定遮罩為 [已顯示]，然後在完成時按一下 [ **新增** ]。</span><span class="sxs-lookup"><span data-stu-id="4c20f-193">Scroll down to the Called Party Transformations section and set the mask as shown, and then click on **Add New** when finished.</span></span>
    
    |<span data-ttu-id="4c20f-194">**參數**</span><span class="sxs-lookup"><span data-stu-id="4c20f-194">**Parameter**</span></span>|<span data-ttu-id="4c20f-195">**建議的設定**</span><span class="sxs-lookup"><span data-stu-id="4c20f-195">**Recommended setting**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="4c20f-196">路由模式</span><span class="sxs-lookup"><span data-stu-id="4c20f-196">Route Pattern</span></span>  <br/> |<span data-ttu-id="4c20f-197">7779999</span><span class="sxs-lookup"><span data-stu-id="4c20f-197">7779999</span></span>  <br/> |
    |<span data-ttu-id="4c20f-198">路由分割區</span><span class="sxs-lookup"><span data-stu-id="4c20f-198">Route Partition</span></span>  <br/> |<span data-ttu-id="4c20f-199">SfBVideoInterop_RoutePartition</span><span class="sxs-lookup"><span data-stu-id="4c20f-199">SfBVideoInterop_RoutePartition</span></span>  <br/> |
    |<span data-ttu-id="4c20f-200">描述</span><span class="sxs-lookup"><span data-stu-id="4c20f-200">Description</span></span>  <br/> |<span data-ttu-id="4c20f-201">SfBVideoInterop 的分割區</span><span class="sxs-lookup"><span data-stu-id="4c20f-201">Partition for SfBVideoInterop</span></span>  <br/> |
    |<span data-ttu-id="4c20f-202">閘道/路由清單</span><span class="sxs-lookup"><span data-stu-id="4c20f-202">Gateway/Route List</span></span>  <br/> |<span data-ttu-id="4c20f-203">SfBVideoInterop_SIPTrunk</span><span class="sxs-lookup"><span data-stu-id="4c20f-203">SfBVideoInterop_SIPTrunk</span></span>  <br/> |
    |<span data-ttu-id="4c20f-204">呼叫方轉換遮罩</span><span class="sxs-lookup"><span data-stu-id="4c20f-204">Called Party Transform Mask</span></span>  <br/> |<span data-ttu-id="4c20f-205">+ 14257779999</span><span class="sxs-lookup"><span data-stu-id="4c20f-205">+14257779999</span></span>  <br/> |
   
23. <span data-ttu-id="4c20f-206">流覽至 Cisco 統一 CM 管理- \> 呼叫路由- \> SIP 路由模式。</span><span class="sxs-lookup"><span data-stu-id="4c20f-206">Navigate to Cisco Unified CM Administration-\>Call Routing-\>SIP Route Pattern.</span></span>
    
24. <span data-ttu-id="4c20f-207">在 [SIP 路由模式設定] 畫面中，設定 [模式定義] 選項（如圖所示），然後按一下 [ **新增**]。</span><span class="sxs-lookup"><span data-stu-id="4c20f-207">In the SIP Route Pattern Configuration screen, set the Pattern Definition options as shown, and click on **Add New**.</span></span>
    
    |<span data-ttu-id="4c20f-208">**參數**</span><span class="sxs-lookup"><span data-stu-id="4c20f-208">**Parameter**</span></span>|<span data-ttu-id="4c20f-209">**建議的設定**</span><span class="sxs-lookup"><span data-stu-id="4c20f-209">**Recommended setting**</span></span>|
    |:-----|:-----|
    | <span data-ttu-id="4c20f-210">模式用法</span><span class="sxs-lookup"><span data-stu-id="4c20f-210">Pattern Usage</span></span> <br/> |<span data-ttu-id="4c20f-211">網域路由</span><span class="sxs-lookup"><span data-stu-id="4c20f-211">Domain Routing</span></span>  <br/> |
    |<span data-ttu-id="4c20f-212">IPv4 模式</span><span class="sxs-lookup"><span data-stu-id="4c20f-212">IPv4 Pattern</span></span>  <br/> |<span data-ttu-id="4c20f-213">使用 IPv6 時，contoso.com (留下空白) </span><span class="sxs-lookup"><span data-stu-id="4c20f-213">contoso.com (leave blank if using IPv6)</span></span>  <br/> |
    |<span data-ttu-id="4c20f-214">IPv6 模式</span><span class="sxs-lookup"><span data-stu-id="4c20f-214">IPv6 Pattern</span></span>  <br/> |<span data-ttu-id="4c20f-215">使用 IPv4 時，contoso.com (留下空白) </span><span class="sxs-lookup"><span data-stu-id="4c20f-215">contoso.com (leave blank if using IPv4)</span></span>  <br/> |
    |<span data-ttu-id="4c20f-216">描述</span><span class="sxs-lookup"><span data-stu-id="4c20f-216">Description</span></span>  <br/> |<span data-ttu-id="4c20f-217">SIPRoute 到 mediarv 的模式</span><span class="sxs-lookup"><span data-stu-id="4c20f-217">SIPRoute Pattern to mediarv</span></span>  <br/> |
    |<span data-ttu-id="4c20f-218">路由分割區</span><span class="sxs-lookup"><span data-stu-id="4c20f-218">Route Partition</span></span>  <br/> |<span data-ttu-id="4c20f-219">SfBVideoInterop_RoutePartition</span><span class="sxs-lookup"><span data-stu-id="4c20f-219">SfBVideoInterop_RoutePartition</span></span>  <br/> |
    |<span data-ttu-id="4c20f-220">SIP 主幹/路由清單</span><span class="sxs-lookup"><span data-stu-id="4c20f-220">SIP Trunk/Route List</span></span>  <br/> |<span data-ttu-id="4c20f-221">SfBVideoInterop_SIPTrunk</span><span class="sxs-lookup"><span data-stu-id="4c20f-221">SfBVideoInterop_SIPTrunk</span></span>  <br/> |
    |<span data-ttu-id="4c20f-222">封鎖模式] 核取方塊</span><span class="sxs-lookup"><span data-stu-id="4c20f-222">Block Pattern checkbox</span></span>  <br/> |<span data-ttu-id="4c20f-223">保留未勾選</span><span class="sxs-lookup"><span data-stu-id="4c20f-223">leave unchecked</span></span>  <br/> |
   
25. <span data-ttu-id="4c20f-224">如果您已從預設設定變更音訊或影片位元速率，您必須將其恢復為預設值。</span><span class="sxs-lookup"><span data-stu-id="4c20f-224">If you have changed the audio or video bit rates from the default settings, you will need to return them to the defaults.</span></span> <span data-ttu-id="4c20f-225">若要設定 Audio/Video 通話的位元速率，請流覽至 Cisco 統一 CM 管理- \> 系統- \> 地區資訊- \> 地區。</span><span class="sxs-lookup"><span data-stu-id="4c20f-225">To set the bit rate for Audio/Video calls, navigate to Cisco Unified CM Administration-\>System-\>Region Information-\>Region.</span></span> <span data-ttu-id="4c20f-226">預設值如下所示：</span><span class="sxs-lookup"><span data-stu-id="4c20f-226">The defaults are shown below for reference:</span></span>
    
    |<span data-ttu-id="4c20f-227">**參數**</span><span class="sxs-lookup"><span data-stu-id="4c20f-227">**Parameter**</span></span>|<span data-ttu-id="4c20f-228">**建議的設定**</span><span class="sxs-lookup"><span data-stu-id="4c20f-228">**Recommended setting**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="4c20f-229">地區</span><span class="sxs-lookup"><span data-stu-id="4c20f-229">Region</span></span>  <br/> |<span data-ttu-id="4c20f-230">預設</span><span class="sxs-lookup"><span data-stu-id="4c20f-230">Default</span></span>  <br/> |
    |<span data-ttu-id="4c20f-231">音訊編解碼器偏好清單</span><span class="sxs-lookup"><span data-stu-id="4c20f-231">Audio Codec Preference List</span></span>  <br/> |<span data-ttu-id="4c20f-232">系統預設值</span><span class="sxs-lookup"><span data-stu-id="4c20f-232">System Default</span></span>  <br/> |
    |<span data-ttu-id="4c20f-233">音訊位元速率上限</span><span class="sxs-lookup"><span data-stu-id="4c20f-233">Maximum Audio Bit Rate</span></span>  <br/> |<span data-ttu-id="4c20f-234">64 kbps (g.722，g.711) </span><span class="sxs-lookup"><span data-stu-id="4c20f-234">64 kbps (G.722, G.711)</span></span>  <br/> |
    |<span data-ttu-id="4c20f-235">影片通話的最長會話位元速率</span><span class="sxs-lookup"><span data-stu-id="4c20f-235">Maximum Session Bit Rate for Video Calls</span></span>  <br/> |<span data-ttu-id="4c20f-236">200000 kbps</span><span class="sxs-lookup"><span data-stu-id="4c20f-236">200000 kbps</span></span>  <br/> |
    |<span data-ttu-id="4c20f-237">會話位元速率上限</span><span class="sxs-lookup"><span data-stu-id="4c20f-237">Maximum Session Bit Rate</span></span>  <br/> |<span data-ttu-id="4c20f-238">2000000000 kbps</span><span class="sxs-lookup"><span data-stu-id="4c20f-238">2000000000 kbps</span></span>  <br/> |
   
<span data-ttu-id="4c20f-239">此時，CUCM 影片閘道已設定為搭配 VIS 使用。</span><span class="sxs-lookup"><span data-stu-id="4c20f-239">At this point the CUCM video gateway is configured to work with the VIS.</span></span> <span data-ttu-id="4c20f-240">在您想要整合的每個 VTC 中，都需要進行對應的設定。</span><span class="sxs-lookup"><span data-stu-id="4c20f-240">Corresponding configuration will need to be done on each VTC you wish to integrate.</span></span>
> [!NOTE]
> <span data-ttu-id="4c20f-241">若要改善復原能力，您可以設定此 CUCM 閘道，以與第二個影片交互操作伺服器或 VIS 集區搭配使用。</span><span class="sxs-lookup"><span data-stu-id="4c20f-241">To improve resiliency, you may want to configure this CUCM gateway to work with a second Video Interop Server or VIS pool.</span></span> <span data-ttu-id="4c20f-242">如需詳細資訊，請參閱 [恢復機制](../../plan-your-deployment/video-interop-server.md#resiliency) 。</span><span class="sxs-lookup"><span data-stu-id="4c20f-242">See [Resiliency mechanisms](../../plan-your-deployment/video-interop-server.md#resiliency) for more information.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="4c20f-243">另請參閱</span><span class="sxs-lookup"><span data-stu-id="4c20f-243">See also</span></span>

[<span data-ttu-id="4c20f-244">設定 VTC 以搭配商務用 Skype 伺服器進行交互操作</span><span class="sxs-lookup"><span data-stu-id="4c20f-244">Configure a VTC for Interoperation with Skype for Business Server</span></span>](configure-a-vtc-for-interoperation.md)
