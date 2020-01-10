---
title: 在商務用 Skype Server 中設定視頻交互操作伺服器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 0fde142b-70b1-46c6-b1f9-f9d70115371d
description: 摘要：在商務用 Skype Server 中設定視頻互通性伺服器（VIS）角色。
ms.openlocfilehash: fb9dc36bcf2f1a6f1346705f74dd3cf2844a973c
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003053"
---
# <a name="configure-the-video-interop-server-in-skype-for-business-server"></a><span data-ttu-id="0ecef-103">在商務用 Skype Server 中設定視頻交互操作伺服器</span><span class="sxs-lookup"><span data-stu-id="0ecef-103">Configure the Video Interop Server in Skype for Business Server</span></span>
 
<span data-ttu-id="0ecef-104">**摘要：** 在商務用 Skype Server 中設定影片互通性伺服器（VIS）角色。</span><span class="sxs-lookup"><span data-stu-id="0ecef-104">**Summary:** Configure the Video Interop Server (VIS) role in Skype for Business Server.</span></span>
  
 <span data-ttu-id="0ecef-105">使用 Windows PowerShell 設定 VIS 將與視頻 trunks 相關聯的設定。</span><span class="sxs-lookup"><span data-stu-id="0ecef-105">Configure the settings that the VIS will associate with video trunks using Windows PowerShell.</span></span> <span data-ttu-id="0ecef-106">安裝 VIS 服務之後，就會建立含全域作用中的影片幹線設定。</span><span class="sxs-lookup"><span data-stu-id="0ecef-106">A video trunk configuration with global scope is created once the VIS service is installed.</span></span> <span data-ttu-id="0ecef-107">此視頻幹線設定會由 VIS 套用至所有沒有視頻幹線設定且具有更具體範圍的 trunks。</span><span class="sxs-lookup"><span data-stu-id="0ecef-107">This video trunk configuration is applied by the VIS to all trunks which do not have video trunk configuration with a more specific scope.</span></span> <span data-ttu-id="0ecef-108">請注意，[影片主幹設定] 是適用于 [視頻 trunks] 的設定集合。</span><span class="sxs-lookup"><span data-stu-id="0ecef-108">Note that the video trunk configuration is a collection of settings that is applicable to video trunks.</span></span>
  
## <a name="configure-video-trunk-and-dial-plan"></a><span data-ttu-id="0ecef-109">設定影片幹線與撥號方案</span><span class="sxs-lookup"><span data-stu-id="0ecef-109">Configure video trunk and dial plan</span></span>

<span data-ttu-id="0ecef-110">使用下列 Windows PowerShell 命令來指定要與在 VIS 和所有視頻閘道之間的拓撲結構中定義的新定義幹線相關聯的影片幹線設定和撥號計畫。</span><span class="sxs-lookup"><span data-stu-id="0ecef-110">Use the following Windows PowerShell commands to specify the video trunk configuration and dial plan to be associated with the newly defined trunk(s) defined in the Topology Document between the VIS and all Video Gateways.</span></span> <span data-ttu-id="0ecef-111">所有這些設定都可以在 [全域]、[網站] 或 [服務] （[視頻閘道]）層級設定。</span><span class="sxs-lookup"><span data-stu-id="0ecef-111">All these settings can be set at the Global, Site, or service (Video Gateway) levels.</span></span> 
  
<span data-ttu-id="0ecef-112">具有全域作用中的撥號方案會針對商務用 Skype Server 部署建立。</span><span class="sxs-lookup"><span data-stu-id="0ecef-112">A dial plan with global scope is created per Skype for Business Server deployment.</span></span> <span data-ttu-id="0ecef-113">這個撥號方案是由 VIS 套用至所有不含特定範圍的撥號規劃的 trunks。</span><span class="sxs-lookup"><span data-stu-id="0ecef-113">This dial plan is applied by VIS to all trunks which do not have any dial plan with more specific scope.</span></span> 
  
