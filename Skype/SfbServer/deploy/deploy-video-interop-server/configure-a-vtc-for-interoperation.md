---
title: 設定 VTC 以搭配商務用 Skype 伺服器進行交互操作
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
ms.assetid: 1016aed6-99fe-452e-8b20-81c814808c3d
description: 摘要：將 VTC 裝置設定為搭配商務用 Skype Server 使用。
ms.openlocfilehash: 7697fd9f33a4fece4871b056a05264ece888d357
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802073"
---
# <a name="configure-a-vtc-for-interoperation-with-skype-for-business-server"></a><span data-ttu-id="c337c-103">設定 VTC 以搭配商務用 Skype 伺服器進行交互操作</span><span class="sxs-lookup"><span data-stu-id="c337c-103">Configure a VTC for Interoperation with Skype for Business Server</span></span>
 
<span data-ttu-id="c337c-104">**摘要：** 設定 VTC 裝置與商務用 Skype Server 搭配使用。</span><span class="sxs-lookup"><span data-stu-id="c337c-104">**Summary:** Configure the VTC devices to work with Skype for Business Server.</span></span>
  
<span data-ttu-id="c337c-105">您必須針對將透過 SIP 主幹和 Cisco 整合通訊管理員 (CallManager，或 CUCM) 視頻閘道來連線至商務用 Skype VIS server 的每個 VTC，執行下列設定自訂程式。</span><span class="sxs-lookup"><span data-stu-id="c337c-105">You will need to perform the following configuration customization procedures for each VTC that will connect to the Skype for Business VIS server through a SIP trunk and Cisco Unified Communications Manager (CallManager, or CUCM) video gateway.</span></span>
  
<span data-ttu-id="c337c-106">這裡所述的設定只是 CUCM 如何設定為搭配 VIS 使用的範例。</span><span class="sxs-lookup"><span data-stu-id="c337c-106">The settings described here are meant only as examples of how CUCM can be configured to work with a VIS.</span></span> <span data-ttu-id="c337c-107">其他設定和/或替代 CUCM 功能的使用方式也可以用來達到相同的結果。</span><span class="sxs-lookup"><span data-stu-id="c337c-107">Other settings and/or usages of alternate CUCM functionality could also be used to achieve the same result.</span></span> <span data-ttu-id="c337c-108">不建議使用特定案例的最佳設定。</span><span class="sxs-lookup"><span data-stu-id="c337c-108">No recommendation is implied as to the optimal configuration for a particular scenario.</span></span>
  
### <a name="configure-a-vtc-registered-with-cucm"></a><span data-ttu-id="c337c-109">設定 VTC 註冊的 CUCM</span><span class="sxs-lookup"><span data-stu-id="c337c-109">Configure a VTC registered with CUCM</span></span>

1. <span data-ttu-id="c337c-110">登入 Cisco VTC 裝置，並流覽至 [設定- \> 系統設定-布建] \> 。</span><span class="sxs-lookup"><span data-stu-id="c337c-110">Log in to the Cisco VTC device and navigate to Configuration-\>System Configuration-\>Provisioning.</span></span>
    
2. <span data-ttu-id="c337c-111">請確認下列設定，並視需要進行修正：</span><span class="sxs-lookup"><span data-stu-id="c337c-111">Verify the following settings, correcting as needed:</span></span> 
    
   |<span data-ttu-id="c337c-112">**參數**</span><span class="sxs-lookup"><span data-stu-id="c337c-112">**Parameter**</span></span>|<span data-ttu-id="c337c-113">**建議的設定**</span><span class="sxs-lookup"><span data-stu-id="c337c-113">**Recommended setting**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="c337c-114">布建模式</span><span class="sxs-lookup"><span data-stu-id="c337c-114">Provisioning Mode</span></span>  <br/> | <span data-ttu-id="c337c-115">CUCM</span><span class="sxs-lookup"><span data-stu-id="c337c-115">CUCM</span></span> <br/> |
   |<span data-ttu-id="c337c-116">ExternalManager 位址</span><span class="sxs-lookup"><span data-stu-id="c337c-116">ExternalManager Address</span></span>  <br/> | <span data-ttu-id="c337c-117">CUCM 的 FQDN</span><span class="sxs-lookup"><span data-stu-id="c337c-117">CUCM's FQDN</span></span> <br/> |
   | <span data-ttu-id="c337c-118">ExternalManager 網域</span><span class="sxs-lookup"><span data-stu-id="c337c-118">ExternalManager Domain</span></span> <br/> |<span data-ttu-id="c337c-119">CUCM 所在的網域</span><span class="sxs-lookup"><span data-stu-id="c337c-119">CUCM's domain</span></span>  <br/> |
   
