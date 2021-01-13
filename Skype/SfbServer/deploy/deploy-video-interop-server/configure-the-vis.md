---
title: 在商務用 Skype Server 中設定視頻 Interop 伺服器
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
ms.assetid: 0fde142b-70b1-46c6-b1f9-f9d70115371d
description: 摘要：在商務用 Skype Server 中設定 (VIS) 角色的視頻 Interop 伺服器。
ms.openlocfilehash: 84ab821249ae388bc1ba0dc41cb980c90d4f0853
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820693"
---
# <a name="configure-the-video-interop-server-in-skype-for-business-server"></a><span data-ttu-id="b8f79-103">在商務用 Skype Server 中設定視頻 Interop 伺服器</span><span class="sxs-lookup"><span data-stu-id="b8f79-103">Configure the Video Interop Server in Skype for Business Server</span></span>
 
<span data-ttu-id="b8f79-104">**摘要：** 在商務用 Skype Server 中設定 (VIS) 角色的視頻 Interop 伺服器。</span><span class="sxs-lookup"><span data-stu-id="b8f79-104">**Summary:** Configure the Video Interop Server (VIS) role in Skype for Business Server.</span></span>
  
 <span data-ttu-id="b8f79-105">使用 Windows PowerShell，設定 VIS 將與影片主幹關聯的設定。</span><span class="sxs-lookup"><span data-stu-id="b8f79-105">Configure the settings that the VIS will associate with video trunks using Windows PowerShell.</span></span> <span data-ttu-id="b8f79-106">安裝 VIS 服務後，就會建立具有全域範圍的影片主幹設定。</span><span class="sxs-lookup"><span data-stu-id="b8f79-106">A video trunk configuration with global scope is created once the VIS service is installed.</span></span> <span data-ttu-id="b8f79-107">此影片主幹設定會由 VIS 套用至所有未具有較特定範圍的「影片主幹」設定的主幹。</span><span class="sxs-lookup"><span data-stu-id="b8f79-107">This video trunk configuration is applied by the VIS to all trunks which do not have video trunk configuration with a more specific scope.</span></span> <span data-ttu-id="b8f79-108">請注意，「影片主幹」設定是適用于影片主幹的設定集合。</span><span class="sxs-lookup"><span data-stu-id="b8f79-108">Note that the video trunk configuration is a collection of settings that is applicable to video trunks.</span></span>
  
## <a name="configure-video-trunk-and-dial-plan"></a><span data-ttu-id="b8f79-109">設定影片主幹及撥號對應表</span><span class="sxs-lookup"><span data-stu-id="b8f79-109">Configure video trunk and dial plan</span></span>

<span data-ttu-id="b8f79-110">使用下列 Windows PowerShell 命令，指定要與新定義主幹 (關聯的影片主幹設定和撥號對應表，) 在 VIS 和所有的視頻閘道之間的拓撲檔中所定義。</span><span class="sxs-lookup"><span data-stu-id="b8f79-110">Use the following Windows PowerShell commands to specify the video trunk configuration and dial plan to be associated with the newly defined trunk(s) defined in the Topology Document between the VIS and all Video Gateways.</span></span> <span data-ttu-id="b8f79-111">您可以在全域、網站或服務 (的視頻閘道) 層級設定所有這些設定。</span><span class="sxs-lookup"><span data-stu-id="b8f79-111">All these settings can be set at the Global, Site, or service (Video Gateway) levels.</span></span> 
  
<span data-ttu-id="b8f79-112">具有全域範圍的撥號對應表是針對商務用 Skype Server 部署而建立的。</span><span class="sxs-lookup"><span data-stu-id="b8f79-112">A dial plan with global scope is created per Skype for Business Server deployment.</span></span> <span data-ttu-id="b8f79-113">此撥號對應表是由 VIS 套用至所有沒有具有更特定範圍的撥號對應表的主幹。</span><span class="sxs-lookup"><span data-stu-id="b8f79-113">This dial plan is applied by VIS to all trunks which do not have any dial plan with more specific scope.</span></span> 
  