### <a name="configure-the-vis-using-windows-powershell"></a><span data-ttu-id="0ecef-114">使用 Windows PowerShell 設定 VIS</span><span class="sxs-lookup"><span data-stu-id="0ecef-114">Configure the VIS using Windows PowerShell</span></span>

1. <span data-ttu-id="0ecef-115">使用下列 Windows PowerShell Cmdlet，建立新的影片幹線設定（設定的集合），以在 VIS 與 Cisco 整合通訊管理員（CallManager 或 CUCM）之間的主幹上使用：</span><span class="sxs-lookup"><span data-stu-id="0ecef-115">Create a new video trunk configuration (a collection of settings) to use on the trunk between the VIS and Cisco Unified Communications Manager (CallManager, or CUCM), using the following Windows PowerShell cmdlet:</span></span>
    
   ```powershell
   New-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com" -GatewaySendsRtcpForActiveCalls $false -GatewaySendsRtcpForCallsOnHold $false -EnableMediaEncryptionForSipOverTls $true(or $false)
   ```

    <span data-ttu-id="0ecef-116">如果有需要修改的現有影片主幹，請使用下列 Windows PowerShell Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="0ecef-116">If there is an existing video trunk that needs to be modified, use the following Windows PowerShell cmdlet:</span></span>
    
   ```powershell
   Set-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com" -GatewaySendsRtcpForActiveCalls $false -GatewaySendsRtcpForCallsOnHold $false -EnableMediaEncryptionForSipOverTls  $true(or $false)
   ```

    <span data-ttu-id="0ecef-117">若要查看與特定的影片幹線設定相關聯的設定，請使用下列 Windows PowerShell Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="0ecef-117">To view the settings associated with a particular video trunk configuration, use the following Windows PowerShell cmdlet:</span></span>
    
   ```powershell
   Get-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com"
   ```

    <span data-ttu-id="0ecef-118">若要移除特定的視頻幹線設定，請使用下列 Windows PowerShell Cmdlet （請注意，如果特定幹線沒有更明確限制範圍的視頻幹線設定，就會套用全域範圍的視頻幹線設定）：</span><span class="sxs-lookup"><span data-stu-id="0ecef-118">To remove a particular video trunk configuration, use the following Windows PowerShell cmdlet (note that the globally scoped video trunk configuration will be applied if there is not a more specifically scoped video trunk configuration for a particular trunk):</span></span>
    
   ```powershell
   Remove-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com"
   ```

2. <span data-ttu-id="0ecef-119">使用下列 Windows PowerShell Cmdlet 建立要與主幹產生關聯的撥號方案：</span><span class="sxs-lookup"><span data-stu-id="0ecef-119">Establish a dial plan to associate with the trunk, using the following Windows PowerShell cmdlets:</span></span>
    
   ```powershell
   New-CsDialPlan -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com" -SimpleName "TrunkTestDialPlan" 
   New-CsVoiceNormalizationRule -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com/SevenDigitRule" -Pattern '^(\d{7})$' -Translation '+1425$1' 
   Get-CsDialPlan -Identity "Service:CUCMVIS1.CUCMInterop.contoso.com"
   Remove-CsVoiceNormalizationRule -Identity  "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com/Keep All"
   ```

<span data-ttu-id="0ecef-120">若要覆寫會干擾預期 VIS 和 CUCM 互動的預設規則，則需要**Remove-CsVoiceNormalizationRule**命令。</span><span class="sxs-lookup"><span data-stu-id="0ecef-120">The **Remove-CsVoiceNormalizationRule** command is needed to override a default rule that will interfere with the expected VIS and CUCM interaction.</span></span>
> [!NOTE]
> <span data-ttu-id="0ecef-121">[移除-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/remove-csdialplan?view=skype-ps)可用來移除撥號方案。</span><span class="sxs-lookup"><span data-stu-id="0ecef-121">[Remove-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/remove-csdialplan?view=skype-ps) can be used to remove a dial plan.</span></span>
  