3. <span data-ttu-id="c337c-120">流覽至 [設定- \> 系統設定- \> 網路]。</span><span class="sxs-lookup"><span data-stu-id="c337c-120">Navigate to Configuration-\>System Configuration-\>Network.</span></span>
    
4. <span data-ttu-id="c337c-121">請確認下列設定，並視需要進行修正：</span><span class="sxs-lookup"><span data-stu-id="c337c-121">Verify the following settings, correcting as needed:</span></span> 
    
   |<span data-ttu-id="c337c-122">**參數**</span><span class="sxs-lookup"><span data-stu-id="c337c-122">**Parameter**</span></span>|<span data-ttu-id="c337c-123">**建議的設定**</span><span class="sxs-lookup"><span data-stu-id="c337c-123">**Recommended setting**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="c337c-124">DNS 功能變數名稱</span><span class="sxs-lookup"><span data-stu-id="c337c-124">DNS Domain Name</span></span>  <br/> | <span data-ttu-id="c337c-125">CUCM 的功能變數名稱</span><span class="sxs-lookup"><span data-stu-id="c337c-125">CUCM's Domain name</span></span> <br/> |
   |<span data-ttu-id="c337c-126">DNS 伺服器1位址</span><span class="sxs-lookup"><span data-stu-id="c337c-126">DNS Server 1 Address</span></span>  <br/> | <span data-ttu-id="c337c-127">您想要的 DNS 伺服器位址</span><span class="sxs-lookup"><span data-stu-id="c337c-127">your desired DNS server address</span></span> <br/> |
   
5. <span data-ttu-id="c337c-128">流覽至 [設定- \> 系統設定- \> 網路服務]。</span><span class="sxs-lookup"><span data-stu-id="c337c-128">Navigate to Configuration-\>System Configuration-\>Network Services.</span></span> <span data-ttu-id="c337c-129">確定已關閉 H 323 模式，且已開啟 SIP 模式。</span><span class="sxs-lookup"><span data-stu-id="c337c-129">Ensure that H.323 mode is turned off and SIP mode is turned on.</span></span> 
    
6. <span data-ttu-id="c337c-130">當端點已向 CUCM 註冊時，會自動設定這些選項。</span><span class="sxs-lookup"><span data-stu-id="c337c-130">These options are set automatically when the endpoint is registered with CUCM.</span></span> <span data-ttu-id="c337c-131">請確認下列設定，並視需要進行修正：</span><span class="sxs-lookup"><span data-stu-id="c337c-131">Verify the following settings, correcting as needed:</span></span> 
    
   |<span data-ttu-id="c337c-132">**參數**</span><span class="sxs-lookup"><span data-stu-id="c337c-132">**Parameter**</span></span>|<span data-ttu-id="c337c-133">**建議的設定**</span><span class="sxs-lookup"><span data-stu-id="c337c-133">**Recommended setting**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="c337c-134">上的323模式</span><span class="sxs-lookup"><span data-stu-id="c337c-134">H.323 Mode</span></span>  <br/> | <span data-ttu-id="c337c-135">關閉</span><span class="sxs-lookup"><span data-stu-id="c337c-135">Off</span></span> <br/> |
   |<span data-ttu-id="c337c-136">HTTP 模式</span><span class="sxs-lookup"><span data-stu-id="c337c-136">HTTP Mode</span></span>  <br/> | <span data-ttu-id="c337c-137">開啟</span><span class="sxs-lookup"><span data-stu-id="c337c-137">On</span></span> <br/> |
   | <span data-ttu-id="c337c-138">SIP 模式</span><span class="sxs-lookup"><span data-stu-id="c337c-138">SIP Mode</span></span> <br/> | <span data-ttu-id="c337c-139">開啟</span><span class="sxs-lookup"><span data-stu-id="c337c-139">On</span></span> <br/> |
   |<span data-ttu-id="c337c-140">Telnet 模式</span><span class="sxs-lookup"><span data-stu-id="c337c-140">Telnet Mode</span></span>  <br/> | <span data-ttu-id="c337c-141">開啟</span><span class="sxs-lookup"><span data-stu-id="c337c-141">On</span></span> <br/> |
   |<span data-ttu-id="c337c-142">WelcomeText</span><span class="sxs-lookup"><span data-stu-id="c337c-142">WelcomeText</span></span>  <br/> | <span data-ttu-id="c337c-143">開啟</span><span class="sxs-lookup"><span data-stu-id="c337c-143">On</span></span> <br/> |
   |<span data-ttu-id="c337c-144">XMLAPI 模式</span><span class="sxs-lookup"><span data-stu-id="c337c-144">XMLAPI Mode</span></span>  <br/> | <span data-ttu-id="c337c-145">開啟</span><span class="sxs-lookup"><span data-stu-id="c337c-145">On</span></span> <br/> |
   
