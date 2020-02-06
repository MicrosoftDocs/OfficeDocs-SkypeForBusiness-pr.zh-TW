---
title: 設定與商務用 Skype 伺服器交互操作的 VTC
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 1016aed6-99fe-452e-8b20-81c814808c3d
description: 摘要：設定 VTC 裝置以搭配商務用 Skype 伺服器使用。
ms.openlocfilehash: b266c8cc97898fe192ec023183a565b921d86949
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41798080"
---
# <a name="configure-a-vtc-for-interoperation-with-skype-for-business-server"></a><span data-ttu-id="1eecb-103">設定與商務用 Skype 伺服器交互操作的 VTC</span><span class="sxs-lookup"><span data-stu-id="1eecb-103">Configure a VTC for Interoperation with Skype for Business Server</span></span>
 
<span data-ttu-id="1eecb-104">**摘要：** 將 VTC 裝置設定為與商務用 Skype 伺服器搭配使用。</span><span class="sxs-lookup"><span data-stu-id="1eecb-104">**Summary:** Configure the VTC devices to work with Skype for Business Server.</span></span>
  
<span data-ttu-id="1eecb-105">您必須針對將透過 SIP 幹線與 Cisco 整合通訊管理員（CallManager 或 CUCM）視頻閘道連線到商務用 Skype VIS 伺服器的每個 VTC，執行下列設定自訂程式。</span><span class="sxs-lookup"><span data-stu-id="1eecb-105">You will need to perform the following configuration customization procedures for each VTC that will connect to the Skype for Business VIS server through a SIP trunk and Cisco Unified Communications Manager (CallManager, or CUCM) video gateway.</span></span>
  
<span data-ttu-id="1eecb-106">此處所述的設定僅做為如何設定 CUCM 以搭配 VIS 使用的範例。</span><span class="sxs-lookup"><span data-stu-id="1eecb-106">The settings described here are meant only as examples of how CUCM can be configured to work with a VIS.</span></span> <span data-ttu-id="1eecb-107">您也可以使用替代 CUCM 功能的其他設定和/或用法來達到相同的結果。</span><span class="sxs-lookup"><span data-stu-id="1eecb-107">Other settings and/or usages of alternate CUCM functionality could also be used to achieve the same result.</span></span> <span data-ttu-id="1eecb-108">針對特定案例，不建議使用最佳配置。</span><span class="sxs-lookup"><span data-stu-id="1eecb-108">No recommendation is implied as to the optimal configuration for a particular scenario.</span></span>
  
### <a name="configure-a-vtc-registered-with-cucm"></a><span data-ttu-id="1eecb-109">設定註冊至 CUCM 的 VTC</span><span class="sxs-lookup"><span data-stu-id="1eecb-109">Configure a VTC registered with CUCM</span></span>

1. <span data-ttu-id="1eecb-110">登入 Cisco VTC 裝置，然後流覽至 [配置-\>系統設定]\>-[設定]。</span><span class="sxs-lookup"><span data-stu-id="1eecb-110">Log in to the Cisco VTC device and navigate to Configuration-\>System Configuration-\>Provisioning.</span></span>
    
2. <span data-ttu-id="1eecb-111">確認下列設定，視需要修正：</span><span class="sxs-lookup"><span data-stu-id="1eecb-111">Verify the following settings, correcting as needed:</span></span> 
    
   |<span data-ttu-id="1eecb-112">**參數**</span><span class="sxs-lookup"><span data-stu-id="1eecb-112">**Parameter**</span></span>|<span data-ttu-id="1eecb-113">**建議的設定**</span><span class="sxs-lookup"><span data-stu-id="1eecb-113">**Recommended setting**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="1eecb-114">預配模式</span><span class="sxs-lookup"><span data-stu-id="1eecb-114">Provisioning Mode</span></span>  <br/> | <span data-ttu-id="1eecb-115">CUCM</span><span class="sxs-lookup"><span data-stu-id="1eecb-115">CUCM</span></span> <br/> |
   |<span data-ttu-id="1eecb-116">ExternalManager 位址</span><span class="sxs-lookup"><span data-stu-id="1eecb-116">ExternalManager Address</span></span>  <br/> | <span data-ttu-id="1eecb-117">CUCM 的 FQDN</span><span class="sxs-lookup"><span data-stu-id="1eecb-117">CUCM's FQDN</span></span> <br/> |
   | <span data-ttu-id="1eecb-118">ExternalManager 網域</span><span class="sxs-lookup"><span data-stu-id="1eecb-118">ExternalManager Domain</span></span> <br/> |<span data-ttu-id="1eecb-119">CUCM 的網域</span><span class="sxs-lookup"><span data-stu-id="1eecb-119">CUCM's domain</span></span>  <br/> |
   