<span data-ttu-id="0ecef-122">對於來自視頻閘道的視頻 SIP 幹線呼叫，其要求 URI 包含非 E. 164 個數字，VIS 將會讀取與關聯主幹相關聯的撥號方案名稱，並將撥號計畫名稱包含在此 VI 中之邀請 URI 的電話內容部分中S 會傳送到前端。</span><span class="sxs-lookup"><span data-stu-id="0ecef-122">For a video SIP Trunk call from a Video Gateway whose Request URI contains a non-E.164 number, VIS will read the name of the dial plan associated with the associated trunk, and will include the dial plan name in the phone context part of the Request URI in the Invite that VIS sends to the Front End.</span></span> <span data-ttu-id="0ecef-123">前端的翻譯應用程式接著會解壓縮並將與撥號計畫相關聯的正常化規則套用至要求 URI。</span><span class="sxs-lookup"><span data-stu-id="0ecef-123">The Translation Application on the Front End then extracts and applies the normalization rules associated with the dial plan to the Request URI.</span></span>
## <a name="trunk-configuration-options"></a><span data-ttu-id="0ecef-124">幹線配置選項</span><span class="sxs-lookup"><span data-stu-id="0ecef-124">Trunk configuration options</span></span>

<span data-ttu-id="0ecef-125">先前所述的影片主幹設定的 Windows PowerShell Cmdlet 是商務用 Skype Server 2015 的新程式。</span><span class="sxs-lookup"><span data-stu-id="0ecef-125">The Windows PowerShell cmdlets for video trunk configuration mentioned previously were new to Skype for Business Server 2015.</span></span> <span data-ttu-id="0ecef-126">與影片幹線設定相關的設定需要簡短的說明。</span><span class="sxs-lookup"><span data-stu-id="0ecef-126">The settings associated with video trunk configuration require a brief explanation.</span></span>
  
 <span data-ttu-id="0ecef-127">**GatewaySendsRtcpForActiveCalls**這個參數會判斷 RTCP 資料包是否從 VTC 傳送至 VIS，以進行使用中的通話。</span><span class="sxs-lookup"><span data-stu-id="0ecef-127">**GatewaySendsRtcpForActiveCalls** This parameter determines whether RTCP packets are sent from the VTC to the VIS for active calls.</span></span> <span data-ttu-id="0ecef-128">此處的目前通話指的是至少允許媒體流向一個方向的通話。</span><span class="sxs-lookup"><span data-stu-id="0ecef-128">An active call in this context is a call where media is allowed to flow in at least one direction.</span></span> <span data-ttu-id="0ecef-129">如果 GatewaySendsRtcpForActiveCalls 設定為 True，則 VIS 可以在超過30秒的期限內收到 RTCP 資料包時終止通話。</span><span class="sxs-lookup"><span data-stu-id="0ecef-129">If GatewaySendsRtcpForActiveCalls is set to True, VIS can terminate a call if it does not receive RTCP packets for a period exceeding 30 seconds.</span></span> <span data-ttu-id="0ecef-130">預設值為**True**。</span><span class="sxs-lookup"><span data-stu-id="0ecef-130">The default is **True**.</span></span>
  
 <span data-ttu-id="0ecef-131">**GatewaySendsRtcpForCallsOnHold**這個參數決定是否要在主幹中繼續傳送 RTCP 資料包，以取得已保留的通話，而且不會將任何媒體資料包流向任何方向。</span><span class="sxs-lookup"><span data-stu-id="0ecef-131">**GatewaySendsRtcpForCallsOnHold** This parameter determines whether RTCP packets continue to be sent across the trunk for calls that have been placed on hold and no media packets are expected to flow in either direction.</span></span> <span data-ttu-id="0ecef-132">如果通話處於保留狀態時，如果沒有 RTCP 資料包從 VTC 流向 VIS，VIS 可以終止通話。</span><span class="sxs-lookup"><span data-stu-id="0ecef-132">VIS can terminate the call, if there are no RTCP packets flowing from the VTC to VIS while the call is on Hold.</span></span> <span data-ttu-id="0ecef-133">預設值為**True**。</span><span class="sxs-lookup"><span data-stu-id="0ecef-133">The default is **True**.</span></span> <span data-ttu-id="0ecef-134">當 SIPTransport 通訊協定設定為 TCP 時，此設定會被忽略。</span><span class="sxs-lookup"><span data-stu-id="0ecef-134">When the SIPTransport protocol is set to TCP, this setting is ignored.</span></span>
  
 <span data-ttu-id="0ecef-135">**EnableMediaEncryptionForSipOverTls**此參數可在 SIPTransport 通訊協定設定為 TLS 時啟用或停用媒體的 SRTP。</span><span class="sxs-lookup"><span data-stu-id="0ecef-135">**EnableMediaEncryptionForSipOverTls** This parameter enables or disables SRTP for media when the SIPTransport protocol is set to TLS.</span></span> <span data-ttu-id="0ecef-136">預設值為**True**。</span><span class="sxs-lookup"><span data-stu-id="0ecef-136">The default is **True**.</span></span> <span data-ttu-id="0ecef-137">當 SIPTransport 通訊協定設定為 TCP 時，此設定會被忽略。</span><span class="sxs-lookup"><span data-stu-id="0ecef-137">When the SIPTransport protocol is set to TCP, this setting is ignored.</span></span>
  
 <span data-ttu-id="0ecef-138">**EnableSessionTimer**這個參數可在 VIS 端針對與影片 SIP 幹線相關聯的每個 SIP 對話方塊，啟用或停用會話計時器。</span><span class="sxs-lookup"><span data-stu-id="0ecef-138">**EnableSessionTimer** This parameter enables or disables session timers on the VIS side for each SIP dialog associated with the video SIP trunk.</span></span> <span data-ttu-id="0ecef-139">預設值為**False**。</span><span class="sxs-lookup"><span data-stu-id="0ecef-139">The default is **False**.</span></span>
  
 <span data-ttu-id="0ecef-140">**ForwardErrorCorrectionType**這個參數是用來判斷視頻資料流程的轉寄糾錯（FEC）是否要套用在視頻互通性伺服器與視頻閘道之間的腿上。</span><span class="sxs-lookup"><span data-stu-id="0ecef-140">**ForwardErrorCorrectionType** This parameter is used to determine if Forward Error Correction (FEC) for video streams is to be applied on the leg between the Video Interop Server and a Video Gateway.</span></span> <span data-ttu-id="0ecef-141">將 ForwardErrorCorrectionType 設定為 [None]，就會關閉 VIS 與視頻閘道/VTC 之間的 FEC。</span><span class="sxs-lookup"><span data-stu-id="0ecef-141">Setting ForwardErrorCorrectionType to "None" turns off FEC between VIS and Video Gateway/VTC.</span></span> <span data-ttu-id="0ecef-142">將 ForwardErrorCorrectionType 設定為「Cisco」可讓您透過 Cisco （例如 Cisco 整合通訊管理員（CUCM）等與視頻閘道相容的 FEC。</span><span class="sxs-lookup"><span data-stu-id="0ecef-142">Setting ForwardErrorCorrectionType to "Cisco" enables FEC compatible with Video Gateways by Cisco, such as Cisco Unified Communications Manager (CUCM).</span></span> <span data-ttu-id="0ecef-143">預設值為 [**無**]。</span><span class="sxs-lookup"><span data-stu-id="0ecef-143">The default is **None**.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="0ecef-144">另請參閱</span><span class="sxs-lookup"><span data-stu-id="0ecef-144">See also</span></span>

[<span data-ttu-id="0ecef-145">設定 CUCM 以與商務用 Skype 伺服器進行交互操作</span><span class="sxs-lookup"><span data-stu-id="0ecef-145">Configure CUCM for Interoperation with Skype for Business Server</span></span>](configure-cucm-for-interoperation.md)