7. <span data-ttu-id="c337c-146">流覽至 [設定- \> 系統設定- \> SIP]。</span><span class="sxs-lookup"><span data-stu-id="c337c-146">Navigate to Configuration-\>System Configuration-\>SIP.</span></span>
    
8. <span data-ttu-id="c337c-147">請確認下列設定，並視需要進行修正：</span><span class="sxs-lookup"><span data-stu-id="c337c-147">Verify the following settings, correcting as needed:</span></span> 
    
   |<span data-ttu-id="c337c-148">**參數**</span><span class="sxs-lookup"><span data-stu-id="c337c-148">**Parameter**</span></span>|<span data-ttu-id="c337c-149">**建議的設定**</span><span class="sxs-lookup"><span data-stu-id="c337c-149">**Recommended setting**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="c337c-150">設定檔 1-DefaultTransport</span><span class="sxs-lookup"><span data-stu-id="c337c-150">Profile 1 - DefaultTransport</span></span>  <br/> | <span data-ttu-id="c337c-151">TCP</span><span class="sxs-lookup"><span data-stu-id="c337c-151">TCP</span></span> <br/> |
   |<span data-ttu-id="c337c-152">設定檔 1-輸出</span><span class="sxs-lookup"><span data-stu-id="c337c-152">Profile 1 - Outbound</span></span>  <br/> | <span data-ttu-id="c337c-153">關閉</span><span class="sxs-lookup"><span data-stu-id="c337c-153">Off</span></span> <br/> |
   |<span data-ttu-id="c337c-154">設定檔 1-TlsVerify</span><span class="sxs-lookup"><span data-stu-id="c337c-154">Profile 1 - TlsVerify</span></span>  <br/> | <span data-ttu-id="c337c-155">開啟</span><span class="sxs-lookup"><span data-stu-id="c337c-155">On</span></span> <br/> |
   |<span data-ttu-id="c337c-156">設定檔 1-類型</span><span class="sxs-lookup"><span data-stu-id="c337c-156">Profile 1 - Type</span></span>  <br/> | <span data-ttu-id="c337c-157">Cisco</span><span class="sxs-lookup"><span data-stu-id="c337c-157">Cisco</span></span> <br/> |
   |<span data-ttu-id="c337c-158">設定檔 1-URI</span><span class="sxs-lookup"><span data-stu-id="c337c-158">Profile 1 - URI</span></span>  <br/> | <span data-ttu-id="c337c-159">在 CUCM 註冊時自動指派</span><span class="sxs-lookup"><span data-stu-id="c337c-159">Automatically assigned at CUCM registration</span></span> <br/> |
   |<span data-ttu-id="c337c-160">Proxy 1-位址</span><span class="sxs-lookup"><span data-stu-id="c337c-160">Proxy 1 - Address</span></span>  <br/> |<span data-ttu-id="c337c-161">CUCM 的主機名稱</span><span class="sxs-lookup"><span data-stu-id="c337c-161">The host name of the CUCM</span></span>  <br/> |
   
<span data-ttu-id="c337c-162">VTC 現在已設定為交互操作。</span><span class="sxs-lookup"><span data-stu-id="c337c-162">The VTC is now configured for interoperation.</span></span> <span data-ttu-id="c337c-163">在服務可以開始之前，請先在 CUCM 側執行一些最後的步驟。</span><span class="sxs-lookup"><span data-stu-id="c337c-163">Before service can begin, there are final steps to perform on the CUCM side.</span></span>
### <a name="configure-vtc-devices-on-cucm"></a><span data-ttu-id="c337c-164">在 CUCM 上設定 VTC 裝置</span><span class="sxs-lookup"><span data-stu-id="c337c-164">Configure VTC devices on CUCM</span></span>

1. <span data-ttu-id="c337c-165">登入 CUCM 並流覽至 Cisco 統一 CM 管理- \> 裝置- \> 電話- \> 尋找。</span><span class="sxs-lookup"><span data-stu-id="c337c-165">Log in to CUCM and Navigate to Cisco Unified CM Administration-\>Device-\>Phone-\>Find.</span></span> 
    