3. <span data-ttu-id="1eecb-120">流覽至 [配置\>-系統設定\>-網路]。</span><span class="sxs-lookup"><span data-stu-id="1eecb-120">Navigate to Configuration-\>System Configuration-\>Network.</span></span>
    
4. <span data-ttu-id="1eecb-121">確認下列設定，視需要修正：</span><span class="sxs-lookup"><span data-stu-id="1eecb-121">Verify the following settings, correcting as needed:</span></span> 
    
   |<span data-ttu-id="1eecb-122">**參數**</span><span class="sxs-lookup"><span data-stu-id="1eecb-122">**Parameter**</span></span>|<span data-ttu-id="1eecb-123">**建議的設定**</span><span class="sxs-lookup"><span data-stu-id="1eecb-123">**Recommended setting**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="1eecb-124">DNS 功能變數名稱</span><span class="sxs-lookup"><span data-stu-id="1eecb-124">DNS Domain Name</span></span>  <br/> | <span data-ttu-id="1eecb-125">CUCM 的網功能變數名稱稱</span><span class="sxs-lookup"><span data-stu-id="1eecb-125">CUCM's Domain name</span></span> <br/> |
   |<span data-ttu-id="1eecb-126">DNS 伺服器1位址</span><span class="sxs-lookup"><span data-stu-id="1eecb-126">DNS Server 1 Address</span></span>  <br/> | <span data-ttu-id="1eecb-127">您想要的 DNS 伺服器位址</span><span class="sxs-lookup"><span data-stu-id="1eecb-127">your desired DNS server address</span></span> <br/> |
   
5. <span data-ttu-id="1eecb-128">流覽至 [配置\>-系統設定\>-網路服務]。</span><span class="sxs-lookup"><span data-stu-id="1eecb-128">Navigate to Configuration-\>System Configuration-\>Network Services.</span></span> <span data-ttu-id="1eecb-129">確定已關閉 H-323 模式，且已開啟 SIP 模式。</span><span class="sxs-lookup"><span data-stu-id="1eecb-129">Ensure that H.323 mode is turned off and SIP mode is turned on.</span></span> 
    
6. <span data-ttu-id="1eecb-130">當端點註冊至 CUCM 時，這些選項會自動設定。</span><span class="sxs-lookup"><span data-stu-id="1eecb-130">These options are set automatically when the endpoint is registered with CUCM.</span></span> <span data-ttu-id="1eecb-131">確認下列設定，視需要修正：</span><span class="sxs-lookup"><span data-stu-id="1eecb-131">Verify the following settings, correcting as needed:</span></span> 
    
   |<span data-ttu-id="1eecb-132">**參數**</span><span class="sxs-lookup"><span data-stu-id="1eecb-132">**Parameter**</span></span>|<span data-ttu-id="1eecb-133">**建議的設定**</span><span class="sxs-lookup"><span data-stu-id="1eecb-133">**Recommended setting**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="1eecb-134">H. 323 Mode</span><span class="sxs-lookup"><span data-stu-id="1eecb-134">H.323 Mode</span></span>  <br/> | <span data-ttu-id="1eecb-135">出</span><span class="sxs-lookup"><span data-stu-id="1eecb-135">Off</span></span> <br/> |
   |<span data-ttu-id="1eecb-136">HTTP 模式</span><span class="sxs-lookup"><span data-stu-id="1eecb-136">HTTP Mode</span></span>  <br/> | <span data-ttu-id="1eecb-137">按</span><span class="sxs-lookup"><span data-stu-id="1eecb-137">On</span></span> <br/> |
   | <span data-ttu-id="1eecb-138">SIP 模式</span><span class="sxs-lookup"><span data-stu-id="1eecb-138">SIP Mode</span></span> <br/> | <span data-ttu-id="1eecb-139">按</span><span class="sxs-lookup"><span data-stu-id="1eecb-139">On</span></span> <br/> |
   |<span data-ttu-id="1eecb-140">Telnet 模式</span><span class="sxs-lookup"><span data-stu-id="1eecb-140">Telnet Mode</span></span>  <br/> | <span data-ttu-id="1eecb-141">按</span><span class="sxs-lookup"><span data-stu-id="1eecb-141">On</span></span> <br/> |
   |<span data-ttu-id="1eecb-142">WelcomeText</span><span class="sxs-lookup"><span data-stu-id="1eecb-142">WelcomeText</span></span>  <br/> | <span data-ttu-id="1eecb-143">按</span><span class="sxs-lookup"><span data-stu-id="1eecb-143">On</span></span> <br/> |
   |<span data-ttu-id="1eecb-144">XMLAPI 模式</span><span class="sxs-lookup"><span data-stu-id="1eecb-144">XMLAPI Mode</span></span>  <br/> | <span data-ttu-id="1eecb-145">按</span><span class="sxs-lookup"><span data-stu-id="1eecb-145">On</span></span> <br/> |
   