### <a name="configure-the-vis-using-windows-powershell"></a><span data-ttu-id="b8f79-114">使用 Windows PowerShell 設定 VIS</span><span class="sxs-lookup"><span data-stu-id="b8f79-114">Configure the VIS using Windows PowerShell</span></span>

1. <span data-ttu-id="b8f79-115">使用下列 Windows PowerShell Cmdlet，建立新的影片主幹設定 (，以在 VIS 和 Cisco 整合通訊管理員 (CallManager 或 CUCM) 之間的主幹上使用的設定) ：</span><span class="sxs-lookup"><span data-stu-id="b8f79-115">Create a new video trunk configuration (a collection of settings) to use on the trunk between the VIS and Cisco Unified Communications Manager (CallManager, or CUCM), using the following Windows PowerShell cmdlet:</span></span>
    
   ```powershell
   New-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com" -GatewaySendsRtcpForActiveCalls $false -GatewaySendsRtcpForCallsOnHold $false -EnableMediaEncryptionForSipOverTls $true(or $false)
   ```

    <span data-ttu-id="b8f79-116">如果有需要修改的現有影片主幹，請使用下列 Windows PowerShell Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="b8f79-116">If there is an existing video trunk that needs to be modified, use the following Windows PowerShell cmdlet:</span></span>
    
   ```powershell
   Set-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com" -GatewaySendsRtcpForActiveCalls $false -GatewaySendsRtcpForCallsOnHold $false -EnableMediaEncryptionForSipOverTls  $true(or $false)
   ```

    <span data-ttu-id="b8f79-117">若要查看與特定影片主幹設定相關聯的設定，請使用下列 Windows PowerShell Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="b8f79-117">To view the settings associated with a particular video trunk configuration, use the following Windows PowerShell cmdlet:</span></span>
    
   ```powershell
   Get-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com"
   ```

    <span data-ttu-id="b8f79-118">若要移除特定的「影片主幹」設定，請使用下列 Windows PowerShell Cmdlet (請注意，如果特定主幹) 上沒有特殊範圍的影片主幹設定，則會套用全域範圍的視頻主幹設定：</span><span class="sxs-lookup"><span data-stu-id="b8f79-118">To remove a particular video trunk configuration, use the following Windows PowerShell cmdlet (note that the globally scoped video trunk configuration will be applied if there is not a more specifically scoped video trunk configuration for a particular trunk):</span></span>
    
   ```powershell
   Remove-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com"
   ```

2. <span data-ttu-id="b8f79-119">使用下列 Windows PowerShell Cmdlet，建立與主幹相關聯的撥號對應表：</span><span class="sxs-lookup"><span data-stu-id="b8f79-119">Establish a dial plan to associate with the trunk, using the following Windows PowerShell cmdlets:</span></span>
    
   ```powershell
   New-CsDialPlan -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com" -SimpleName "TrunkTestDialPlan" 
   New-CsVoiceNormalizationRule -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com/SevenDigitRule" -Pattern '^(\d{7})$' -Translation '+1425$1' 
   Get-CsDialPlan -Identity "Service:CUCMVIS1.CUCMInterop.contoso.com"
   Remove-CsVoiceNormalizationRule -Identity  "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com/Keep All"
   ```