2. <span data-ttu-id="c337c-166">選取要設定的 VTC 裝置。</span><span class="sxs-lookup"><span data-stu-id="c337c-166">Select the VTC device to be configured.</span></span> <span data-ttu-id="c337c-167">在 [電話設定] 畫面上驗證下列設定，並視需要進行修正。</span><span class="sxs-lookup"><span data-stu-id="c337c-167">Verify the following settings on the Phone Configuration screen, correcting as needed.</span></span> <span data-ttu-id="c337c-168">變更或驗證這些設定後，按一下 [ **儲存**]。</span><span class="sxs-lookup"><span data-stu-id="c337c-168">Once these settings have been changed or verified, click on **Save**.</span></span>
    
   |<span data-ttu-id="c337c-169">**參數**</span><span class="sxs-lookup"><span data-stu-id="c337c-169">**Parameter**</span></span>|<span data-ttu-id="c337c-170">**建議的設定**</span><span class="sxs-lookup"><span data-stu-id="c337c-170">**Recommended setting**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="c337c-171">裝置資訊-電話按鈕範本</span><span class="sxs-lookup"><span data-stu-id="c337c-171">Device Information - Phone Button Template</span></span>  <br/> | <span data-ttu-id="c337c-172">標準 Cisco Telepresence 編解碼器 C40</span><span class="sxs-lookup"><span data-stu-id="c337c-172">Standard Cisco Telepresence Codec C40</span></span> <br/> |
   |<span data-ttu-id="c337c-173">裝置資訊-常見的電話設定檔</span><span class="sxs-lookup"><span data-stu-id="c337c-173">Device Information - Common Phone Profile</span></span>  <br/> | <span data-ttu-id="c337c-174">標準通用電話設定檔</span><span class="sxs-lookup"><span data-stu-id="c337c-174">Standard Common Phone Profile</span></span> <br/> |
   |<span data-ttu-id="c337c-175">裝置資訊-呼叫搜尋空間</span><span class="sxs-lookup"><span data-stu-id="c337c-175">Device Information - Calling Search Space</span></span>  <br/> | <span data-ttu-id="c337c-176">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="c337c-176">CSS_SfBVideoInterop</span></span> <br/> |
   |<span data-ttu-id="c337c-177">裝置資訊-AAR 呼叫搜尋空間</span><span class="sxs-lookup"><span data-stu-id="c337c-177">Device Information - AAR Calling Search Space</span></span>  <br/> | <span data-ttu-id="c337c-178">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="c337c-178">CSS_SfBVideoInterop</span></span> <br/> |
   |<span data-ttu-id="c337c-179">裝置資訊-媒體資源群組清單</span><span class="sxs-lookup"><span data-stu-id="c337c-179">Device Information - Media Resource Group List</span></span>  <br/> | <span data-ttu-id="c337c-180">MRGL_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="c337c-180">MRGL_SfBVideoInterop</span></span> <br/> |
   |<span data-ttu-id="c337c-181">通訊協定特定資訊-裝置安全性設定檔</span><span class="sxs-lookup"><span data-stu-id="c337c-181">Protocol Specific Information - Device Security Profile</span></span>  <br/> | <span data-ttu-id="c337c-182">Cisco Telepresence 編解碼器 C40</span><span class="sxs-lookup"><span data-stu-id="c337c-182">Cisco Telepresence Codec C40</span></span> <br/> |
   |<span data-ttu-id="c337c-183">通訊協定特定資訊-重新路由呼叫搜尋空間</span><span class="sxs-lookup"><span data-stu-id="c337c-183">Protocol Specific Information - Rerouting Calling Search Space</span></span>  <br/> | <span data-ttu-id="c337c-184">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="c337c-184">CSS_SfBVideoInterop</span></span> <br/> |
   |<span data-ttu-id="c337c-185">通訊協定特定資訊-訂閱通話搜尋空間</span><span class="sxs-lookup"><span data-stu-id="c337c-185">Protocol Specific Information - SUBSCRIBE Calling Search Space</span></span>  <br/> | <span data-ttu-id="c337c-186">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="c337c-186">CSS_SfBVideoInterop</span></span> <br/> |
   |<span data-ttu-id="c337c-187">通訊協定特定資訊-SIP 設定檔</span><span class="sxs-lookup"><span data-stu-id="c337c-187">Protocol Specific Information -SIP Profile</span></span>  <br/> | <span data-ttu-id="c337c-188">Telepresence 端點的標準 SIP 設定檔</span><span class="sxs-lookup"><span data-stu-id="c337c-188">Standard SIP Profile for Telepresence Endpoint</span></span> <br/> |
   