7. <span data-ttu-id="1eecb-146">流覽至 [配置\>-系統設定\>-SIP]。</span><span class="sxs-lookup"><span data-stu-id="1eecb-146">Navigate to Configuration-\>System Configuration-\>SIP.</span></span>
    
8. <span data-ttu-id="1eecb-147">確認下列設定，視需要修正：</span><span class="sxs-lookup"><span data-stu-id="1eecb-147">Verify the following settings, correcting as needed:</span></span> 
    
   |<span data-ttu-id="1eecb-148">**參數**</span><span class="sxs-lookup"><span data-stu-id="1eecb-148">**Parameter**</span></span>|<span data-ttu-id="1eecb-149">**建議的設定**</span><span class="sxs-lookup"><span data-stu-id="1eecb-149">**Recommended setting**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="1eecb-150">設定檔 1-DefaultTransport</span><span class="sxs-lookup"><span data-stu-id="1eecb-150">Profile 1 - DefaultTransport</span></span>  <br/> | <span data-ttu-id="1eecb-151">TCP-OUT</span><span class="sxs-lookup"><span data-stu-id="1eecb-151">TCP</span></span> <br/> |
   |<span data-ttu-id="1eecb-152">設定檔 1-輸出</span><span class="sxs-lookup"><span data-stu-id="1eecb-152">Profile 1 - Outbound</span></span>  <br/> | <span data-ttu-id="1eecb-153">出</span><span class="sxs-lookup"><span data-stu-id="1eecb-153">Off</span></span> <br/> |
   |<span data-ttu-id="1eecb-154">設定檔 1-TlsVerify</span><span class="sxs-lookup"><span data-stu-id="1eecb-154">Profile 1 - TlsVerify</span></span>  <br/> | <span data-ttu-id="1eecb-155">按</span><span class="sxs-lookup"><span data-stu-id="1eecb-155">On</span></span> <br/> |
   |<span data-ttu-id="1eecb-156">設定檔 1-類型</span><span class="sxs-lookup"><span data-stu-id="1eecb-156">Profile 1 - Type</span></span>  <br/> | <span data-ttu-id="1eecb-157">Cisco</span><span class="sxs-lookup"><span data-stu-id="1eecb-157">Cisco</span></span> <br/> |
   |<span data-ttu-id="1eecb-158">設定檔 1-URI</span><span class="sxs-lookup"><span data-stu-id="1eecb-158">Profile 1 - URI</span></span>  <br/> | <span data-ttu-id="1eecb-159">在 CUCM 註冊時自動指派</span><span class="sxs-lookup"><span data-stu-id="1eecb-159">Automatically assigned at CUCM registration</span></span> <br/> |
   |<span data-ttu-id="1eecb-160">Proxy 1-位址</span><span class="sxs-lookup"><span data-stu-id="1eecb-160">Proxy 1 - Address</span></span>  <br/> |<span data-ttu-id="1eecb-161">CUCM 的主機名稱</span><span class="sxs-lookup"><span data-stu-id="1eecb-161">The host name of the CUCM</span></span>  <br/> |
   
<span data-ttu-id="1eecb-162">VTC 現在已針對互用性進行設定。</span><span class="sxs-lookup"><span data-stu-id="1eecb-162">The VTC is now configured for interoperation.</span></span> <span data-ttu-id="1eecb-163">在服務開始之前，請先在 CUCM 端執行最後一個步驟。</span><span class="sxs-lookup"><span data-stu-id="1eecb-163">Before service can begin, there are final steps to perform on the CUCM side.</span></span>
### <a name="configure-vtc-devices-on-cucm"></a><span data-ttu-id="1eecb-164">在 CUCM 上設定 VTC 裝置</span><span class="sxs-lookup"><span data-stu-id="1eecb-164">Configure VTC devices on CUCM</span></span>

1. <span data-ttu-id="1eecb-165">登入 CUCM 並流覽至 Cisco 一體化 CM 管理-\>裝置-\>電話-\>尋找。</span><span class="sxs-lookup"><span data-stu-id="1eecb-165">Log in to CUCM and Navigate to Cisco Unified CM Administration-\>Device-\>Phone-\>Find.</span></span> 
    