<span data-ttu-id="b8f79-120">需要使用 **Remove-get-csvoicenormalizationrule** 命令來覆寫會干擾預期 VIS 和 CUCM 互動的預設規則。</span><span class="sxs-lookup"><span data-stu-id="b8f79-120">The **Remove-CsVoiceNormalizationRule** command is needed to override a default rule that will interfere with the expected VIS and CUCM interaction.</span></span>
> [!NOTE]
> <span data-ttu-id="b8f79-121">可以使用[get-csdialplan](https://docs.microsoft.com/powershell/module/skype/remove-csdialplan?view=skype-ps)移除撥號對應表。</span><span class="sxs-lookup"><span data-stu-id="b8f79-121">[Remove-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/remove-csdialplan?view=skype-ps) can be used to remove a dial plan.</span></span>
  
<span data-ttu-id="b8f79-122">針對來自視頻閘道（要求 URI 包含非 e.164 號碼）的影片 SIP 主幹呼叫，VIS 會讀取與關聯主幹相關聯的撥號對應表名稱，並將撥號對應表名稱包含在 VIS 傳送至前端之邀請中之要求 URI 的電話內容部分中。</span><span class="sxs-lookup"><span data-stu-id="b8f79-122">For a video SIP Trunk call from a Video Gateway whose Request URI contains a non-E.164 number, VIS will read the name of the dial plan associated with the associated trunk, and will include the dial plan name in the phone context part of the Request URI in the Invite that VIS sends to the Front End.</span></span> <span data-ttu-id="b8f79-123">前端的翻譯應用程式接著會解壓縮並套用與撥號對應表相關聯的正規化規則到要求 URI。</span><span class="sxs-lookup"><span data-stu-id="b8f79-123">The Translation Application on the Front End then extracts and applies the normalization rules associated with the dial plan to the Request URI.</span></span>
## <a name="trunk-configuration-options"></a><span data-ttu-id="b8f79-124">主幹設定選項</span><span class="sxs-lookup"><span data-stu-id="b8f79-124">Trunk configuration options</span></span>

<span data-ttu-id="b8f79-125">先前提及之影片主幹設定的 Windows PowerShell Cmdlet 是商務用 Skype Server 2015 的新 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="b8f79-125">The Windows PowerShell cmdlets for video trunk configuration mentioned previously were new to Skype for Business Server 2015.</span></span> <span data-ttu-id="b8f79-126">與影片主幹設定相關聯的設定需要簡短的說明。</span><span class="sxs-lookup"><span data-stu-id="b8f79-126">The settings associated with video trunk configuration require a brief explanation.</span></span>
  
 <span data-ttu-id="b8f79-127">**GatewaySendsRtcpForActiveCalls** 此參數會決定是否要將 RTCP 的封包從 VTC 傳送至 VIS 以進行使用中通話。</span><span class="sxs-lookup"><span data-stu-id="b8f79-127">**GatewaySendsRtcpForActiveCalls** This parameter determines whether RTCP packets are sent from the VTC to the VIS for active calls.</span></span> <span data-ttu-id="b8f79-128">此處的目前通話指的是至少允許媒體流向一個方向的通話。</span><span class="sxs-lookup"><span data-stu-id="b8f79-128">An active call in this context is a call where media is allowed to flow in at least one direction.</span></span> <span data-ttu-id="b8f79-129">如果 GatewaySendsRtcpForActiveCalls 設定為 True，VIS 可以在超過30秒的期限內收到 RTCP 封包時結束通話。</span><span class="sxs-lookup"><span data-stu-id="b8f79-129">If GatewaySendsRtcpForActiveCalls is set to True, VIS can terminate a call if it does not receive RTCP packets for a period exceeding 30 seconds.</span></span> <span data-ttu-id="b8f79-130">預設值為 **True** 。</span><span class="sxs-lookup"><span data-stu-id="b8f79-130">The default is **True**.</span></span>
  
 <span data-ttu-id="b8f79-131">**GatewaySendsRtcpForCallsOnHold** 此參數會決定是否要針對暫止的通話繼續在主幹中傳送 RTCP 封包，而且沒有預期任何媒體封包流向任何方向。</span><span class="sxs-lookup"><span data-stu-id="b8f79-131">**GatewaySendsRtcpForCallsOnHold** This parameter determines whether RTCP packets continue to be sent across the trunk for calls that have been placed on hold and no media packets are expected to flow in either direction.</span></span> <span data-ttu-id="b8f79-132">若通話處於保留狀態，VIS 可以終止通話（如果沒有 RTCP 封包從 VTC 流向 VIS）。</span><span class="sxs-lookup"><span data-stu-id="b8f79-132">VIS can terminate the call, if there are no RTCP packets flowing from the VTC to VIS while the call is on Hold.</span></span> <span data-ttu-id="b8f79-133">預設值為 **True** 。</span><span class="sxs-lookup"><span data-stu-id="b8f79-133">The default is **True**.</span></span> <span data-ttu-id="b8f79-134">SIPTransport 通訊協定設定為 TCP 時，會忽略此設定。</span><span class="sxs-lookup"><span data-stu-id="b8f79-134">When the SIPTransport protocol is set to TCP, this setting is ignored.</span></span>
  
 <span data-ttu-id="b8f79-135">**EnableMediaEncryptionForSipOverTls** 當 SIPTransport 通訊協定設定為 TLS 時，此參數會啟用或停用媒體的 SRTP。</span><span class="sxs-lookup"><span data-stu-id="b8f79-135">**EnableMediaEncryptionForSipOverTls** This parameter enables or disables SRTP for media when the SIPTransport protocol is set to TLS.</span></span> <span data-ttu-id="b8f79-136">預設值為 **True** 。</span><span class="sxs-lookup"><span data-stu-id="b8f79-136">The default is **True**.</span></span> <span data-ttu-id="b8f79-137">SIPTransport 通訊協定設定為 TCP 時，會忽略此設定。</span><span class="sxs-lookup"><span data-stu-id="b8f79-137">When the SIPTransport protocol is set to TCP, this setting is ignored.</span></span>
  
 <span data-ttu-id="b8f79-138">**EnableSessionTimer** 此參數會針對與影片 SIP 主幹相關聯的每個 SIP 對話方塊，啟用或停用 VIS 端的會話計時器。</span><span class="sxs-lookup"><span data-stu-id="b8f79-138">**EnableSessionTimer** This parameter enables or disables session timers on the VIS side for each SIP dialog associated with the video SIP trunk.</span></span> <span data-ttu-id="b8f79-139">預設值為 **False** 。</span><span class="sxs-lookup"><span data-stu-id="b8f79-139">The default is **False**.</span></span>
  
 <span data-ttu-id="b8f79-140">**ForwardErrorCorrectionType** 此參數是用來判斷是否要將影片的 [轉寄錯誤修正] (FEC) 套用到視頻 Interop 伺服器和視頻閘道之間的腿。</span><span class="sxs-lookup"><span data-stu-id="b8f79-140">**ForwardErrorCorrectionType** This parameter is used to determine if Forward Error Correction (FEC) for video streams is to be applied on the leg between the Video Interop Server and a Video Gateway.</span></span> <span data-ttu-id="b8f79-141">將 ForwardErrorCorrectionType 設定為 "None" 會關閉 VIS 和 Video Gateway/VTC 之間的 FEC。</span><span class="sxs-lookup"><span data-stu-id="b8f79-141">Setting ForwardErrorCorrectionType to "None" turns off FEC between VIS and Video Gateway/VTC.</span></span> <span data-ttu-id="b8f79-142">將 ForwardErrorCorrectionType 設定為 "Cisco" 可使 FEC 與透過 Cisco 的視頻閘道相容，例如 Cisco 整合通訊管理員 (CUCM) 。</span><span class="sxs-lookup"><span data-stu-id="b8f79-142">Setting ForwardErrorCorrectionType to "Cisco" enables FEC compatible with Video Gateways by Cisco, such as Cisco Unified Communications Manager (CUCM).</span></span> <span data-ttu-id="b8f79-143">預設值為 **None**。</span><span class="sxs-lookup"><span data-stu-id="b8f79-143">The default is **None**.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="b8f79-144">另請參閱</span><span class="sxs-lookup"><span data-stu-id="b8f79-144">See also</span></span>

[<span data-ttu-id="b8f79-145">設定 CUCM 以搭配商務用 Skype 伺服器進行交互操作</span><span class="sxs-lookup"><span data-stu-id="b8f79-145">Configure CUCM for Interoperation with Skype for Business Server</span></span>](configure-cucm-for-interoperation.md)