3. <span data-ttu-id="c337c-189">儲存 VTC 設定之後，請重新導覽裝置的電話設定畫面。</span><span class="sxs-lookup"><span data-stu-id="c337c-189">Once VTC configuration is saved, re-navigate to the Phone Configuration screen for the device.</span></span> <span data-ttu-id="c337c-190">在 [關聯] 群組中的畫面頂端，按一下影片交互操作的關聯。</span><span class="sxs-lookup"><span data-stu-id="c337c-190">At the top of the screen in the Association group, click on the association for the Video Interop.</span></span> <span data-ttu-id="c337c-191">這會顯示 [目錄號碼] 設定畫面。</span><span class="sxs-lookup"><span data-stu-id="c337c-191">This brings up the Directory Number Configuration screen.</span></span> 
    
4. <span data-ttu-id="c337c-192">請確認下列設定，並視需要進行修正：</span><span class="sxs-lookup"><span data-stu-id="c337c-192">Verify the following settings, correcting as needed:</span></span> 
    
    <span data-ttu-id="c337c-193">進行適當的變更，如目錄號碼資訊和目錄編號設定所示。</span><span class="sxs-lookup"><span data-stu-id="c337c-193">Make the appropriate changes as shown to the Directory Number Information and the Directory Number Settings.</span></span>
    
   |<span data-ttu-id="c337c-194">**參數**</span><span class="sxs-lookup"><span data-stu-id="c337c-194">**Parameter**</span></span>|<span data-ttu-id="c337c-195">**建議的設定**</span><span class="sxs-lookup"><span data-stu-id="c337c-195">**Recommended setting**</span></span>|
   |:-----|:-----|
   | <span data-ttu-id="c337c-196">目錄號碼資訊-路由分割區</span><span class="sxs-lookup"><span data-stu-id="c337c-196">Directory Number Information - Route Partition</span></span> <br/> | <span data-ttu-id="c337c-197">SfBVideoInterop_RoutePartition</span><span class="sxs-lookup"><span data-stu-id="c337c-197">SfBVideoInterop_RoutePartition</span></span> <br/> |
   |<span data-ttu-id="c337c-198">目錄號碼設定-呼叫搜尋空間</span><span class="sxs-lookup"><span data-stu-id="c337c-198">Directory Number Settings - Calling Search Space</span></span>  <br/> | <span data-ttu-id="c337c-199">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="c337c-199">CSS_SfBVideoInterop</span></span> <br/> |
   |<span data-ttu-id="c337c-200">MLPP 備用方和機密存取層級設定-MLPP 呼叫搜尋空間</span><span class="sxs-lookup"><span data-stu-id="c337c-200">MLPP Alternate Party and Confidential Access Level Settings - MLPP Calling Search Space</span></span>  <br/> | <span data-ttu-id="c337c-201">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="c337c-201">CSS_SfBVideoInterop</span></span> <br/> |
   |<span data-ttu-id="c337c-202">裝置顯示幕上的第1列 (來電者識別碼) </span><span class="sxs-lookup"><span data-stu-id="c337c-202">Line 1 on Device - Display (Caller ID)</span></span>  <br/> | <span data-ttu-id="c337c-203">視需要</span><span class="sxs-lookup"><span data-stu-id="c337c-203">As desired</span></span> <br/> |
   |<span data-ttu-id="c337c-204">裝置-ASCII 顯示幕上的第1列 (來電者識別碼) </span><span class="sxs-lookup"><span data-stu-id="c337c-204">Line 1 on Device - ASCII Display (Caller ID)</span></span>  <br/> | <span data-ttu-id="c337c-205">視需要</span><span class="sxs-lookup"><span data-stu-id="c337c-205">As desired</span></span> <br/> |
   
5. <span data-ttu-id="c337c-206">完成時，請滾到畫面的頂端，然後按 [ **儲存**]。</span><span class="sxs-lookup"><span data-stu-id="c337c-206">When finished, scroll to the top of the screen and press **Save**.</span></span> 
    
<span data-ttu-id="c337c-207">現在已完成此 VTC 裝置的設定。</span><span class="sxs-lookup"><span data-stu-id="c337c-207">Configuration is now complete for this VTC device.</span></span> <span data-ttu-id="c337c-208">您將需要針對企業中的其他 VTC 裝置重複此程式。</span><span class="sxs-lookup"><span data-stu-id="c337c-208">You will need to repeat this process for other VTC devices in your enterprise.</span></span>