2. <span data-ttu-id="1eecb-166">選取要設定的 VTC 裝置。</span><span class="sxs-lookup"><span data-stu-id="1eecb-166">Select the VTC device to be configured.</span></span> <span data-ttu-id="1eecb-167">確認 [電話設定] 畫面上的下列設定，並視需要修正。</span><span class="sxs-lookup"><span data-stu-id="1eecb-167">Verify the following settings on the Phone Configuration screen, correcting as needed.</span></span> <span data-ttu-id="1eecb-168">變更或驗證這些設定之後，按一下 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="1eecb-168">Once these settings have been changed or verified, click on **Save**.</span></span>
    
   |<span data-ttu-id="1eecb-169">**參數**</span><span class="sxs-lookup"><span data-stu-id="1eecb-169">**Parameter**</span></span>|<span data-ttu-id="1eecb-170">**建議的設定**</span><span class="sxs-lookup"><span data-stu-id="1eecb-170">**Recommended setting**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="1eecb-171">裝置資訊-電話按鈕範本</span><span class="sxs-lookup"><span data-stu-id="1eecb-171">Device Information - Phone Button Template</span></span>  <br/> | <span data-ttu-id="1eecb-172">標準 Cisco Telepresence 編解碼器 C40</span><span class="sxs-lookup"><span data-stu-id="1eecb-172">Standard Cisco Telepresence Codec C40</span></span> <br/> |
   |<span data-ttu-id="1eecb-173">裝置資訊-常用的電話設定檔</span><span class="sxs-lookup"><span data-stu-id="1eecb-173">Device Information - Common Phone Profile</span></span>  <br/> | <span data-ttu-id="1eecb-174">標準常用電話設定檔</span><span class="sxs-lookup"><span data-stu-id="1eecb-174">Standard Common Phone Profile</span></span> <br/> |
   |<span data-ttu-id="1eecb-175">裝置資訊-呼叫搜尋空間</span><span class="sxs-lookup"><span data-stu-id="1eecb-175">Device Information - Calling Search Space</span></span>  <br/> | <span data-ttu-id="1eecb-176">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="1eecb-176">CSS_SfBVideoInterop</span></span> <br/> |
   |<span data-ttu-id="1eecb-177">裝置資訊-AAR 通話搜尋空間</span><span class="sxs-lookup"><span data-stu-id="1eecb-177">Device Information - AAR Calling Search Space</span></span>  <br/> | <span data-ttu-id="1eecb-178">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="1eecb-178">CSS_SfBVideoInterop</span></span> <br/> |
   |<span data-ttu-id="1eecb-179">裝置資訊-媒體資源群組清單</span><span class="sxs-lookup"><span data-stu-id="1eecb-179">Device Information - Media Resource Group List</span></span>  <br/> | <span data-ttu-id="1eecb-180">MRGL_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="1eecb-180">MRGL_SfBVideoInterop</span></span> <br/> |
   |<span data-ttu-id="1eecb-181">通訊協定的特定資訊-裝置安全設定檔</span><span class="sxs-lookup"><span data-stu-id="1eecb-181">Protocol Specific Information - Device Security Profile</span></span>  <br/> | <span data-ttu-id="1eecb-182">Cisco Telepresence 編解碼器 C40</span><span class="sxs-lookup"><span data-stu-id="1eecb-182">Cisco Telepresence Codec C40</span></span> <br/> |
   |<span data-ttu-id="1eecb-183">通訊協定特定資訊-重新路由呼叫搜尋空間</span><span class="sxs-lookup"><span data-stu-id="1eecb-183">Protocol Specific Information - Rerouting Calling Search Space</span></span>  <br/> | <span data-ttu-id="1eecb-184">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="1eecb-184">CSS_SfBVideoInterop</span></span> <br/> |
   |<span data-ttu-id="1eecb-185">通訊協定的特定資訊-訂閱通話搜尋空間</span><span class="sxs-lookup"><span data-stu-id="1eecb-185">Protocol Specific Information - SUBSCRIBE Calling Search Space</span></span>  <br/> | <span data-ttu-id="1eecb-186">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="1eecb-186">CSS_SfBVideoInterop</span></span> <br/> |
   |<span data-ttu-id="1eecb-187">通訊協定的特定資訊-SIP 設定檔</span><span class="sxs-lookup"><span data-stu-id="1eecb-187">Protocol Specific Information -SIP Profile</span></span>  <br/> | <span data-ttu-id="1eecb-188">Telepresence 端點的標準 SIP 設定檔</span><span class="sxs-lookup"><span data-stu-id="1eecb-188">Standard SIP Profile for Telepresence Endpoint</span></span> <br/> |
   
3. <span data-ttu-id="1eecb-189">儲存 VTC 設定之後，請重新流覽裝置的 [電話設定] 畫面。</span><span class="sxs-lookup"><span data-stu-id="1eecb-189">Once VTC configuration is saved, re-navigate to the Phone Configuration screen for the device.</span></span> <span data-ttu-id="1eecb-190">在畫面頂端的 [關聯] 群組中，按一下影片交互操作的關聯。</span><span class="sxs-lookup"><span data-stu-id="1eecb-190">At the top of the screen in the Association group, click on the association for the Video Interop.</span></span> <span data-ttu-id="1eecb-191">這會顯示 [目錄號碼設定] 畫面。</span><span class="sxs-lookup"><span data-stu-id="1eecb-191">This brings up the Directory Number Configuration screen.</span></span> 
    
4. <span data-ttu-id="1eecb-192">確認下列設定，視需要修正：</span><span class="sxs-lookup"><span data-stu-id="1eecb-192">Verify the following settings, correcting as needed:</span></span> 
    
    <span data-ttu-id="1eecb-193">根據目錄號碼資訊和目錄編號設定，進行適當的變更。</span><span class="sxs-lookup"><span data-stu-id="1eecb-193">Make the appropriate changes as shown to the Directory Number Information and the Directory Number Settings.</span></span>
    
   |<span data-ttu-id="1eecb-194">**參數**</span><span class="sxs-lookup"><span data-stu-id="1eecb-194">**Parameter**</span></span>|<span data-ttu-id="1eecb-195">**建議的設定**</span><span class="sxs-lookup"><span data-stu-id="1eecb-195">**Recommended setting**</span></span>|
   |:-----|:-----|
   | <span data-ttu-id="1eecb-196">目錄號碼資訊-路由分區</span><span class="sxs-lookup"><span data-stu-id="1eecb-196">Directory Number Information - Route Partition</span></span> <br/> | <span data-ttu-id="1eecb-197">SfBVideoInterop_RoutePartition</span><span class="sxs-lookup"><span data-stu-id="1eecb-197">SfBVideoInterop_RoutePartition</span></span> <br/> |
   |<span data-ttu-id="1eecb-198">目錄號碼設定-呼叫搜尋空間</span><span class="sxs-lookup"><span data-stu-id="1eecb-198">Directory Number Settings - Calling Search Space</span></span>  <br/> | <span data-ttu-id="1eecb-199">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="1eecb-199">CSS_SfBVideoInterop</span></span> <br/> |
   |<span data-ttu-id="1eecb-200">MLPP 備用方及機密存取層級設定-MLPP 呼叫搜尋空間</span><span class="sxs-lookup"><span data-stu-id="1eecb-200">MLPP Alternate Party and Confidential Access Level Settings - MLPP Calling Search Space</span></span>  <br/> | <span data-ttu-id="1eecb-201">CSS_SfBVideoInterop</span><span class="sxs-lookup"><span data-stu-id="1eecb-201">CSS_SfBVideoInterop</span></span> <br/> |
   |<span data-ttu-id="1eecb-202">裝置上的第1行（本機號碼）</span><span class="sxs-lookup"><span data-stu-id="1eecb-202">Line 1 on Device - Display (Caller ID)</span></span>  <br/> | <span data-ttu-id="1eecb-203">視需要</span><span class="sxs-lookup"><span data-stu-id="1eecb-203">As desired</span></span> <br/> |
   |<span data-ttu-id="1eecb-204">裝置上的第1列-ASCII 顯示（來電者識別碼）</span><span class="sxs-lookup"><span data-stu-id="1eecb-204">Line 1 on Device - ASCII Display (Caller ID)</span></span>  <br/> | <span data-ttu-id="1eecb-205">視需要</span><span class="sxs-lookup"><span data-stu-id="1eecb-205">As desired</span></span> <br/> |
   
5. <span data-ttu-id="1eecb-206">完成後，請滾動至畫面頂端，然後按 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="1eecb-206">When finished, scroll to the top of the screen and press **Save**.</span></span> 
    
<span data-ttu-id="1eecb-207">此 VTC 裝置的設定現已完成。</span><span class="sxs-lookup"><span data-stu-id="1eecb-207">Configuration is now complete for this VTC device.</span></span> <span data-ttu-id="1eecb-208">您將需要針對企業中的其他 VTC 裝置重複此程式。</span><span class="sxs-lookup"><span data-stu-id="1eecb-208">You will need to repeat this process for other VTC devices in your enterprise.</span></span>

