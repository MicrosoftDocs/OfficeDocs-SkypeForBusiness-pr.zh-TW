---
title: 設定直接路由
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: 瞭解如何設定 Microsoft Phone 系統 Direct 路由。
ms.openlocfilehash: 86406af88648d367f02fd420c9ba278bdfd47185
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/11/2020
ms.locfileid: "41888592"
---
# <a name="configure-direct-routing"></a><span data-ttu-id="e0800-103">設定直接路由</span><span class="sxs-lookup"><span data-stu-id="e0800-103">Configure Direct Routing</span></span>

> [!Tip]
> <span data-ttu-id="e0800-104">請觀看下列會話，瞭解直接路由的優點、如何規劃，以及部署方式：[直接在 Microsoft 團隊中傳送路線](https://aka.ms/teams-direct-routing)</span><span class="sxs-lookup"><span data-stu-id="e0800-104">Watch the following session to learn about the benefits of Direct Routing, how to plan for it, and how to deploy it: [Direct Routing in Microsoft Teams](https://aka.ms/teams-direct-routing)</span></span>

<span data-ttu-id="e0800-105">如果您尚未這麼做，請閱讀規劃先決條件的 [[直接路由](direct-routing-plan.md)]，並查看設定 Microsoft Phone 系統網路之前所需採取的其他步驟。</span><span class="sxs-lookup"><span data-stu-id="e0800-105">If you have not already done so, read [Plan Direct Routing](direct-routing-plan.md) for prerequisites and to review other steps you’ll need to take before you configure your Microsoft Phone System network.</span></span> 

<span data-ttu-id="e0800-106">本文說明如何設定 Microsoft Phone 系統 Direct 路由。</span><span class="sxs-lookup"><span data-stu-id="e0800-106">This article describes how to configure Microsoft Phone System Direct Routing.</span></span> <span data-ttu-id="e0800-107">它詳細說明如何將支援的會話邊界控制器（SBC）搭配使用，以直接傳送路線，以及如何將 Microsoft 團隊使用者設定為使用直接路由來連接至公用的交換電話網絡（PSTN）。</span><span class="sxs-lookup"><span data-stu-id="e0800-107">It details how to pair a supported Session Border Controller (SBC) to Direct Routing and how to configure Microsoft Teams users to use Direct Routing to connect to the Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="e0800-108">若要完成本文所述的步驟，管理員需要熟悉 PowerShell Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="e0800-108">To complete the steps explained in this article, administrators need some familiarity with PowerShell cmdlets.</span></span> <span data-ttu-id="e0800-109">如需有關使用 PowerShell 的詳細資訊，請參閱[設定您的 Windows PowerShell 電腦](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)。</span><span class="sxs-lookup"><span data-stu-id="e0800-109">For more information about using PowerShell, see [Set up your computer for Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span> 

<span data-ttu-id="e0800-110">我們建議您確認您的 SBC 已按照您的 SBC 廠商的建議進行設定：</span><span class="sxs-lookup"><span data-stu-id="e0800-110">We recommend that you confirm that your SBC has already been configured as recommended by your SBC vendor:</span></span> 

- [<span data-ttu-id="e0800-111">AudioCodes 部署檔</span><span class="sxs-lookup"><span data-stu-id="e0800-111">AudioCodes deployment documentation</span></span>](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [<span data-ttu-id="e0800-112">Oracle 部署檔</span><span class="sxs-lookup"><span data-stu-id="e0800-112">Oracle deployment documentation</span></span>](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [<span data-ttu-id="e0800-113">功能區通訊部署檔</span><span class="sxs-lookup"><span data-stu-id="e0800-113">Ribbon Communications deployment documentation</span></span>](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [<span data-ttu-id="e0800-114">TE-系統（anynode）部署檔</span><span class="sxs-lookup"><span data-stu-id="e0800-114">TE-Systems (anynode) deployment documentation</span></span>](https://www.anynode.de/anynode-and-microsoft-teams/)

<span data-ttu-id="e0800-115">您可以設定您的 Microsoft 手機系統，並讓使用者使用直接路由，然後將 Microsoft 團隊設定為首選的呼叫用戶端，方法是完成下列程式：</span><span class="sxs-lookup"><span data-stu-id="e0800-115">You can configure your Microsoft Phone System and enable users to use Direct Routing, then set up Microsoft Teams as the preferred calling client by completing the following procedures:</span></span> 

- [<span data-ttu-id="e0800-116">將 SBC 與 Microsoft 手機系統配對並驗證配對</span><span class="sxs-lookup"><span data-stu-id="e0800-116">Pair the SBC with a Microsoft Phone System and validate the pairing</span></span>](#pair-the-sbc-to-the-direct-routing-service-of-phone-system)
- [<span data-ttu-id="e0800-117">允許使用者使用直接路由服務</span><span class="sxs-lookup"><span data-stu-id="e0800-117">Enable users for Direct Routing Service</span></span>](#enable-users-for-direct-routing-service)
- <span data-ttu-id="e0800-118">確定 Microsoft 團隊是使用者的首選呼叫用戶端</span><span class="sxs-lookup"><span data-stu-id="e0800-118">Ensure that Microsoft Teams is the preferred calling client for the users</span></span>

## <a name="pair-the-sbc-to-the-direct-routing-service-of-phone-system"></a><span data-ttu-id="e0800-119">將 SBC 與電話系統的直接路由服務配對</span><span class="sxs-lookup"><span data-stu-id="e0800-119">Pair the SBC to the Direct Routing Service of Phone System</span></span> 

<span data-ttu-id="e0800-120">以下是可讓您將 SBC 連接或配對至直接路由介面的三個高層次步驟：</span><span class="sxs-lookup"><span data-stu-id="e0800-120">The following are the three high-level steps to let you connect, or pair, the SBC to the Direct Routing interface:</span></span> 

1. <span data-ttu-id="e0800-121">使用 PowerShell**連線到商務用 Skype Online**系統管理中心</span><span class="sxs-lookup"><span data-stu-id="e0800-121">Connect to **Skype for Business Online** admin center using PowerShell</span></span> 
2. <span data-ttu-id="e0800-122">對 SBC 進行配對</span><span class="sxs-lookup"><span data-stu-id="e0800-122">Pair the SBC</span></span> 
3. <span data-ttu-id="e0800-123">驗證配對</span><span class="sxs-lookup"><span data-stu-id="e0800-123">Validate the pairing</span></span> 

### <a name="connect-to-skype-for-business-online-by-using-powershell"></a><span data-ttu-id="e0800-124">使用 PowerShell 連線到商務用 Skype Online</span><span class="sxs-lookup"><span data-stu-id="e0800-124">Connect to Skype for Business Online by using PowerShell</span></span> 

<span data-ttu-id="e0800-125">您可以使用連接至租使用者的 PowerShell 會話，將 SBC 與直接路由介面配對。</span><span class="sxs-lookup"><span data-stu-id="e0800-125">You can use a PowerShell session connected to the tenant to pair the SBC to the Direct Routing interface.</span></span> <span data-ttu-id="e0800-126">若要開啟 PowerShell 會話，請依照[設定您的 Windows PowerShell 電腦](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)中所述的步驟進行。</span><span class="sxs-lookup"><span data-stu-id="e0800-126">To open a PowerShell session, please follow the steps outlined in [Set up your computer for Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span> 
 
<span data-ttu-id="e0800-127">建立遠端 PowerShell 會話之後，請確認您可以看到管理 SBC 的命令。</span><span class="sxs-lookup"><span data-stu-id="e0800-127">After you establish a remote PowerShell session, please validate that you can see the commands to manage the SBC.</span></span> <span data-ttu-id="e0800-128">若要驗證命令，請在 PowerShell 會話中輸入或複製/貼上下列內容，然後按 Enter：</span><span class="sxs-lookup"><span data-stu-id="e0800-128">To validate the commands, type or copy/paste in the following in the PowerShell session and press Enter:</span></span> 

```PowerShell
Get-Command *onlinePSTNGateway*
```

<span data-ttu-id="e0800-129">您的命令會傳回這裡顯示的四個函數，可讓您管理 SBC。</span><span class="sxs-lookup"><span data-stu-id="e0800-129">Your command will return the four functions shown here that will let you manage the SBC.</span></span> 

<pre>
CommandType    Name                       Version    Source 
-----------    ----                       -------    ------ 
Function       Get-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt 
Function       New-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt 
Function       Remove-CsOnlinePSTNGateway 1.0        tmp_v5fiu1no.wxt 
Function       Set-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt
</pre>   


### <a name="pair-the-sbc-to-the-tenant"></a><span data-ttu-id="e0800-130">將 SBC 與租使用者配對</span><span class="sxs-lookup"><span data-stu-id="e0800-130">Pair the SBC to the tenant</span></span> 

<span data-ttu-id="e0800-131">若要將 SBC 與租使用者進行配對，請在 PowerShell 會話中輸入下列內容，然後按 Enter 鍵：</span><span class="sxs-lookup"><span data-stu-id="e0800-131">To pair the SBC to the tenant, in the PowerShell session type the following and press Enter:</span></span> 

```PowerShell
New-CsOnlinePSTNGateway -Fqdn <SBC FQDN> -SipSignalingPort <SBC SIP Port> -MaxConcurrentSessions <Max Concurrent Sessions the SBC can handle> -Enabled $true 
```
  > [!NOTE]
  > 1. <span data-ttu-id="e0800-132">我們強烈建議您在 SBC 中設定最大通話限制，使用可在 SBC 檔中找到的資訊。</span><span class="sxs-lookup"><span data-stu-id="e0800-132">We highly recommend setting a maximum call limit in the SBC, using information that can be found in the SBC documentation.</span></span> <span data-ttu-id="e0800-133">如果 SBC 是容量等級，則限制會觸發通知。</span><span class="sxs-lookup"><span data-stu-id="e0800-133">The limit will trigger a notification if the SBC is at the capacity level.</span></span>
  > 2. <span data-ttu-id="e0800-134">您只能將 SBC 的網域部分與您在租使用者中註冊的其中一個網域相符（除了\*onmicrosoft.com），才能將它配對。</span><span class="sxs-lookup"><span data-stu-id="e0800-134">You can only pair the SBC if the domain portion of its FQDN matches one of the domains registered in your tenant, except \*.onmicrosoft.com.</span></span> <span data-ttu-id="e0800-135">SBC \*FQDN 名稱不支援使用 onmicrosoft.com 功能變數名稱。</span><span class="sxs-lookup"><span data-stu-id="e0800-135">Using \*.onmicrosoft.com domain names is not supported for the SBC FQDN name.</span></span> <span data-ttu-id="e0800-136">例如，如果您有兩個功能變數名稱：</span><span class="sxs-lookup"><span data-stu-id="e0800-136">For example, if you have two domain names:</span></span><br/><br/>
  > <span data-ttu-id="e0800-137">**contoso**</span><span class="sxs-lookup"><span data-stu-id="e0800-137">**contoso**.com</span></span><br/><span data-ttu-id="e0800-138">**contoso**. onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="e0800-138">**contoso**.onmicrosoft.com</span></span><br/><br/>
  > <span data-ttu-id="e0800-139">針對 SBC 名稱，您可以使用名稱 sbc.contoso.com。</span><span class="sxs-lookup"><span data-stu-id="e0800-139">For the SBC name, you can use the name sbc.contoso.com.</span></span> <span data-ttu-id="e0800-140">如果您嘗試將 SBC 與 name （contoso..）結合使用，系統將不會讓您，因為該域不是由這個租使用者所擁有。</span><span class="sxs-lookup"><span data-stu-id="e0800-140">If you try to pair the SBC with a name sbc.contoso.abc, the system will not let you, as the domain is not owned by this tenant.</span></span><br/>
  > <span data-ttu-id="e0800-141">除了在您的租使用者中註冊的網域外，請務必先擁有該網域的使用者以及指派的 E3 或 E5 授權。</span><span class="sxs-lookup"><span data-stu-id="e0800-141">In addition to the domain registered in your tenant, it is important that there is a user with that domain and an assigned E3 or E5 license.</span></span> <span data-ttu-id="e0800-142">如果不是，您會收到下列錯誤：</span><span class="sxs-lookup"><span data-stu-id="e0800-142">If not, you will receive the following error:</span></span><br/>
  <span data-ttu-id="e0800-143">`Can not use the “sbc.contoso.com” domain as it was not configured for this tenant`.</span><span class="sxs-lookup"><span data-stu-id="e0800-143">`Can not use the “sbc.contoso.com” domain as it was not configured for this tenant`.</span></span>

```PowerShell
New-CsOnlinePSTNGateway -Identity sbc.contoso.com -Enabled $true -SipSignalingPort 5067 -MaxConcurrentSessions 100 
```
<span data-ttu-id="e0800-144">回報</span><span class="sxs-lookup"><span data-stu-id="e0800-144">Returns:</span></span>
<pre>
Identity              : sbc.contoso.com 
Fqdn                  : sbc.contoso.com 
SipSignalingPort     : 5067 
FailoverTimeSeconds   : 10 
ForwardCallHistory    : False 
ForwardPai            : False 
SendSipOptions        : True 
MaxConcurrentSessions : 100 
Enabled               : True   
</pre>
<span data-ttu-id="e0800-145">您可以在配對處理期間設定其他選項。</span><span class="sxs-lookup"><span data-stu-id="e0800-145">There are additional options that can be set during the pairing process.</span></span> <span data-ttu-id="e0800-146">不過，在前面的範例中，只會顯示所需的最低參數。</span><span class="sxs-lookup"><span data-stu-id="e0800-146">In the previous example, however, only the minimum required parameters are shown.</span></span> 
 
<span data-ttu-id="e0800-147">下表列出您可以在設定參數時使用的其他參數```New-CsOnlinePstnGateway```。</span><span class="sxs-lookup"><span data-stu-id="e0800-147">The following table lists the additional parameters that you can use in setting parameters for ```New-CsOnlinePstnGateway```.</span></span>

|<span data-ttu-id="e0800-148">必填？</span><span class="sxs-lookup"><span data-stu-id="e0800-148">Required?</span></span>|<span data-ttu-id="e0800-149">名稱</span><span class="sxs-lookup"><span data-stu-id="e0800-149">Name</span></span>|<span data-ttu-id="e0800-150">描述</span><span class="sxs-lookup"><span data-stu-id="e0800-150">Description</span></span>|<span data-ttu-id="e0800-151">設置</span><span class="sxs-lookup"><span data-stu-id="e0800-151">Default</span></span>|<span data-ttu-id="e0800-152">可能值</span><span class="sxs-lookup"><span data-stu-id="e0800-152">Possible values</span></span>|<span data-ttu-id="e0800-153">類型與限制</span><span class="sxs-lookup"><span data-stu-id="e0800-153">Type and restrictions</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="e0800-154">是</span><span class="sxs-lookup"><span data-stu-id="e0800-154">Yes</span></span>|<span data-ttu-id="e0800-155">稱</span><span class="sxs-lookup"><span data-stu-id="e0800-155">FQDN</span></span>|<span data-ttu-id="e0800-156">SBC 的 FQDN 名稱</span><span class="sxs-lookup"><span data-stu-id="e0800-156">The FQDN name of the SBC</span></span> |<span data-ttu-id="e0800-157">無</span><span class="sxs-lookup"><span data-stu-id="e0800-157">None</span></span>|<span data-ttu-id="e0800-158">NoneFQDN name，限制63字元</span><span class="sxs-lookup"><span data-stu-id="e0800-158">NoneFQDN name, limit 63 characters</span></span>|<span data-ttu-id="e0800-159">在[Active Directory 中針對電腦、網域、網站和組織單位命名慣例](https://support.microsoft.com/help/909264)的允許和禁止字元清單</span><span class="sxs-lookup"><span data-stu-id="e0800-159">String, list of allowed and disallowed characters on [Naming conventions in Active Directory for computers, domains, sites, and OUs](https://support.microsoft.com/help/909264)</span></span>|
|<span data-ttu-id="e0800-160">否</span><span class="sxs-lookup"><span data-stu-id="e0800-160">No</span></span>|<span data-ttu-id="e0800-161">MediaBypass</span><span class="sxs-lookup"><span data-stu-id="e0800-161">MediaBypass</span></span> |<span data-ttu-id="e0800-162">指示 SBC 的參數支援「媒體旁路」，且系統管理員想要使用它。</span><span class="sxs-lookup"><span data-stu-id="e0800-162">Parameter indicated of the SBC supports Media Bypass and the administrator wants to use it.</span></span>|<span data-ttu-id="e0800-163">無</span><span class="sxs-lookup"><span data-stu-id="e0800-163">None</span></span>|<span data-ttu-id="e0800-164">滿足</span><span class="sxs-lookup"><span data-stu-id="e0800-164">True</span></span><br/><span data-ttu-id="e0800-165">虛假</span><span class="sxs-lookup"><span data-stu-id="e0800-165">False</span></span>|<span data-ttu-id="e0800-166">Boolean</span><span class="sxs-lookup"><span data-stu-id="e0800-166">Boolean</span></span>|
|<span data-ttu-id="e0800-167">是</span><span class="sxs-lookup"><span data-stu-id="e0800-167">Yes</span></span>|<span data-ttu-id="e0800-168">SipSignalingPort</span><span class="sxs-lookup"><span data-stu-id="e0800-168">SipSignalingPort</span></span> |<span data-ttu-id="e0800-169">使用傳輸層安全性（TLS）通訊協定，與直接路由服務通訊時所使用的偵聽埠。</span><span class="sxs-lookup"><span data-stu-id="e0800-169">Listening port used for communicating with Direct Routing services by using the Transport Layer Security (TLS) protocol.</span></span>|<span data-ttu-id="e0800-170">無</span><span class="sxs-lookup"><span data-stu-id="e0800-170">None</span></span>|<span data-ttu-id="e0800-171">任何埠</span><span class="sxs-lookup"><span data-stu-id="e0800-171">Any port</span></span>|<span data-ttu-id="e0800-172">0到65535</span><span class="sxs-lookup"><span data-stu-id="e0800-172">0 to 65535</span></span> |
|<span data-ttu-id="e0800-173">否</span><span class="sxs-lookup"><span data-stu-id="e0800-173">No</span></span>|<span data-ttu-id="e0800-174">FailoverTimeSeconds</span><span class="sxs-lookup"><span data-stu-id="e0800-174">FailoverTimeSeconds</span></span> |<span data-ttu-id="e0800-175">當設定為10（預設值）時，閘道不會在10秒內應答的輸出呼叫會路由至下一個可用的幹線;如果沒有其他 trunks，就會自動中斷通話。</span><span class="sxs-lookup"><span data-stu-id="e0800-175">When set to 10 (default value), outbound calls that are not answered by the gateway within 10 seconds are routed to the next available trunk; if there are no additional trunks, then the call is automatically dropped.</span></span> <span data-ttu-id="e0800-176">組織的網路速度與閘道回應速度若是很慢，可能會造成來電不必要地遭到掛斷。</span><span class="sxs-lookup"><span data-stu-id="e0800-176">In an organization with slow networks and gateway responses, that could potentially result in calls being dropped unnecessarily.</span></span> <span data-ttu-id="e0800-177">預設值為10。</span><span class="sxs-lookup"><span data-stu-id="e0800-177">The default value is 10.</span></span>|<span data-ttu-id="e0800-178">第</span><span class="sxs-lookup"><span data-stu-id="e0800-178">10</span></span>|<span data-ttu-id="e0800-179">電話</span><span class="sxs-lookup"><span data-stu-id="e0800-179">Number</span></span>|<span data-ttu-id="e0800-180">Int</span><span class="sxs-lookup"><span data-stu-id="e0800-180">Int</span></span>|
|<span data-ttu-id="e0800-181">否</span><span class="sxs-lookup"><span data-stu-id="e0800-181">No</span></span>|<span data-ttu-id="e0800-182">ForwardCallHistory</span><span class="sxs-lookup"><span data-stu-id="e0800-182">ForwardCallHistory</span></span> |<span data-ttu-id="e0800-183">指出是否透過主幹轉送通話記錄資訊。</span><span class="sxs-lookup"><span data-stu-id="e0800-183">Indicates whether call history information will be forwarded through the trunk.</span></span> <span data-ttu-id="e0800-184">如果啟用，Office 365 PSTN Proxy 會傳送兩個標頭： [歷程記錄] 資訊和 [參照者]。</span><span class="sxs-lookup"><span data-stu-id="e0800-184">If enabled, the Office 365 PSTN Proxy sends two headers: History-info and Referred-By.</span></span> <span data-ttu-id="e0800-185">預設值為**False** （$False）。</span><span class="sxs-lookup"><span data-stu-id="e0800-185">The default value is **False** ($False).</span></span> |<span data-ttu-id="e0800-186">虛假</span><span class="sxs-lookup"><span data-stu-id="e0800-186">False</span></span>|<span data-ttu-id="e0800-187">滿足</span><span class="sxs-lookup"><span data-stu-id="e0800-187">True</span></span><br/><span data-ttu-id="e0800-188">虛假</span><span class="sxs-lookup"><span data-stu-id="e0800-188">False</span></span>|<span data-ttu-id="e0800-189">Boolean</span><span class="sxs-lookup"><span data-stu-id="e0800-189">Boolean</span></span>|
|<span data-ttu-id="e0800-190">否</span><span class="sxs-lookup"><span data-stu-id="e0800-190">No</span></span>|<span data-ttu-id="e0800-191">ForwardPAI</span><span class="sxs-lookup"><span data-stu-id="e0800-191">ForwardPAI</span></span>|<span data-ttu-id="e0800-192">指出 P-Asserted-Identity (PAI) 標頭是否要隨通話轉接。</span><span class="sxs-lookup"><span data-stu-id="e0800-192">Indicates whether the P-Asserted-Identity (PAI) header will be forwarded along with the call.</span></span> <span data-ttu-id="e0800-193">PAI 標頭可用於驗證來電者的身分識別。</span><span class="sxs-lookup"><span data-stu-id="e0800-193">The PAI header provides a way to verify the identity of the caller.</span></span> <span data-ttu-id="e0800-194">如果啟用，則也會傳送隱私權： ID 標頭。</span><span class="sxs-lookup"><span data-stu-id="e0800-194">If enabled the Privacy:ID header will also be sent.</span></span> <span data-ttu-id="e0800-195">預設值為**False** （$False）。</span><span class="sxs-lookup"><span data-stu-id="e0800-195">The default value is **False** ($False).</span></span>|<span data-ttu-id="e0800-196">虛假</span><span class="sxs-lookup"><span data-stu-id="e0800-196">False</span></span>|<span data-ttu-id="e0800-197">滿足</span><span class="sxs-lookup"><span data-stu-id="e0800-197">True</span></span><br/><span data-ttu-id="e0800-198">虛假</span><span class="sxs-lookup"><span data-stu-id="e0800-198">False</span></span>|<span data-ttu-id="e0800-199">Boolean</span><span class="sxs-lookup"><span data-stu-id="e0800-199">Boolean</span></span>|
|<span data-ttu-id="e0800-200">否</span><span class="sxs-lookup"><span data-stu-id="e0800-200">No</span></span>|<span data-ttu-id="e0800-201">SendSIPOptions</span><span class="sxs-lookup"><span data-stu-id="e0800-201">SendSIPOptions</span></span> |<span data-ttu-id="e0800-202">定義 SBC 是否將傳送 SIP 選項。</span><span class="sxs-lookup"><span data-stu-id="e0800-202">Defines if an SBC will or will not send the SIP options.</span></span> <span data-ttu-id="e0800-203">如果停用，則會將 SBC 排除在監視及觸發系統中。</span><span class="sxs-lookup"><span data-stu-id="e0800-203">If disabled, the SBC will be excluded from Monitoring and Alerting system.</span></span> <span data-ttu-id="e0800-204">我們強烈建議您啟用 SIP 選項。</span><span class="sxs-lookup"><span data-stu-id="e0800-204">We highly recommend that you enable SIP options.</span></span> <span data-ttu-id="e0800-205">預設值為**True**。</span><span class="sxs-lookup"><span data-stu-id="e0800-205">Default value is **True**.</span></span> |<span data-ttu-id="e0800-206">滿足</span><span class="sxs-lookup"><span data-stu-id="e0800-206">True</span></span>|<span data-ttu-id="e0800-207">滿足</span><span class="sxs-lookup"><span data-stu-id="e0800-207">True</span></span><br/><span data-ttu-id="e0800-208">虛假</span><span class="sxs-lookup"><span data-stu-id="e0800-208">False</span></span>|<span data-ttu-id="e0800-209">Boolean</span><span class="sxs-lookup"><span data-stu-id="e0800-209">Boolean</span></span>|
|<span data-ttu-id="e0800-210">否</span><span class="sxs-lookup"><span data-stu-id="e0800-210">No</span></span>|<span data-ttu-id="e0800-211">MaxConcurrentSessions</span><span class="sxs-lookup"><span data-stu-id="e0800-211">MaxConcurrentSessions</span></span> |<span data-ttu-id="e0800-212">由觸發系統所使用。</span><span class="sxs-lookup"><span data-stu-id="e0800-212">Used by alerting system.</span></span> <span data-ttu-id="e0800-213">設定任何值後，當併發會話數量為90% 或高於此值時，警示系統會在租使用者管理員產生警示。</span><span class="sxs-lookup"><span data-stu-id="e0800-213">When any value is set, the alerting system will generate an alert to the tenant administrator when the number of concurrent session is 90% or higher than this value.</span></span> <span data-ttu-id="e0800-214">如果未設定參數，就不會產生預警。</span><span class="sxs-lookup"><span data-stu-id="e0800-214">If parameter is not set, the alerts are not generated.</span></span> <span data-ttu-id="e0800-215">不過，監視系統會在每24小時報告併發會話數目。</span><span class="sxs-lookup"><span data-stu-id="e0800-215">However, the monitoring system will report number of concurrent session every 24 hours.</span></span> |<span data-ttu-id="e0800-216">非</span><span class="sxs-lookup"><span data-stu-id="e0800-216">Null</span></span>|<span data-ttu-id="e0800-217">非</span><span class="sxs-lookup"><span data-stu-id="e0800-217">Null</span></span><br/><span data-ttu-id="e0800-218">1到100000</span><span class="sxs-lookup"><span data-stu-id="e0800-218">1 to 100,000</span></span> ||
|<span data-ttu-id="e0800-219">否</span><span class="sxs-lookup"><span data-stu-id="e0800-219">No</span></span>|<span data-ttu-id="e0800-220">MediaRelayRoutingLocationOverride</span><span class="sxs-lookup"><span data-stu-id="e0800-220">MediaRelayRoutingLocationOverride</span></span> |<span data-ttu-id="e0800-221">允許手動選取媒體路徑。</span><span class="sxs-lookup"><span data-stu-id="e0800-221">Allows selecting path for media manually.</span></span> <span data-ttu-id="e0800-222">[直接傳送] 會根據 SBC 的公用 IP，指派媒體路徑的資料中心。</span><span class="sxs-lookup"><span data-stu-id="e0800-222">Direct Routing assigns a datacenter for media path based on the public IP of the SBC.</span></span> <span data-ttu-id="e0800-223">我們總是選取最接近 SBC 資料中心的資料。</span><span class="sxs-lookup"><span data-stu-id="e0800-223">We always select closest to the SBC datacenter.</span></span> <span data-ttu-id="e0800-224">不過，在某些情況下，來自例如美國範圍的公用 IP 可以指派給位於歐洲的 SBC。</span><span class="sxs-lookup"><span data-stu-id="e0800-224">However, in some cases a public IP from for example a US range can be assigned to an SBC located in Europe.</span></span> <span data-ttu-id="e0800-225">在這種情況下，我們會使用不是最佳的媒體路徑。</span><span class="sxs-lookup"><span data-stu-id="e0800-225">In this case we will be using not optimal media path.</span></span> <span data-ttu-id="e0800-226">這個參數可讓您手動設定媒體流量的首選區域。</span><span class="sxs-lookup"><span data-stu-id="e0800-226">This parameter allows manually set the preferred region for media traffic.</span></span> <span data-ttu-id="e0800-227">我們只建議在通話記錄中清楚指出自動指派媒體路徑的 datacenter，不會指派最接近 SBC 資料中心的資料中心。</span><span class="sxs-lookup"><span data-stu-id="e0800-227">We only recommend setting this parameter if the call logs clearly indicate that automatic assignment of the datacenter for media path does not assign the closest to the SBC datacenter.</span></span> |<span data-ttu-id="e0800-228">無</span><span class="sxs-lookup"><span data-stu-id="e0800-228">None</span></span>|<span data-ttu-id="e0800-229">ISO 格式的國家/地區代碼</span><span class="sxs-lookup"><span data-stu-id="e0800-229">Country codes in ISO format</span></span>||
|<span data-ttu-id="e0800-230">否</span><span class="sxs-lookup"><span data-stu-id="e0800-230">No</span></span>|<span data-ttu-id="e0800-231">後</span><span class="sxs-lookup"><span data-stu-id="e0800-231">Enabled</span></span>|<span data-ttu-id="e0800-232">用來針對撥出通話啟用這個 SBC。</span><span class="sxs-lookup"><span data-stu-id="e0800-232">Used to enable this SBC for outbound calls.</span></span> <span data-ttu-id="e0800-233">可用於暫時移除 SBC，或在進行更新或在維護期間進行。</span><span class="sxs-lookup"><span data-stu-id="e0800-233">Can be used to temporarily remove the SBC, while it is being updated or during maintenance.</span></span> |<span data-ttu-id="e0800-234">虛假</span><span class="sxs-lookup"><span data-stu-id="e0800-234">False</span></span>|<span data-ttu-id="e0800-235">滿足</span><span class="sxs-lookup"><span data-stu-id="e0800-235">True</span></span><br/><span data-ttu-id="e0800-236">虛假</span><span class="sxs-lookup"><span data-stu-id="e0800-236">False</span></span>|<span data-ttu-id="e0800-237">Boolean</span><span class="sxs-lookup"><span data-stu-id="e0800-237">Boolean</span></span>|
 
### <a name="verify-the-sbc-pairing"></a><span data-ttu-id="e0800-238">驗證 SBC 配對</span><span class="sxs-lookup"><span data-stu-id="e0800-238">Verify the SBC pairing</span></span> 

<span data-ttu-id="e0800-239">確認連線：</span><span class="sxs-lookup"><span data-stu-id="e0800-239">Verify the connection:</span></span> 
- <span data-ttu-id="e0800-240">檢查 SBC 是否在成對的 SBCs 清單中。</span><span class="sxs-lookup"><span data-stu-id="e0800-240">Check if the SBC is on the list of paired SBCs.</span></span> 
- <span data-ttu-id="e0800-241">驗證 SIP 選項。</span><span class="sxs-lookup"><span data-stu-id="e0800-241">Validate SIP Options.</span></span> 
 
#### <a name="validate-if-the-sbc-is-on-the-list-of-paired-sbcs"></a><span data-ttu-id="e0800-242">驗證 SBC 是否在成對半形的清單中</span><span class="sxs-lookup"><span data-stu-id="e0800-242">Validate if the SBC is on the list of paired SBCs</span></span> 

<span data-ttu-id="e0800-243">在您配對 SBC 之後，請在遠端 PowerShell 會話中執行下列命令，以驗證 SBC 是否出現在成對的 SBCs 清單中：`Get-CSOnlinePSTNGateway`</span><span class="sxs-lookup"><span data-stu-id="e0800-243">After you pair the SBC, validate that the SBC is present in the list of paired SBCs by running the following command in a remote PowerShell session: `Get-CSOnlinePSTNGateway`</span></span>

<span data-ttu-id="e0800-244">成對閘道應該會出現在清單中，如下列範例所示，然後確認**Enabled**參數顯示的值**為 True**。</span><span class="sxs-lookup"><span data-stu-id="e0800-244">The paired gateway should appear in the list as shown in the example below, and verify that the **Enabled** parameter  displays a value of **True**.</span></span> <span data-ttu-id="e0800-245">鍵</span><span class="sxs-lookup"><span data-stu-id="e0800-245">Enter:</span></span>

```PowerShell
Get-CsOnlinePSTNGateway -Identity sbc.contoso.com  
```
<span data-ttu-id="e0800-246">返回：</span><span class="sxs-lookup"><span data-stu-id="e0800-246">Which returns:</span></span>
<pre>
Identity              : sbc.contoso.com  
Fqdn                  : sbc.contoso.com 
SipSignalingPort     : 5067 
CodecPriority         : SILKWB,SILKNB,PCMU,PCMA 
ExcludedCodecs        :  
FailoverTimeSeconds   : 10 
ForwardCallHistory    : False 
ForwardPai            : False 
SendSipOptions        : True 
MaxConcurrentSessions : 100 
Enabled               : True 
</pre>

#### <a name="validate-sip-options-flow"></a><span data-ttu-id="e0800-247">驗證 SIP 選項流程</span><span class="sxs-lookup"><span data-stu-id="e0800-247">Validate SIP Options flow</span></span> 

<span data-ttu-id="e0800-248">若要使用外寄 SIP 選項驗證配對，請使用 SBC 管理介面，並確認 SBC 是否收到其外寄選項訊息的 200 OK 回應。</span><span class="sxs-lookup"><span data-stu-id="e0800-248">To validate the pairing using outgoing SIP Options, use the SBC management interface and confirm that the SBC receives 200 OK responses to its outgoing OPTIONS messages.</span></span>

<span data-ttu-id="e0800-249">當直接路由查看內送的選項時，它會開始將傳出的 SIP 選項訊息傳送到 [傳入選項] 訊息中的 [連絡人頭] 欄位中設定的 SBC FQDN。</span><span class="sxs-lookup"><span data-stu-id="e0800-249">When Direct Routing sees incoming OPTIONS, it will start sending outgoing SIP Options messages to the SBC FQDN configured in the Contact header field in the incoming OPTIONS message.</span></span> 

<span data-ttu-id="e0800-250">若要使用傳入的 SIP 選項驗證配對，請使用 SBC 管理介面，並查看 SBC 會傳送回復給來自直接路由的選項訊息，且其傳送的回應代碼為 200 OK。</span><span class="sxs-lookup"><span data-stu-id="e0800-250">To validate the pairing using incoming SIP Options, use the SBC management interface and see that the SBC sends a reply to the OPTIONS messages coming in from Direct Routing and that the response code it sends is 200 OK.</span></span>

## <a name="enable-users-for-direct-routing-service"></a><span data-ttu-id="e0800-251">允許使用者使用直接路由服務</span><span class="sxs-lookup"><span data-stu-id="e0800-251">Enable users for Direct Routing Service</span></span> 

<span data-ttu-id="e0800-252">當您準備好要讓使用者使用直接路由服務時，請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="e0800-252">When you are ready to enable users for the Direct Routing Service, follow these steps:</span></span> 

1. <span data-ttu-id="e0800-253">在 Office 365 中建立使用者並指派電話系統授權。</span><span class="sxs-lookup"><span data-stu-id="e0800-253">Create a user in Office 365 and assign a phone system license.</span></span> 
2. <span data-ttu-id="e0800-254">確定使用者是駐留在商務用 Skype Online 中。</span><span class="sxs-lookup"><span data-stu-id="e0800-254">Ensure that the user is homed in Skype for Business Online.</span></span> 
3. <span data-ttu-id="e0800-255">設定電話號碼，並啟用企業語音及語音信箱。</span><span class="sxs-lookup"><span data-stu-id="e0800-255">Configure the phone number and enable enterprise voice and voicemail.</span></span> 
4. <span data-ttu-id="e0800-256">設定語音路由。</span><span class="sxs-lookup"><span data-stu-id="e0800-256">Configure voice routing.</span></span> <span data-ttu-id="e0800-257">此路線會自動驗證。</span><span class="sxs-lookup"><span data-stu-id="e0800-257">The route is automatically validated.</span></span>

### <a name="create-a-user-in-office-365-and-assign-the-license"></a><span data-ttu-id="e0800-258">在 Office 365 中建立使用者並指派授權</span><span class="sxs-lookup"><span data-stu-id="e0800-258">Create a user in Office 365 and assign the license</span></span> 

<span data-ttu-id="e0800-259">在 Office 365 中建立新使用者有兩個選項。</span><span class="sxs-lookup"><span data-stu-id="e0800-259">There are two options for creating a new user in Office 365.</span></span> <span data-ttu-id="e0800-260">不過，建議您的組織選取並使用其中一個選項來避免路由問題：</span><span class="sxs-lookup"><span data-stu-id="e0800-260">However, we recommend that your organization select and use one option to avoid routing issues:</span></span> 

- <span data-ttu-id="e0800-261">在內部部署的 Active Directory 中建立使用者，並將使用者同步處理到雲端。</span><span class="sxs-lookup"><span data-stu-id="e0800-261">Create the user in on-premises Active Directory and sync the user to the cloud.</span></span> <span data-ttu-id="e0800-262">請參閱[將您的內部部署目錄與 Azure Active Directory 整合](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect)。</span><span class="sxs-lookup"><span data-stu-id="e0800-262">See [Integrate your on-premises directories with Azure Active Directory](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).</span></span>
- <span data-ttu-id="e0800-263">直接在 Office 365 管理員入口網站中建立使用者。</span><span class="sxs-lookup"><span data-stu-id="e0800-263">Create the user directly in the Office 365 Administrator Portal.</span></span> <span data-ttu-id="e0800-264">請參閱[個別或大量將使用者新增至 Office 365-系統管理協助](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec)。</span><span class="sxs-lookup"><span data-stu-id="e0800-264">See [Add users individually or in bulk to Office 365 - Admin Help](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec).</span></span> 

<span data-ttu-id="e0800-265">如果您的商務用 skype Online 部署與商務用 Skype 2015 或 Lync 2010/2013 內部部署共同存在，則支援的唯一選項是在內部部署 Active Directory 中建立使用者，並將使用者同步處理到雲端（選項1）。</span><span class="sxs-lookup"><span data-stu-id="e0800-265">If your Skype for Business Online deployment co-exists with Skype for Business 2015 or Lync 2010/2013 on-premises, the only supported option is to create the user in on-premises Active Directory and sync the user to the cloud (Option 1).</span></span> 

<span data-ttu-id="e0800-266">如需授權需求的相關資訊，請參閱[規劃直接路由](direct-routing-plan.md)中的[授權和其他需求](direct-routing-plan.md#licensing-and-other-requirements)。</span><span class="sxs-lookup"><span data-stu-id="e0800-266">For information about license requirements, see [licensing and other requirements](direct-routing-plan.md#licensing-and-other-requirements) in [Plan Direct Routing](direct-routing-plan.md).</span></span>

### <a name="ensure-that-the-user-is-homed-in-skype-for-business-online"></a><span data-ttu-id="e0800-267">確定使用者是在商務用 Skype Online 中託管</span><span class="sxs-lookup"><span data-stu-id="e0800-267">Ensure that the user is homed in Skype for Business Online</span></span> 

<span data-ttu-id="e0800-268">[直接傳送] 要求使用者駐留在商務用 Skype Online 中。</span><span class="sxs-lookup"><span data-stu-id="e0800-268">Direct Routing requires the user to be homed in Skype for Business Online.</span></span> <span data-ttu-id="e0800-269">您可以透過查看 RegistrarPool 參數來檢查此情況。</span><span class="sxs-lookup"><span data-stu-id="e0800-269">You can check this by looking at the RegistrarPool parameter.</span></span> <span data-ttu-id="e0800-270">它必須在 infra.lync.com 網域中有一個值。</span><span class="sxs-lookup"><span data-stu-id="e0800-270">It needs to have a value in the infra.lync.com domain.</span></span>

1. <span data-ttu-id="e0800-271">[連線至遠端 PowerShell]。</span><span class="sxs-lookup"><span data-stu-id="e0800-271">Connect to remote PowerShell.</span></span>
2. <span data-ttu-id="e0800-272">發出命令：</span><span class="sxs-lookup"><span data-stu-id="e0800-272">Issue the command:</span></span> 

    ```PowerShell
    Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool
    ``` 

### <a name="configure-the-phone-number-and-enable-enterprise-voice-and-voicemail"></a><span data-ttu-id="e0800-273">設定電話號碼並啟用企業語音及語音信箱</span><span class="sxs-lookup"><span data-stu-id="e0800-273">Configure the phone number and enable enterprise voice and voicemail</span></span> 

<span data-ttu-id="e0800-274">在您建立使用者並指派授權之後，下一步就是設定他們的電話號碼和語音信箱。</span><span class="sxs-lookup"><span data-stu-id="e0800-274">After you have created the user and assigned a license, the next step is to configure their phone number and voicemail.</span></span> <span data-ttu-id="e0800-275">這可以一步完成。</span><span class="sxs-lookup"><span data-stu-id="e0800-275">This can be done in one step.</span></span> 

<span data-ttu-id="e0800-276">若要新增電話號碼並啟用語音信箱：</span><span class="sxs-lookup"><span data-stu-id="e0800-276">To add the phone number and enable for voicemail:</span></span>
 
1. <span data-ttu-id="e0800-277">連線到遠端 PowerShell 會話。</span><span class="sxs-lookup"><span data-stu-id="e0800-277">Connect to a remote PowerShell session.</span></span> 
2. <span data-ttu-id="e0800-278">輸入命令：</span><span class="sxs-lookup"><span data-stu-id="e0800-278">Enter the command:</span></span> 
 
    ```PowerShell
    Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI tel:<E.164 phone number>
    ```

    <span data-ttu-id="e0800-279">例如，若要將使用者的電話號碼新增至 [Spencer Low]，您可以輸入下列專案：</span><span class="sxs-lookup"><span data-stu-id="e0800-279">For example, to add a phone number for user "Spencer Low," you would enter the following:</span></span> 

    ```PowerShell
    Set-CsUser -Identity "Spencer Low" -OnPremLineURI tel:+14255388797 -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
    ```

    <span data-ttu-id="e0800-280">所使用的電話號碼必須設定為完整的 E. 164 電話號碼（國家/地區碼）。</span><span class="sxs-lookup"><span data-stu-id="e0800-280">The phone number used has to be configured as a full E.164 phone number with country code.</span></span> 

      > [!NOTE]
      > <span data-ttu-id="e0800-281">如果使用者的電話號碼是在內部部署管理，請使用內部部署商務用 Skype 管理命令介面或 [控制台] 來設定使用者的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="e0800-281">If the user’s phone number is managed on premises, use on-premises Skype for Business Management Shell or Control Panel to configure the user's phone number.</span></span> 

### <a name="configure-voice-routing"></a><span data-ttu-id="e0800-282">設定語音路由</span><span class="sxs-lookup"><span data-stu-id="e0800-282">Configure Voice Routing</span></span> 

<span data-ttu-id="e0800-283">Microsoft Phone 系統有一個路由機制，可讓您根據下列情況，將呼叫傳送到特定的 SBC：</span><span class="sxs-lookup"><span data-stu-id="e0800-283">Microsoft Phone System has a routing mechanism that allows a call to be sent to a specific SBC based on:</span></span> 

- <span data-ttu-id="e0800-284">名為 [數位模式]</span><span class="sxs-lookup"><span data-stu-id="e0800-284">Called number pattern</span></span> 
- <span data-ttu-id="e0800-285">撥打電話的電話號碼模式 + 特定使用者</span><span class="sxs-lookup"><span data-stu-id="e0800-285">Called number pattern + Specific User who makes the call</span></span>
 
<span data-ttu-id="e0800-286">SBCs 可以指定為 [作用中] 和 [備份]。</span><span class="sxs-lookup"><span data-stu-id="e0800-286">SBCs can be designated as active and backup.</span></span> <span data-ttu-id="e0800-287">這表示當針對此數值模式設定為作用中的 SBC，或數位模式 + 特定使用者時，會將呼叫路由至備份 SBC。</span><span class="sxs-lookup"><span data-stu-id="e0800-287">That means when the SBC that is configured as active for this number pattern, or number pattern + specific user, is not available, then the calls will be routed to a backup SBC.</span></span>
 
<span data-ttu-id="e0800-288">[通話路由] 是由下列元素所組成：</span><span class="sxs-lookup"><span data-stu-id="e0800-288">Call routing is made up of the following elements:</span></span> 
- <span data-ttu-id="e0800-289">語音路由策略– PSTN 用途的容器;可以指派給使用者或多位使用者</span><span class="sxs-lookup"><span data-stu-id="e0800-289">Voice Routing Policy – container for PSTN Usages; can be assigned to a user or to multiple users</span></span> 
- <span data-ttu-id="e0800-290">PSTN 用途–語音路由和 PSTN 用途的容器;可以在不同的語音路由策略中共用</span><span class="sxs-lookup"><span data-stu-id="e0800-290">PSTN Usages – container for Voice Routes and PSTN Usages; can be shared in different Voice Routing Policies</span></span> 
- <span data-ttu-id="e0800-291">語音路由-數位模式和一組線上 PSTN 閘道，用於撥打電話號碼符合模式的電話</span><span class="sxs-lookup"><span data-stu-id="e0800-291">Voice Routes – number pattern and set of Online PSTN Gateways to use for calls where calling number matches the pattern</span></span> 
- <span data-ttu-id="e0800-292">線上 PSTN 閘道-指向 SBC 的指標也會儲存透過 SBC 發出呼叫時所套用的設定，例如轉寄 P 斷言身分識別（PAI）或首選編解碼器。可以新增到語音路由</span><span class="sxs-lookup"><span data-stu-id="e0800-292">Online PSTN Gateway - pointer to an SBC, also stores the configuration that is applied when call is placed via the SBC, such as forward P-Asserted-Identity (PAI) or Preferred Codecs; can be added to Voice Routes</span></span> 

#### <a name="creating-a-voice-routing-policy-with-one-pstn-usage"></a><span data-ttu-id="e0800-293">建立具有一個 PSTN 使用量的語音路由策略</span><span class="sxs-lookup"><span data-stu-id="e0800-293">Creating a voice routing policy with one PSTN Usage</span></span> 

<span data-ttu-id="e0800-294">下圖顯示通話流程中的語音路由策略的兩個範例。</span><span class="sxs-lookup"><span data-stu-id="e0800-294">The following diagram shows two examples of voice routing policies in call flow.</span></span>

<span data-ttu-id="e0800-295">**通話流程1（在左邊）：** 如果使用者撥打電話給 + 1 425 XXX XX 或 + 1 206 XXX XX xx，該通話會路由至 SBC sbc1.contoso.biz 或 sbc2.contoso.biz。</span><span class="sxs-lookup"><span data-stu-id="e0800-295">**Call Flow 1 (on the left):** If a user makes a call to +1 425 XXX XX XX or +1 206 XXX XX XX, the call is routed to SBC sbc1.contoso.biz or sbc2.contoso.biz.</span></span> <span data-ttu-id="e0800-296">如果 sbc1.contoso.biz 和 sbc2.contoso.biz 都無法使用，就會掛斷通話。</span><span class="sxs-lookup"><span data-stu-id="e0800-296">If neither sbc1.contoso.biz nor sbc2.contoso.biz are available, the call is dropped.</span></span> 

<span data-ttu-id="e0800-297">**通話流程2（右側）：** 如果使用者撥打電話給 + 1 425 XXX XX 或 + 1 206 XXX XX xx，該通話就會先路由至 SBC sbc1.contoso.biz 或 sbc2.contoso.biz。</span><span class="sxs-lookup"><span data-stu-id="e0800-297">**Call Flow 2 (on the right):** If a user makes a call to +1 425 XXX XX XX or +1 206 XXX XX XX, the call is first routed to SBC sbc1.contoso.biz or sbc2.contoso.biz.</span></span> <span data-ttu-id="e0800-298">如果沒有可用的 SBC，則會嘗試使用較低優先順序的路由（sbc3.contoso.biz 和 sbc4.contoso.biz）。</span><span class="sxs-lookup"><span data-stu-id="e0800-298">If neither SBC is available, the route with lower priority will be tried (sbc3.contoso.biz and sbc4.contoso.biz).</span></span> <span data-ttu-id="e0800-299">如果沒有任何 SBCs 可用，就會中斷通話。</span><span class="sxs-lookup"><span data-stu-id="e0800-299">If none of the SBCs are available, the call is dropped.</span></span> 

![顯示語音路由策略範例](media/ConfigDirectRouting-VoiceRoutingPolicyExamples.png)

<span data-ttu-id="e0800-301">在這兩個範例中，雖然語音路由是指派優先順序，但路由中的 SBCs 會以隨機順序嘗試。</span><span class="sxs-lookup"><span data-stu-id="e0800-301">In both examples, while the Voice Route is assigned priorities, the SBCs in the routes are tried in random order.</span></span>

  > [!NOTE]
  > <span data-ttu-id="e0800-302">除非使用者也有 Microsoft 通話方案授權，否則呼叫範例設定中的 [除了模式 + 1 425 XXX xx xx] 或 [+ 1 206 XXX xx xx] 以外的任何號碼。</span><span class="sxs-lookup"><span data-stu-id="e0800-302">Unless the user also has a Microsoft Calling Plan license, calls to any number except numbers matching the patterns +1 425 XXX XX XX or +1 206 XXX XX XX in the example configuration are dropped.</span></span> <span data-ttu-id="e0800-303">如果使用者有通話方案授權，通話會根據 Microsoft 通話方案的原則自動傳送。</span><span class="sxs-lookup"><span data-stu-id="e0800-303">If the user has a Calling Plan license, the call is automatically routed according to the policies of the Microsoft Calling Plan.</span></span> 

<span data-ttu-id="e0800-304">Microsoft 通話方案會自動套用為所有擁有 Microsoft 通話方案授權的使用者，而且不需要額外的呼叫路由設定。</span><span class="sxs-lookup"><span data-stu-id="e0800-304">The Microsoft Calling Plan applies automatically as the last route to all users with the Microsoft Calling Plan license and does not require additional call routing configuration.</span></span>

<span data-ttu-id="e0800-305">在下圖所示的範例中，新增了語音信箱，以傳送來電給所有其他美國和加拿大的號碼（移至撥打電話號碼模式 + 1 XXX XXX xx XX 的通話）。</span><span class="sxs-lookup"><span data-stu-id="e0800-305">In the example shown in the following diagram, a voice route is added to send calls to all other US and Canadian number (calls that go to called number pattern +1 XXX XXX XX XX).</span></span>

![顯示含有第三個路線的語音路由策略](media/ConfigDirectRouting-VoiceRoutingPolicywith3rdroute.png)

<span data-ttu-id="e0800-307">針對所有其他通話，如果使用者同時擁有兩個授權（Microsoft 手機系統和 Microsoft 通話方案），則會使用自動路由。</span><span class="sxs-lookup"><span data-stu-id="e0800-307">For all other calls, if a user has both licenses (Microsoft Phone System and Microsoft Calling Plan), Automatic Route is used.</span></span> <span data-ttu-id="e0800-308">如果沒有與管理員建立的線上語音路線中的數位模式相符，請透過 Microsoft 通話方案傳送。</span><span class="sxs-lookup"><span data-stu-id="e0800-308">If nothing matches the number patterns in the administrator-created online voice routes, route via Microsoft Calling Plan.</span></span>

<span data-ttu-id="e0800-309">如果使用者只有 Microsoft 手機系統，就會中斷通話，因為沒有可用的相符規則。</span><span class="sxs-lookup"><span data-stu-id="e0800-309">If the user has only Microsoft Phone System, the call is dropped because no matching rules are available.</span></span>

  > [!NOTE]
  > <span data-ttu-id="e0800-310">在這種情況下，路由 "Other + 1" 的優先順序值不重要，因為只有一個路由符合模式 + 1 XXX XXX XXX xx。</span><span class="sxs-lookup"><span data-stu-id="e0800-310">The Priority value for route "Other +1" doesn’t matter in this case, as there is only one route that matches the pattern +1 XXX XXX XX XX.</span></span> <span data-ttu-id="e0800-311">如果使用者撥打電話給 + 1 324 567 89 89，且 sbc5.contoso.biz 和 sbc6.contoso.biz 都無法使用，通話就會斷撥。</span><span class="sxs-lookup"><span data-stu-id="e0800-311">If a user makes a call to +1 324 567 89 89 and both sbc5.contoso.biz and sbc6.contoso.biz are unavailable, the call is dropped.</span></span>

<span data-ttu-id="e0800-312">下表摘要列出使用三個語音路由的配置。</span><span class="sxs-lookup"><span data-stu-id="e0800-312">The following table summarizes the configuration using three voice routes.</span></span> <span data-ttu-id="e0800-313">在這個範例中，所有三個路由都是「美國和加拿大」相同的 PSTN 使用量。</span><span class="sxs-lookup"><span data-stu-id="e0800-313">In this example, all three routes are part of the same PSTN Usage "US and Canada".</span></span>

|<span data-ttu-id="e0800-314">**PSTN 使用量**</span><span class="sxs-lookup"><span data-stu-id="e0800-314">**PSTN usage**</span></span>|<span data-ttu-id="e0800-315">**語音路線**</span><span class="sxs-lookup"><span data-stu-id="e0800-315">**Voice route**</span></span>|<span data-ttu-id="e0800-316">**數位模式**</span><span class="sxs-lookup"><span data-stu-id="e0800-316">**Number pattern**</span></span>|<span data-ttu-id="e0800-317">**優先順序**</span><span class="sxs-lookup"><span data-stu-id="e0800-317">**Priority**</span></span>|<span data-ttu-id="e0800-318">**SBC**</span><span class="sxs-lookup"><span data-stu-id="e0800-318">**SBC**</span></span>|<span data-ttu-id="e0800-319">**描述**</span><span class="sxs-lookup"><span data-stu-id="e0800-319">**Description**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="e0800-320">僅限美國</span><span class="sxs-lookup"><span data-stu-id="e0800-320">US only</span></span>|<span data-ttu-id="e0800-321">"雷德蒙 1"</span><span class="sxs-lookup"><span data-stu-id="e0800-321">"Redmond 1"</span></span>|<span data-ttu-id="e0800-322">^\\+ 1 （425\|206）（\d{7}） $</span><span class="sxs-lookup"><span data-stu-id="e0800-322">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="e0800-323">1</span><span class="sxs-lookup"><span data-stu-id="e0800-323">1</span></span>|<span data-ttu-id="e0800-324">sbc1.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="e0800-324">sbc1.contoso.biz</span></span><br/><span data-ttu-id="e0800-325">sbc2.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="e0800-325">sbc2.contoso.biz</span></span>|<span data-ttu-id="e0800-326">呼叫號碼 + 1 425 XXX XX xx 美元或 + 1 206 XXX XX xx 的活動路由</span><span class="sxs-lookup"><span data-stu-id="e0800-326">Active route for called numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="e0800-327">僅限美國</span><span class="sxs-lookup"><span data-stu-id="e0800-327">US only</span></span>|<span data-ttu-id="e0800-328">"雷德蒙 2"</span><span class="sxs-lookup"><span data-stu-id="e0800-328">"Redmond 2"</span></span>|<span data-ttu-id="e0800-329">^\\+ 1 （425\|206）（\d{7}） $</span><span class="sxs-lookup"><span data-stu-id="e0800-329">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="e0800-330">pplx-2</span><span class="sxs-lookup"><span data-stu-id="e0800-330">2</span></span>|<span data-ttu-id="e0800-331">sbc3.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="e0800-331">sbc3.contoso.biz</span></span><br/><span data-ttu-id="e0800-332">sbc4.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="e0800-332">sbc4.contoso.biz</span></span>|<span data-ttu-id="e0800-333">呼叫號碼的備份路由 + 1 425 XXX XX XX or + 1 206 XXX XX xx</span><span class="sxs-lookup"><span data-stu-id="e0800-333">Backup route for called numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="e0800-334">僅限美國</span><span class="sxs-lookup"><span data-stu-id="e0800-334">US only</span></span>|<span data-ttu-id="e0800-335">"Other + 1"</span><span class="sxs-lookup"><span data-stu-id="e0800-335">"Other +1"</span></span>|<span data-ttu-id="e0800-336">^\\+ 1 （\d{10}） $</span><span class="sxs-lookup"><span data-stu-id="e0800-336">^\\+1(\d{10})$</span></span>|<span data-ttu-id="e0800-337">3</span><span class="sxs-lookup"><span data-stu-id="e0800-337">3</span></span>|<span data-ttu-id="e0800-338">sbc5.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="e0800-338">sbc5.contoso.biz</span></span><br/><span data-ttu-id="e0800-339">sbc6.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="e0800-339">sbc6.contoso.biz</span></span>|<span data-ttu-id="e0800-340">呼叫號碼的路由 + 1 XXX XXX XXX xx （除 + 1 425 XXX XX 或 + 1 206 XXX XX xx 以外）</span><span class="sxs-lookup"><span data-stu-id="e0800-340">Route for called numbers +1 XXX XXX XX XX (except +1 425 XXX XX XX or +1 206 XXX XX XX)</span></span>|
|||||||

<span data-ttu-id="e0800-341">所有路由都與 PSTN 使用量「美國和加拿大」相關聯，且 PSTN 使用量與語音路由策略「僅限美國」相關聯。</span><span class="sxs-lookup"><span data-stu-id="e0800-341">All routes are associated with the PSTN Usage "US and Canada" and the PSTN Usage is associated with the Voice Routing Policy "US Only."</span></span> <span data-ttu-id="e0800-342">在這個範例中，語音路由策略會指派給使用者 Spencer Low （低）。</span><span class="sxs-lookup"><span data-stu-id="e0800-342">In this example, the voice routing policy is assigned to user Spencer Low.</span></span>

#### <a name="examples-of-call-routes"></a><span data-ttu-id="e0800-343">通話路線範例</span><span class="sxs-lookup"><span data-stu-id="e0800-343">Examples of call routes</span></span>

<span data-ttu-id="e0800-344">在下列範例中，我們將示範如何設定路由、PSTN 使用方式及路由原則，並將原則指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="e0800-344">In the following example, we demonstrate how to configure Routes, PSTN Usages, and Routing policies, and we assign the policy to the user.</span></span>

<span data-ttu-id="e0800-345">**步驟1：** 建立 PSTN 使用 "美國和加拿大"。</span><span class="sxs-lookup"><span data-stu-id="e0800-345">**Step 1:** Create the PSTN Usage "US and Canada".</span></span>

<span data-ttu-id="e0800-346">在商務用 Skype 遠端 PowerShell 會話中，鍵入：</span><span class="sxs-lookup"><span data-stu-id="e0800-346">In a Skype for Business Remote PowerShell session, type:</span></span>

```PowerShell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="US and Canada"}
```

<span data-ttu-id="e0800-347">輸入以下內容以驗證是否已建立使用：</span><span class="sxs-lookup"><span data-stu-id="e0800-347">Validate that the usage was created by entering:</span></span> 
```PowerShell
Get-CSOnlinePSTNUsage
``` 
<span data-ttu-id="e0800-348">這會傳回可能會被截斷的名稱清單：</span><span class="sxs-lookup"><span data-stu-id="e0800-348">Which returns a list of names that may be truncated:</span></span>
```console
Identity    : Global
Usage       : {testusage, US and Canada, International, karlUsage. . .}
```
<span data-ttu-id="e0800-349">在下列範例中，您可以查看執行 PowerShell 命令`(Get-CSOnlinePSTNUsage).usage`以顯示完整名稱（不會被截斷）的結果。</span><span class="sxs-lookup"><span data-stu-id="e0800-349">In the example below, you can see the result of the running the PowerShell command `(Get-CSOnlinePSTNUsage).usage` to display full names (not truncated).</span></span>

<pre>
 testusage
 US and Canada
 International
 karlUsage
 New test env
 Tallinn Lab Sonus
 karlUsage2
 Unrestricted
 Two trunks
</pre>

<span data-ttu-id="e0800-350">**步驟2：** 在商務用 Skype Online 的 PowerShell 會話中，建立三個路線：雷德蒙1、雷德蒙2和其他 + 1，如上表所述。</span><span class="sxs-lookup"><span data-stu-id="e0800-350">**Step 2:** In a PowerShell session in Skype for Business Online, create three routes: Redmond 1, Redmond 2, and Other +1, as detailed in the previous table.</span></span> 

<span data-ttu-id="e0800-351">若要建立「雷蒙德1」路線，請輸入：</span><span class="sxs-lookup"><span data-stu-id="e0800-351">To create the "Redmond 1" route, enter:</span></span>

```PowerShell
New-CsOnlineVoiceRoute -Identity "Redmond 1" -NumberPattern "^\+1(425|206)
(\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="e0800-352">返回：</span><span class="sxs-lookup"><span data-stu-id="e0800-352">Which returns:</span></span>
<pre>
Identity                : Redmond 1
Priority                : 1
Description             :
NumberPattern           : ^\+1(425|206) (\d{7})$
OnlinePstnUsages        : {US and Canada}
OnlinePstnGatewayList   : {sbc1.contoso.biz, sbc2.contoso.biz}
Name                    : Redmond 1
</pre>
<span data-ttu-id="e0800-353">若要建立雷德蒙2路線，請輸入：</span><span class="sxs-lookup"><span data-stu-id="e0800-353">To create the Redmond 2 route, enter:</span></span>

```PowerShell
New-CsOnlineVoiceRoute -Identity "Redmond 2" -NumberPattern "^\+1(425|206)
(\d{7})$" -OnlinePstnGatewayList sbc3.contoso.biz, sbc4.contoso.biz -Priority 2 -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="e0800-354">若要建立其他 + 1 路線，請輸入：</span><span class="sxs-lookup"><span data-stu-id="e0800-354">To create the Other +1 route, enter:</span></span>

```PowerShell
New-CsOnlineVoiceRoute -Identity "Other +1" -NumberPattern "^\+1(\d{10})$"
-OnlinePstnGatewayList sbc5.contoso.biz, sbc6.contoso.biz -OnlinePstnUsages "US and Canada"
```

  > [!CAUTION]
  > <span data-ttu-id="e0800-355">請確定 NumberPattern 屬性中的正則運算式是有效的運算式。</span><span class="sxs-lookup"><span data-stu-id="e0800-355">Make sure that your regular expression in the NumberPattern attribute is a valid expression.</span></span> <span data-ttu-id="e0800-356">您可以使用此網站進行測試：[https://www.regexpal.com](https://www.regexpal.com)</span><span class="sxs-lookup"><span data-stu-id="e0800-356">You can test it using this website: [https://www.regexpal.com](https://www.regexpal.com)</span></span>

<span data-ttu-id="e0800-357">在某些情況下，需要將所有呼叫路由至同一個 SBC;請使用-NumberPattern ". \*"</span><span class="sxs-lookup"><span data-stu-id="e0800-357">In some cases there is a need to route all calls to the same SBC; please use -NumberPattern ".\*"</span></span>

<span data-ttu-id="e0800-358">將所有呼叫路由至同一個 SBC。</span><span class="sxs-lookup"><span data-stu-id="e0800-358">Route all calls to same SBC.</span></span>

```PowerShell
Set-CsOnlineVoiceRoute -id "Redmond 1" -NumberPattern ".*" -OnlinePstnGatewayList sbc1.contoso.biz
```

<span data-ttu-id="e0800-359">使用如下所示的選項，驗證您是否已`Get-CSOnlineVoiceRoute`透過執行 PowerShell 命令來正確設定路線：</span><span class="sxs-lookup"><span data-stu-id="e0800-359">Validate that you’ve correctly configured the route by running the `Get-CSOnlineVoiceRoute` PowerShell command using options as shown:</span></span>

```PowerShell
Get-CsOnlineVoiceRoute | Where-Object {($_.priority -eq 1) -or ($_.priority -eq 2) or ($_.priority -eq 4) -Identity "Redmond 1" -NumberPattern "^\+1(425|206) (\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```
<span data-ttu-id="e0800-360">應傳回的專案：</span><span class="sxs-lookup"><span data-stu-id="e0800-360">Which should return:</span></span>
<pre>
Identity            : Redmond 1 
Priority            : 1
Description     : 
NumberPattern       : ^\+1(425|206) (\d{7})$
OnlinePstnUsages    : {US and Canada}    
OnlinePstnGatewayList   : {sbc1.contoso.biz, sbc2.contoso.biz}
Name            : Redmond 1
Identity        : Redmond 2 
Priority            : 2
Description     : 
NumberPattern       : ^\+1(425|206) (\d{7})$
OnlinePstnUsages    : {US and Canada}    
OnlinePstnGatewayList   : {sbc3.contoso.biz, sbc4.contoso.biz}
Name            : Redmond 2
    
Identity        : Other +1 
Priority            : 4
Description     : 
NumberPattern       : ^\+1(\d{10})$
OnlinePstnUsages    : {US and Canada}    
OnlinePstnGatewayList   : {sbc5.contoso.biz, sbc6.contoso.biz}
Name            : Other +1
</pre>

<span data-ttu-id="e0800-361">在這個範例中，「其他 + 1」路由會自動指派優先順序4。</span><span class="sxs-lookup"><span data-stu-id="e0800-361">In the example, the route "Other +1" was automatically assigned priority 4.</span></span> 

<span data-ttu-id="e0800-362">**步驟3：** 建立「僅限我們」的語音路由策略，並將 PSTN 使用量「美國和加拿大」加入原則。</span><span class="sxs-lookup"><span data-stu-id="e0800-362">**Step 3:** Create a Voice Routing Policy "US Only" and add to the policy the PSTN Usage "US and Canada."</span></span>

<span data-ttu-id="e0800-363">在商務用 Skype Online 的 PowerShell 會話中，鍵入：</span><span class="sxs-lookup"><span data-stu-id="e0800-363">In a PowerShell session in Skype for Business Online, type:</span></span>

```PowerShell
New-CsOnlineVoiceRoutingPolicy "US Only" -OnlinePstnUsages "US and Canada"
```

<span data-ttu-id="e0800-364">結果會顯示在這個範例中：</span><span class="sxs-lookup"><span data-stu-id="e0800-364">The result is shown in this example:</span></span>

<pre>
Identity            : Tag:US only
OnlinePstnUsages    : {US and Canada}
Description         :
RouteType           : BYOT
</pre>

<span data-ttu-id="e0800-365">**步驟4：** 使用 PowerShell 授與使用者 Spencer 低的語音路由原則。</span><span class="sxs-lookup"><span data-stu-id="e0800-365">**Step 4:** Grant to user Spencer Low a voice routing policy by using PowerShell.</span></span>

<span data-ttu-id="e0800-366">在商務用 Skype Online 的 PowerShell 會話中，鍵入：</span><span class="sxs-lookup"><span data-stu-id="e0800-366">In a PowerShell session in Skype for Business Online, type:</span></span>

```PowerShell
Grant-CsOnlineVoiceRoutingPolicy -Identity "Spencer Low" -PolicyName "US Only"
```

<span data-ttu-id="e0800-367">輸入以下命令以驗證原則指派：</span><span class="sxs-lookup"><span data-stu-id="e0800-367">Validate the policy assignment by entering this command:</span></span>

```PowerShell
Get-CsOnlineUser "Spencer Low" | select OnlineVoiceRoutingPolicy
```

<span data-ttu-id="e0800-368">返回：</span><span class="sxs-lookup"><span data-stu-id="e0800-368">Which returns:</span></span>
<pre>
OnlineVoiceRoutingPolicy
---------------------
US Only
</pre>

#### <a name="creating-a-voice-routing-policy-with-several-pstn-usages"></a><span data-ttu-id="e0800-369">建立具有幾個 PSTN 用途的語音路由策略</span><span class="sxs-lookup"><span data-stu-id="e0800-369">Creating a Voice Routing Policy with several PSTN Usages</span></span>

<span data-ttu-id="e0800-370">先前建立的語音路由策略只允許撥打美國和加拿大電話號碼，除非使用者也指派 Microsoft 通話方案授權。</span><span class="sxs-lookup"><span data-stu-id="e0800-370">The Voice Routing Policy created previously only allows calls to phone numbers in the US and Canada--unless the Microsoft Calling Plan license is also assigned to the user.</span></span>

<span data-ttu-id="e0800-371">在下列範例中，您可以建立語音路由策略「無限制」。</span><span class="sxs-lookup"><span data-stu-id="e0800-371">In the example that follows, you can create the Voice Routing Policy "No Restrictions."</span></span> <span data-ttu-id="e0800-372">原則會重複使用在上述範例中建立的 PSTN 使用量 "美國和加拿大"，以及新的 PSTN 使用量 "國際"。</span><span class="sxs-lookup"><span data-stu-id="e0800-372">The policy reuses the PSTN Usage "US and Canada" created in the previous example, as well as the new PSTN Usage "International."</span></span> 

<span data-ttu-id="e0800-373">這會將所有其他呼叫路由到 SBCs sbc2.contoso.biz 和 sbc5.contoso.biz。</span><span class="sxs-lookup"><span data-stu-id="e0800-373">This routes all other calls to the SBCs sbc2.contoso.biz and sbc5.contoso.biz.</span></span> <span data-ttu-id="e0800-374">所顯示的範例會將 [僅限美國] 原則指派給使用者 "Spencer Low"，而不限制使用者「John 的使用方式」。</span><span class="sxs-lookup"><span data-stu-id="e0800-374">The examples that are shown assign the US Only policy to user "Spencer Low," and No Restrictions to the user "John Woods."</span></span>

<span data-ttu-id="e0800-375">Spencer [低] –只允許通話至美國和加拿大號碼。</span><span class="sxs-lookup"><span data-stu-id="e0800-375">Spencer Low – Calls allowed only to US and Canadian numbers.</span></span> <span data-ttu-id="e0800-376">呼叫雷德蒙的數位範圍時，必須使用一組特定的 SBC。</span><span class="sxs-lookup"><span data-stu-id="e0800-376">When calling to the Redmond number range, the specific set of SBC must be used.</span></span> <span data-ttu-id="e0800-377">除非指派給使用者的是通話方案授權，否則不會路由非美國數位。</span><span class="sxs-lookup"><span data-stu-id="e0800-377">Non-US numbers will not be routed unless the Calling Plan license is assigned to the user.</span></span>

<span data-ttu-id="e0800-378">John：可撥打任何號碼的電話。</span><span class="sxs-lookup"><span data-stu-id="e0800-378">John Woods – Calls allowed to any number.</span></span> <span data-ttu-id="e0800-379">呼叫雷德蒙的數位範圍時，必須使用一組特定的 SBC。</span><span class="sxs-lookup"><span data-stu-id="e0800-379">When calling to the Redmond number range, the specific set of SBC must be used.</span></span> <span data-ttu-id="e0800-380">非美國數位會透過 sbc2.contoso.biz 和 sbc5.contoso.biz 路由。</span><span class="sxs-lookup"><span data-stu-id="e0800-380">Non-US numbers will be routed via sbc2.contoso.biz and sbc5.contoso.biz.</span></span>

![顯示指派給使用者 Spencer 低的語音路由策略](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoSpencerLow.png)

<span data-ttu-id="e0800-382">針對所有其他通話，如果使用者同時擁有兩個授權（Microsoft 手機系統和 Microsoft 通話方案），則會使用自動路由。</span><span class="sxs-lookup"><span data-stu-id="e0800-382">For all other calls, if a user has both licenses (Microsoft Phone System and Microsoft Calling Plan), Automatic Route is used.</span></span> <span data-ttu-id="e0800-383">如果沒有與管理員建立的線上語音路線中的數位模式相符，請透過 Microsoft 通話方案傳送。</span><span class="sxs-lookup"><span data-stu-id="e0800-383">If nothing matches the number patterns in the administrator-created online voice routes, route via Microsoft Calling Plan.</span></span>

<span data-ttu-id="e0800-384">如果使用者只有 Microsoft 手機系統，就會中斷通話，因為沒有可用的相符規則。</span><span class="sxs-lookup"><span data-stu-id="e0800-384">If the user has only Microsoft Phone System, the call is dropped because no matching rules are available.</span></span>

![顯示指派給使用者 John 的語音路由策略](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoJohnWoods.png)

<span data-ttu-id="e0800-386">下表摘要列出路由策略「無限制」的使用方式指派和語音路由。</span><span class="sxs-lookup"><span data-stu-id="e0800-386">The following table summarizes routing policy "No Restrictions" usage designations and voice routes.</span></span> 

|<span data-ttu-id="e0800-387">**PSTN 使用量**</span><span class="sxs-lookup"><span data-stu-id="e0800-387">**PSTN usage**</span></span>|<span data-ttu-id="e0800-388">**語音路線**</span><span class="sxs-lookup"><span data-stu-id="e0800-388">**Voice route**</span></span>|<span data-ttu-id="e0800-389">**數位模式**</span><span class="sxs-lookup"><span data-stu-id="e0800-389">**Number pattern**</span></span>|<span data-ttu-id="e0800-390">**優先順序**</span><span class="sxs-lookup"><span data-stu-id="e0800-390">**Priority**</span></span>|<span data-ttu-id="e0800-391">**SBC**</span><span class="sxs-lookup"><span data-stu-id="e0800-391">**SBC**</span></span>|<span data-ttu-id="e0800-392">**描述**</span><span class="sxs-lookup"><span data-stu-id="e0800-392">**Description**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="e0800-393">僅限美國</span><span class="sxs-lookup"><span data-stu-id="e0800-393">US Only</span></span>|<span data-ttu-id="e0800-394">"雷德蒙 1"</span><span class="sxs-lookup"><span data-stu-id="e0800-394">"Redmond 1"</span></span>|<span data-ttu-id="e0800-395">^\\+ 1 （425\|206）（\d{7}） $</span><span class="sxs-lookup"><span data-stu-id="e0800-395">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="e0800-396">1</span><span class="sxs-lookup"><span data-stu-id="e0800-396">1</span></span>|<span data-ttu-id="e0800-397">sbc1.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="e0800-397">sbc1.contoso.biz</span></span><br/><span data-ttu-id="e0800-398">sbc2.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="e0800-398">sbc2.contoso.biz</span></span>|<span data-ttu-id="e0800-399">被呼叫者編號的作用中路由 + 1 425 XXX XX XX 或 + 1 206 XXX XX xx</span><span class="sxs-lookup"><span data-stu-id="e0800-399">Active route for callee numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="e0800-400">僅限美國</span><span class="sxs-lookup"><span data-stu-id="e0800-400">US Only</span></span>|<span data-ttu-id="e0800-401">"雷德蒙 2"</span><span class="sxs-lookup"><span data-stu-id="e0800-401">"Redmond 2"</span></span>|<span data-ttu-id="e0800-402">^\\+ 1 （425\|206）（\d{7}） $</span><span class="sxs-lookup"><span data-stu-id="e0800-402">^\\+1(425\|206)(\d{7})$</span></span>|<span data-ttu-id="e0800-403">pplx-2</span><span class="sxs-lookup"><span data-stu-id="e0800-403">2</span></span>|<span data-ttu-id="e0800-404">sbc3.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="e0800-404">sbc3.contoso.biz</span></span><br/><span data-ttu-id="e0800-405">sbc4.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="e0800-405">sbc4.contoso.biz</span></span>|<span data-ttu-id="e0800-406">被呼叫者編號的備份路由 + 1 425 XXX XX XX 或 + 1 206 XXX XX xx</span><span class="sxs-lookup"><span data-stu-id="e0800-406">Backup route for callee numbers +1 425 XXX XX XX or +1 206 XXX XX XX</span></span>|
|<span data-ttu-id="e0800-407">僅限美國</span><span class="sxs-lookup"><span data-stu-id="e0800-407">US Only</span></span>|<span data-ttu-id="e0800-408">"Other + 1"</span><span class="sxs-lookup"><span data-stu-id="e0800-408">"Other +1"</span></span>|<span data-ttu-id="e0800-409">^\\+ 1 （\d{10}） $</span><span class="sxs-lookup"><span data-stu-id="e0800-409">^\\+1(\d{10})$</span></span>|<span data-ttu-id="e0800-410">3</span><span class="sxs-lookup"><span data-stu-id="e0800-410">3</span></span>|<span data-ttu-id="e0800-411">sbc5.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="e0800-411">sbc5.contoso.biz</span></span><br/><span data-ttu-id="e0800-412">sbc6>. contoso.biz</span><span class="sxs-lookup"><span data-stu-id="e0800-412">sbc6>.contoso.biz</span></span>|<span data-ttu-id="e0800-413">被呼叫者的電話號碼 + 1 XXX XXX XX （不包括 + 1 425 XXX XX 或 + 1 206 XXX xx xx）</span><span class="sxs-lookup"><span data-stu-id="e0800-413">Route for callee numbers +1 XXX XXX XX XX (except +1 425 XXX XX XX or +1 206 XXX XX XX)</span></span>|
|<span data-ttu-id="e0800-414">國際</span><span class="sxs-lookup"><span data-stu-id="e0800-414">International</span></span>|<span data-ttu-id="e0800-415">國際</span><span class="sxs-lookup"><span data-stu-id="e0800-415">International</span></span>|<span data-ttu-id="e0800-416">\d +</span><span class="sxs-lookup"><span data-stu-id="e0800-416">\d+</span></span>|<span data-ttu-id="e0800-417">4</span><span class="sxs-lookup"><span data-stu-id="e0800-417">4</span></span>|<span data-ttu-id="e0800-418">sbc2.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="e0800-418">sbc2.contoso.biz</span></span><br/><span data-ttu-id="e0800-419">sbc5.contoso.biz</span><span class="sxs-lookup"><span data-stu-id="e0800-419">sbc5.contoso.biz</span></span>|<span data-ttu-id="e0800-420">任何數位模式的路線</span><span class="sxs-lookup"><span data-stu-id="e0800-420">Route for any number pattern</span></span> |


  > [!NOTE]
  > - <span data-ttu-id="e0800-421">語音路由策略中的 PSTN 使用順序非常重要。</span><span class="sxs-lookup"><span data-stu-id="e0800-421">The order of PSTN Usages in Voice Routing Policies is critical.</span></span> <span data-ttu-id="e0800-422">此用法會依順序套用，如果在第一個用法中找到一個相符專案，則永遠不會評估其他用法。</span><span class="sxs-lookup"><span data-stu-id="e0800-422">The usages are applied in order, and if a match is found in the first usage, then other usages are never evaluated.</span></span> <span data-ttu-id="e0800-423">Pstn 使用量 "國際" 必須放在 PSTN 使用 [僅限美國] 後。</span><span class="sxs-lookup"><span data-stu-id="e0800-423">The PSTN Usage "International" must be placed after the PSTN Usage "US Only."</span></span> <span data-ttu-id="e0800-424">若要變更 PSTN 用法的順序，請執行`Set-CSOnlineVoiceRoutingPolicy`命令。</span><span class="sxs-lookup"><span data-stu-id="e0800-424">To change the order of the PSTN Usages, run the `Set-CSOnlineVoiceRoutingPolicy` command.</span></span> <br/><span data-ttu-id="e0800-425">例如，若要將訂單從 "美國和加拿大" 先變更為 [國際 "，然後再執行相反順序：</span><span class="sxs-lookup"><span data-stu-id="e0800-425">For example, to change the order from "US and Canada" first and "International" second to the reverse order run:</span></span><br/> `Set-CsOnlineVoiceRoutingPolicy -id tag:"no Restrictions" -OnlinePstnUsages @{Replace="International", "US and Canada"}`
 > - <span data-ttu-id="e0800-426">系統會自動指派「其他 + 1」和「國際」語音路由的優先順序。</span><span class="sxs-lookup"><span data-stu-id="e0800-426">The priority for "Other +1" and "International" Voice routes are assigned automatically.</span></span> <span data-ttu-id="e0800-427">只要其優先順序低於「雷蒙德1」和「雷蒙德2」，就不重要。</span><span class="sxs-lookup"><span data-stu-id="e0800-427">They don’t matter as long as they have lower priorities than "Redmond 1" and "Redmond 2."</span></span>

#### <a name="example-of-voice-routing-policy-for-user-john-woods"></a><span data-ttu-id="e0800-428">使用者 John 的語音路由策略範例</span><span class="sxs-lookup"><span data-stu-id="e0800-428">Example of Voice Routing Policy for user John Woods</span></span>

<span data-ttu-id="e0800-429">建立 PSTN 使用量 "國際"，語音路由 "國際，" 語音路由策略 "無限制，然後再將它指派給使用者「John 54777」的步驟如下所示。</span><span class="sxs-lookup"><span data-stu-id="e0800-429">The steps to create PSTN Usage "International", voice route "International," Voice Routing Policy "No Restrictions," and then assigning it to the user "John Woods" are as follows.</span></span>   


<span data-ttu-id="e0800-430">**步驟 1**：建立 PSTN 使用 "國際"。</span><span class="sxs-lookup"><span data-stu-id="e0800-430">**Step 1**: Create the PSTN Usage "International."</span></span> 

<span data-ttu-id="e0800-431">在商務用 Skype Online 的遠端 PowerShell 會話中，輸入：</span><span class="sxs-lookup"><span data-stu-id="e0800-431">In a remote PowerShell session in Skype for Business Online, enter:</span></span>

```PowerShell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="International"}
```

<span data-ttu-id="e0800-432">**步驟 2**：建立新的語音路由「國際」。</span><span class="sxs-lookup"><span data-stu-id="e0800-432">**Step 2**:  Create the new voice route "International."</span></span>

```PowerShell
New-CsOnlineVoiceRoute -Identity "International" -NumberPattern ".*" -OnlinePstnGatewayList sbc2.contoso.biz, sbc5.contoso.biz -OnlinePstnUsages "International"
```
<span data-ttu-id="e0800-433">返回：</span><span class="sxs-lookup"><span data-stu-id="e0800-433">Which returns:</span></span>

<pre>
Identity                  : International
Priority                  : 5
Description               :
NumberPattern             : .*
OnlinePstnUsages          : {International}
OnlinePstnGatewayList     : {sbc2.contoso.biz, sbc5.contoso.biz}
Name                      : International
</pre>

<span data-ttu-id="e0800-434">**步驟 3**：建立語音路由策略「無限制」。</span><span class="sxs-lookup"><span data-stu-id="e0800-434">**Step 3**: Create a Voice Routing Policy "No Restrictions".</span></span> 

<span data-ttu-id="e0800-435">在此語音路由原則中，PSTN 使用 "雷德蒙 1" 和 "雷德蒙" 會重複使用，以保留對號碼 "+ 1 425 XXX XX" 和 "+ 1 206 XXX XX" （作為本機或內部部署的呼叫）的特殊處理。</span><span class="sxs-lookup"><span data-stu-id="e0800-435">The PSTN Usage "Redmond 1" and "Redmond" are reused in this voice routing policy to preserve special handling for calls to number "+1 425 XXX XX XX" and "+1 206 XXX XX XX" as local or on-premises calls.</span></span>

  ```PowerShell
  New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", "International"
  ```

<span data-ttu-id="e0800-436">請注意 PSTN 的使用順序：</span><span class="sxs-lookup"><span data-stu-id="e0800-436">Take note of the order of PSTN Usages:</span></span>

  <span data-ttu-id="e0800-437">是.</span><span class="sxs-lookup"><span data-stu-id="e0800-437">a.</span></span> <span data-ttu-id="e0800-438">如果撥打的號碼是 "+ 1 425 XXX XX"，且使用下列範例所述的使用方式，則呼叫會遵循「美國和加拿大」用法中的路由設定，並套用特殊路由邏輯。</span><span class="sxs-lookup"><span data-stu-id="e0800-438">If a call made to number "+1 425 XXX XX XX" with the usages configured as in the following example, the call follows the route set in "US and Canada" usage and the special routing logic is applied.</span></span> <span data-ttu-id="e0800-439">也就是說，通話是使用 sbc1.contoso.biz 和 sbc2.contoso.biz 進行路由，然後 sbc3.contoso.biz 和 sbc4.contoso.biz 做為備份路由。</span><span class="sxs-lookup"><span data-stu-id="e0800-439">That is, the call is routed using sbc1.contoso.biz and sbc2.contoso.biz first, and then sbc3.contoso.biz and sbc4.contoso.biz as the backup routes.</span></span>

  <span data-ttu-id="e0800-440">乙.</span><span class="sxs-lookup"><span data-stu-id="e0800-440">b.</span></span> <span data-ttu-id="e0800-441">如果「國際」 PSTN 使用量在「美國和加拿大」之前，則對 + 1 425 XXX XX 的呼叫會路由至 sbc2.contoso.biz 和 sbc5.contoso.biz，成為路由邏輯的一部分。</span><span class="sxs-lookup"><span data-stu-id="e0800-441">If "International" PSTN usage is before "US and Canada," calls to +1 425 XXX XX XX are routed to sbc2.contoso.biz and sbc5.contoso.biz as part of the routing logic.</span></span> <span data-ttu-id="e0800-442">輸入命令：</span><span class="sxs-lookup"><span data-stu-id="e0800-442">Enter the command:</span></span>

  ```PowerShell
  New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", "International"
  ```

<span data-ttu-id="e0800-443">返回：</span><span class="sxs-lookup"><span data-stu-id="e0800-443">Which returns:</span></span>

    <pre>
    Identity              : International 
    OnlinePstnUsages : {US and Canada, International}    
    Description      :  
    RouteType             : BYOT
    </pre>

<span data-ttu-id="e0800-444">**步驟 4**：使用下列命令，將語音路由策略指派給使用者「John xxxxx」。</span><span class="sxs-lookup"><span data-stu-id="e0800-444">**Step 4**: Assign the voice routing policy to the user "John Woods" using the following command.</span></span>

```PowerShell
Grant-CsOnlineVoiceRoutingPolicy -Identity "John Woods" -PolicyName "No Restrictions”
```

<span data-ttu-id="e0800-445">然後使用命令驗證作業：</span><span class="sxs-lookup"><span data-stu-id="e0800-445">Then verify the assignment using the command:</span></span> 

```PowerShell
Get-CsOnlineUser "John Woods" | Select OnlineVoiceRoutingPolicy
```

<span data-ttu-id="e0800-446">返回：</span><span class="sxs-lookup"><span data-stu-id="e0800-446">Which returns:</span></span>

<pre>
OnlineVoiceRoutingPolicy
------------------------
No Restrictions
</pre>

<span data-ttu-id="e0800-447">結果是，套用到 John 54777 通話的語音原則是不受限制的，將遵循可供美國、加拿大和國際電話使用的呼叫路由的邏輯。</span><span class="sxs-lookup"><span data-stu-id="e0800-447">The result is that the voice policy applied to John Woods’ calls is unrestricted, and will follow the logic of call routing available for US, Canada, and International calling.</span></span>

## <a name="assign-teams-only-mode-to-users-to-ensure-calls-land-in-microsoft-teams"></a><span data-ttu-id="e0800-448">將 [僅限團隊] 模式指派給使用者，以確保在 Microsoft 團隊中撥打土地</span><span class="sxs-lookup"><span data-stu-id="e0800-448">Assign Teams Only mode to users to ensure calls land in Microsoft Teams</span></span>

<span data-ttu-id="e0800-449">直接路由要求使用者只能在 [僅限團隊] 模式中，以確保來電在團隊用戶端中保持通話。</span><span class="sxs-lookup"><span data-stu-id="e0800-449">Direct Routing requires that users be in Teams Only mode to ensure incoming calls land in the Teams client.</span></span> <span data-ttu-id="e0800-450">若要將使用者置於 [僅限團隊] 模式，請將 [UpgradeToTeams] TeamsUpgradePolicy 的實例指派給他們。</span><span class="sxs-lookup"><span data-stu-id="e0800-450">To put users in Teams Only mode, assign them the "UpgradeToTeams" instance of TeamsUpgradePolicy.</span></span> <span data-ttu-id="e0800-451">如果您的組織使用商務用 Skype Server 或商務用 Skype Online，請參閱下列文章，以瞭解 Skype 與團隊之間的資訊互用性：[與商務用 Skype 搭配使用團隊之組織的遷移與互通性指導](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype)方針。</span><span class="sxs-lookup"><span data-stu-id="e0800-451">If your organization uses Skype for Business Server or Skype for Business Online, see the following article for information interoperability between Skype and Teams: [Migration and interoperability guidance for organizations using Teams together with Skype for Business](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype).</span></span> 

## <a name="configuring-sending-calls-directly-to-voicemail"></a><span data-ttu-id="e0800-452">設定直接傳送來電至語音信箱</span><span class="sxs-lookup"><span data-stu-id="e0800-452">Configuring sending calls directly to voicemail</span></span>

<span data-ttu-id="e0800-453">[直接路由] 可讓您結束通話呼叫並直接傳送給使用者的語音信箱。</span><span class="sxs-lookup"><span data-stu-id="e0800-453">Direct Routing allows you to end the call to a user and send it directly to the users' voicemail.</span></span> <span data-ttu-id="e0800-454">如果您想要直接將來電傳送到語音信箱，請將不透明的 = app 附加至 [要求 URI 標頭]。</span><span class="sxs-lookup"><span data-stu-id="e0800-454">If you want to send the call directly to voicemail, please attach opaque=app:voicemail to the Request URI header.</span></span> <span data-ttu-id="e0800-455">例如，「sip： user@yourdomain .com; 不透明 = app：語音信箱」。</span><span class="sxs-lookup"><span data-stu-id="e0800-455">For example, "sip:user@yourdomain.com;opaque=app:voicemail".</span></span>
<span data-ttu-id="e0800-456">在這種情況下，小組使用者將不會收到來電通知，該通話會直接連線至使用者的語音信箱。</span><span class="sxs-lookup"><span data-stu-id="e0800-456">In this case the Teams user will not receive the calling notification, the call will be connected to the voicemail of the user directly.</span></span>

## <a name="translate-caller-and-callee-numbers-for-outbound-and-inbound-calls-to-an-alternate-format"></a><span data-ttu-id="e0800-457">將撥出和撥出電話的呼叫者和來電數轉換為替代格式</span><span class="sxs-lookup"><span data-stu-id="e0800-457">Translate caller and callee numbers for outbound and inbound calls to an alternate format</span></span>

<span data-ttu-id="e0800-458">有時候，租使用者管理員可能會根據其建立的模式變更本機號碼和/或撥入式通話，以確保互通性的方程式。</span><span class="sxs-lookup"><span data-stu-id="e0800-458">Sometimes tenant administrators may want to change the callee or caller number for outbound and/or inbound calls based on the patterns they created to ensure interoperability with SBCs.</span></span> <span data-ttu-id="e0800-459">您可以設定一個數位翻譯規則原則，以將被呼叫者或來電者編號轉換成替代格式。</span><span class="sxs-lookup"><span data-stu-id="e0800-459">You can set a Number Translation Rules policy to translate callee or caller numbers to an alternate format.</span></span> <span data-ttu-id="e0800-460">您可以使用原則來轉譯下列各項的數位：</span><span class="sxs-lookup"><span data-stu-id="e0800-460">You can use the policy to translate numbers for the following:</span></span>

- <span data-ttu-id="e0800-461">入站通話：從 PSTN 端點（來電者）到團隊用戶端（被呼叫者）的呼叫。</span><span class="sxs-lookup"><span data-stu-id="e0800-461">Inbound calls: Calls from a PSTN endpoint (caller) to a Teams client (callee).</span></span>
- <span data-ttu-id="e0800-462">[呼出通話]：從團隊用戶端（來電者）到 PSTN 端點（被叫方）的呼叫。</span><span class="sxs-lookup"><span data-stu-id="e0800-462">Outbound calls: Calls from a Teams client (caller) to a PSTN endpoint (callee).</span></span>

<span data-ttu-id="e0800-463">原則會套用到 SBC 層級。</span><span class="sxs-lookup"><span data-stu-id="e0800-463">The policy is applied at the SBC level.</span></span> <span data-ttu-id="e0800-464">您可以將多個翻譯規則指派給 SBC，這些規則會依您在 PowerShell 中列出它們時的出現順序來套用。</span><span class="sxs-lookup"><span data-stu-id="e0800-464">You can assign multiple translation rules to a SBC, which are applied in the order that they appear when you list them in PowerShell.</span></span> <span data-ttu-id="e0800-465">您也可以在原則中變更規則的順序。</span><span class="sxs-lookup"><span data-stu-id="e0800-465">You can also change the order of the rules in the policy.</span></span>

<span data-ttu-id="e0800-466">若要建立、修改、查看及刪除數位處理規則，請使用[新的 CsTeamsTranslationRule](https://docs.microsoft.com/powershell/module/skype/new-csteamstranslationrule)、 [CsTeamsTranslationRule](https://docs.microsoft.com/powershell/module/skype/set-csteamstranslationrule)、 [CsTeamsTranslationRule](https://docs.microsoft.com/powershell/module/skype/get-csteamstranslationrule)及[Remove-CsTeamsTranslationRule](https://docs.microsoft.com/powershell/module/skype/remove-csteamstranslationrule) Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="e0800-466">To create, modify, view, and delete number manipulation rules, use the [New-CsTeamsTranslationRule](https://docs.microsoft.com/powershell/module/skype/new-csteamstranslationrule), [Set-CsTeamsTranslationRule](https://docs.microsoft.com/powershell/module/skype/set-csteamstranslationrule), [Get-CsTeamsTranslationRule](https://docs.microsoft.com/powershell/module/skype/get-csteamstranslationrule), and [Remove-CsTeamsTranslationRule](https://docs.microsoft.com/powershell/module/skype/remove-csteamstranslationrule) cmdlets.</span></span>

<span data-ttu-id="e0800-467">若要在 SBCs 上指派、設定及列出編號操作規則，請[使用新的 CSOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway)和[CSOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstngateway) Cmdlet 以及```InboundTeamsNumberTranslationRules```、 ```InboundPSTNNumberTranslationRules``` ```OutboundTeamsNumberTranslationRules``` ```OutboundPSTNNumberTranslationRules``` ```InboundTeamsNumberTranslationRulesList``` ```InboundPSTNNumberTranslationRulesList``` ```OutboundTeamsNumberTranslationRulesList```、、、、、、、、、、 ```OutboundPSTNNumberTranslationRulesList``` 、、、、、、、、、、和參數。</span><span class="sxs-lookup"><span data-stu-id="e0800-467">To assign, configure, and list number manipulation rules on SBCs, use the [New-CSOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway) and [Set-CSOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstngateway) cmdlets together with the  ```InboundTeamsNumberTranslationRules```, ```InboundPSTNNumberTranslationRules```, ```OutboundTeamsNumberTranslationRules```, ```OutboundPSTNNumberTranslationRules```, ```InboundTeamsNumberTranslationRulesList```, ```InboundPSTNNumberTranslationRulesList```, ```OutboundTeamsNumberTranslationRulesList```, and ```OutboundPSTNNumberTranslationRulesList``` parameters.</span></span>

### <a name="examples"></a><span data-ttu-id="e0800-468">範例</span><span class="sxs-lookup"><span data-stu-id="e0800-468">Examples</span></span>

#### <a name="example-sbc-configuration"></a><span data-ttu-id="e0800-469">SBC 範例配置</span><span class="sxs-lookup"><span data-stu-id="e0800-469">Example SBC configuration</span></span>

<span data-ttu-id="e0800-470">在範例案例中，我們會執行```New-CsOnlinePSTNGateway``` Cmdlet 來建立下列的 SBC 配置。</span><span class="sxs-lookup"><span data-stu-id="e0800-470">For the example scenarios, we run the ```New-CsOnlinePSTNGateway``` cmdlet to create the following SBC configuration.</span></span>

```PowerShell
New-CSOnlinePSTNGateway -Identity sbc1.contoso.com -SipSignalingPort 5061 –InboundTeamsNumberTranslationRulesList ‘AddPlus1’, ‘AddE164SeattleAreaCode’ -InboundPSTNNumberTranslationRulesList ‘AddPlus1’ -OnboundPSTNNumberTranslationRulesList ‘AddSeattleAreaCode’,  -OutboundTeamsNumberTranslationRulesList ‘StripPlus1’
```

<span data-ttu-id="e0800-471">指派給 SBC 的翻譯規則摘要如下表所示。</span><span class="sxs-lookup"><span data-stu-id="e0800-471">The translation rules assigned to the SBC are summarized in the following table.</span></span>

|<span data-ttu-id="e0800-472">名稱</span><span class="sxs-lookup"><span data-stu-id="e0800-472">Name</span></span>  |<span data-ttu-id="e0800-473">模式</span><span class="sxs-lookup"><span data-stu-id="e0800-473">Pattern</span></span> |<span data-ttu-id="e0800-474">翻譯</span><span class="sxs-lookup"><span data-stu-id="e0800-474">Translation</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="e0800-475">AddPlus1</span><span class="sxs-lookup"><span data-stu-id="e0800-475">AddPlus1</span></span>     |<span data-ttu-id="e0800-476">^ （\d{10}） $</span><span class="sxs-lookup"><span data-stu-id="e0800-476">^(\d{10})$</span></span>          |<span data-ttu-id="e0800-477">+ 1 $ 1</span><span class="sxs-lookup"><span data-stu-id="e0800-477">+1$1</span></span>          |
|<span data-ttu-id="e0800-478">AddE164SeattleAreaCode</span><span class="sxs-lookup"><span data-stu-id="e0800-478">AddE164SeattleAreaCode</span></span>      |<span data-ttu-id="e0800-479">^ （\d{4}） $</span><span class="sxs-lookup"><span data-stu-id="e0800-479">^(\d{4})$</span></span>          | <span data-ttu-id="e0800-480">+ 1206555 $ 1</span><span class="sxs-lookup"><span data-stu-id="e0800-480">+1206555$1</span></span>         |
|<span data-ttu-id="e0800-481">AddSeattleAreaCode</span><span class="sxs-lookup"><span data-stu-id="e0800-481">AddSeattleAreaCode</span></span>    |<span data-ttu-id="e0800-482">^ （\d{4}） $</span><span class="sxs-lookup"><span data-stu-id="e0800-482">^(\d{4})$</span></span>          | <span data-ttu-id="e0800-483">425555 $ 1</span><span class="sxs-lookup"><span data-stu-id="e0800-483">425555$1</span></span>         |
|<span data-ttu-id="e0800-484">StripPlus1</span><span class="sxs-lookup"><span data-stu-id="e0800-484">StripPlus1</span></span>    |<span data-ttu-id="e0800-485">^ + 1 （\d{10}） $</span><span class="sxs-lookup"><span data-stu-id="e0800-485">^+1(\d{10})$</span></span>          | <span data-ttu-id="e0800-486">$1</span><span class="sxs-lookup"><span data-stu-id="e0800-486">$1</span></span>         |

<span data-ttu-id="e0800-487">在這些範例案例中，我們有兩個使用者、Alice 和 Bob。</span><span class="sxs-lookup"><span data-stu-id="e0800-487">In these example scenarios, we have two users, Alice and Bob.</span></span> <span data-ttu-id="e0800-488">劉愛琳是團隊使用者，她的號碼是 + 1 206 555 0100。</span><span class="sxs-lookup"><span data-stu-id="e0800-488">Alice is a Teams user and her number is +1 206 555 0100.</span></span> <span data-ttu-id="e0800-489">Bob 是 PSTN 使用者，而其號碼是 + 1 425 555 0100。</span><span class="sxs-lookup"><span data-stu-id="e0800-489">Bob is a PSTN user and his number is +1 425 555 0100.</span></span>

#### <a name="example-1-inbound-call-to-a-ten-digit-number"></a><span data-ttu-id="e0800-490">範例1：撥入至十位數的電話</span><span class="sxs-lookup"><span data-stu-id="e0800-490">Example 1: Inbound call to a ten-digit number</span></span>

<span data-ttu-id="e0800-491">Bob 使用非 E. 164 10 位數的數位呼叫 Alice。</span><span class="sxs-lookup"><span data-stu-id="e0800-491">Bob calls Alice using a non-E.164 ten-digit number.</span></span> <span data-ttu-id="e0800-492">王俊元會撥打2065550100，以達到 Alice。</span><span class="sxs-lookup"><span data-stu-id="e0800-492">Bob dials 2065550100 to reach Alice.</span></span>
<span data-ttu-id="e0800-493">SBC 在 RequestURI 中使用2065550100，並在 [寄件者] 標題中使用 [標題] 和 [4255550100]。</span><span class="sxs-lookup"><span data-stu-id="e0800-493">SBC uses 2065550100 in the RequestURI and To headers and 4255550100 in the From header.</span></span>

|<span data-ttu-id="e0800-494">資料</span><span class="sxs-lookup"><span data-stu-id="e0800-494">Header</span></span>  |<span data-ttu-id="e0800-495">來源語言</span><span class="sxs-lookup"><span data-stu-id="e0800-495">Original</span></span> |<span data-ttu-id="e0800-496">已翻譯的頁首</span><span class="sxs-lookup"><span data-stu-id="e0800-496">Translated header</span></span> |<span data-ttu-id="e0800-497">已套用參數及規則</span><span class="sxs-lookup"><span data-stu-id="e0800-497">Parameter and rule applied</span></span>  |
|---------|---------|---------|---------|
|<span data-ttu-id="e0800-498">RequestURI</span><span class="sxs-lookup"><span data-stu-id="e0800-498">RequestURI</span></span>  |<span data-ttu-id="e0800-499">邀請 sip:2065550100@sbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="e0800-499">INVITE sip:2065550100@sbc.contoso.com</span></span>|<span data-ttu-id="e0800-500">邀請 sip:+12065550100@sbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="e0800-500">INVITE sip:+12065550100@sbc.contoso.com</span></span>|<span data-ttu-id="e0800-501">InboundTeamsNumberTranslationRulesList 'AddPlus1'</span><span class="sxs-lookup"><span data-stu-id="e0800-501">InboundTeamsNumberTranslationRulesList ‘AddPlus1’</span></span>|
|<span data-ttu-id="e0800-502">自</span><span class="sxs-lookup"><span data-stu-id="e0800-502">TO</span></span>    |<span data-ttu-id="e0800-503">至： \<sip:2065550100@sbc.contoso.com></span><span class="sxs-lookup"><span data-stu-id="e0800-503">TO: \<sip:2065550100@sbc.contoso.com></span></span>|<span data-ttu-id="e0800-504">至： \<sip:+12065550100@sbc.contoso.com></span><span class="sxs-lookup"><span data-stu-id="e0800-504">TO: \<sip:+12065550100@sbc.contoso.com></span></span>|<span data-ttu-id="e0800-505">InboundTeamsNumberTranlationRulesList 'AddPlus1'</span><span class="sxs-lookup"><span data-stu-id="e0800-505">InboundTeamsNumberTranlationRulesList ‘AddPlus1’</span></span>|
|<span data-ttu-id="e0800-506">從</span><span class="sxs-lookup"><span data-stu-id="e0800-506">FROM</span></span>   |<span data-ttu-id="e0800-507">發件\<人： sip:4255550100@sbc.contoso.com></span><span class="sxs-lookup"><span data-stu-id="e0800-507">FROM: \<sip:4255550100@sbc.contoso.com></span></span>|<span data-ttu-id="e0800-508">發件\<人： sip:+14255550100@sbc.contoso.com></span><span class="sxs-lookup"><span data-stu-id="e0800-508">FROM: \<sip:+14255550100@sbc.contoso.com></span></span>|<span data-ttu-id="e0800-509">InboundPSTNNumberTranslationRulesList 'AddPlus1'</span><span class="sxs-lookup"><span data-stu-id="e0800-509">InboundPSTNNumberTranslationRulesList ‘AddPlus1’</span></span>|

#### <a name="example-2-inbound-call-to-a-four-digit-number"></a><span data-ttu-id="e0800-510">範例2：撥入至四位數的電話號碼</span><span class="sxs-lookup"><span data-stu-id="e0800-510">Example 2: Inbound call to a four-digit number</span></span>

<span data-ttu-id="e0800-511">Bob 使用四位數的數位撥打 Alice。</span><span class="sxs-lookup"><span data-stu-id="e0800-511">Bob calls Alice using a four-digit number.</span></span> <span data-ttu-id="e0800-512">王俊元會撥打0100，以達到 Alice。</span><span class="sxs-lookup"><span data-stu-id="e0800-512">Bob dials 0100 to reach Alice.</span></span>
<span data-ttu-id="e0800-513">SBC 在 RequestURI 中使用0100，並在 [寄件者] 標題中使用 [標題] 和 [4255550100]。</span><span class="sxs-lookup"><span data-stu-id="e0800-513">SBC uses 0100 in the RequestURI and To headers and 4255550100 in the From header.</span></span>

|<span data-ttu-id="e0800-514">資料</span><span class="sxs-lookup"><span data-stu-id="e0800-514">Header</span></span>  |<span data-ttu-id="e0800-515">來源語言</span><span class="sxs-lookup"><span data-stu-id="e0800-515">Original</span></span> |<span data-ttu-id="e0800-516">已翻譯的頁首</span><span class="sxs-lookup"><span data-stu-id="e0800-516">Translated header</span></span> |<span data-ttu-id="e0800-517">已套用參數及規則</span><span class="sxs-lookup"><span data-stu-id="e0800-517">Parameter and rule applied</span></span>  |
|---------|---------|---------|---------|
|<span data-ttu-id="e0800-518">RequestURI</span><span class="sxs-lookup"><span data-stu-id="e0800-518">RequestURI</span></span>  |<span data-ttu-id="e0800-519">邀請 sip:0100@sbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="e0800-519">INVITE sip:0100@sbc.contoso.com</span></span>          |<span data-ttu-id="e0800-520">邀請 sip:+12065550100@sbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="e0800-520">INVITE sip:+12065550100@sbc.contoso.com</span></span>           |<span data-ttu-id="e0800-521">InboundTeamsNumberTranlationRulesList 'AddE164SeattleAreaCode'</span><span class="sxs-lookup"><span data-stu-id="e0800-521">InboundTeamsNumberTranlationRulesList ‘AddE164SeattleAreaCode’</span></span>        |
|<span data-ttu-id="e0800-522">自</span><span class="sxs-lookup"><span data-stu-id="e0800-522">TO</span></span>    |<span data-ttu-id="e0800-523">至： \<sip:0100@sbc.contoso.com></span><span class="sxs-lookup"><span data-stu-id="e0800-523">TO: \<sip:0100@sbc.contoso.com></span></span>|<span data-ttu-id="e0800-524">至： \<sip:+12065550100@sbc.contoso.com></span><span class="sxs-lookup"><span data-stu-id="e0800-524">TO: \<sip:+12065550100@sbc.contoso.com></span></span>|<span data-ttu-id="e0800-525">InboundTeamsNumberTranlationRulesList 'AddE164SeattleAreaCode'</span><span class="sxs-lookup"><span data-stu-id="e0800-525">InboundTeamsNumberTranlationRulesList ‘AddE164SeattleAreaCode’</span></span>         |
|<span data-ttu-id="e0800-526">從</span><span class="sxs-lookup"><span data-stu-id="e0800-526">FROM</span></span>   |<span data-ttu-id="e0800-527">發件\<人： sip:4255550100@sbc.contoso.com></span><span class="sxs-lookup"><span data-stu-id="e0800-527">FROM: \<sip:4255550100@sbc.contoso.com></span></span>|<span data-ttu-id="e0800-528">發件\<人： sip:+14255550100@sbc.contoso.com></span><span class="sxs-lookup"><span data-stu-id="e0800-528">FROM: \<sip:+14255550100@sbc.contoso.com></span></span>|<span data-ttu-id="e0800-529">InboundPSTNNumberTranlationRulesList 'AddPlus1'</span><span class="sxs-lookup"><span data-stu-id="e0800-529">InboundPSTNNumberTranlationRulesList ‘AddPlus1’</span></span>        |

#### <a name="example-3-outbound-call-using-a-ten-digit-non-e164-number"></a><span data-ttu-id="e0800-530">範例3：使用10位數的非 E. 164 號碼撥出通話</span><span class="sxs-lookup"><span data-stu-id="e0800-530">Example 3: Outbound call using a ten-digit non-E.164 number</span></span>

<span data-ttu-id="e0800-531">劉愛琳會使用十位數的數位呼叫 Bob。</span><span class="sxs-lookup"><span data-stu-id="e0800-531">Alice calls Bob using a ten-digit number.</span></span> <span data-ttu-id="e0800-532">劉愛琳會撥打 425 555 0100 來取得 Bob 的聯繫。</span><span class="sxs-lookup"><span data-stu-id="e0800-532">Alice dials 425 555 0100 to reach Bob.</span></span>
<span data-ttu-id="e0800-533">SBC 針對團隊和 PSTN 使用者設定為使用非 E. 164 10 位數的數位。</span><span class="sxs-lookup"><span data-stu-id="e0800-533">SBC is configured to use non-E.164 ten-digit numbers for both Teams and PSTN users.</span></span>

<span data-ttu-id="e0800-534">在這種情況下，撥號方案會在傳送數位至直接路由介面之前先轉換號碼。</span><span class="sxs-lookup"><span data-stu-id="e0800-534">In this scenario, a dial plan translates the number before sending it to the Direct Routing interface.</span></span> <span data-ttu-id="e0800-535">當 Alice 在 [團隊用戶端] 中輸入 425 555 0100 時，該數位會依國家/地區撥號方案轉譯為 [+ 14255550100]。</span><span class="sxs-lookup"><span data-stu-id="e0800-535">When Alice enters 425 555 0100 in the Teams client, the number is translated to +14255550100 by the country dial plan.</span></span> <span data-ttu-id="e0800-536">產生的數位是撥號方案規則與團隊翻譯規則的累計正常化。</span><span class="sxs-lookup"><span data-stu-id="e0800-536">The resulting numbers are a cumulative normalization of the dial plan rules and Teams translation rules.</span></span> <span data-ttu-id="e0800-537">團隊翻譯規則會移除撥號方案新增的 "+ 1"。</span><span class="sxs-lookup"><span data-stu-id="e0800-537">The Teams translation rules remove the "+1" that was added by the dial plan.</span></span>

|<span data-ttu-id="e0800-538">資料</span><span class="sxs-lookup"><span data-stu-id="e0800-538">Header</span></span>  |<span data-ttu-id="e0800-539">來源語言</span><span class="sxs-lookup"><span data-stu-id="e0800-539">Original</span></span> |<span data-ttu-id="e0800-540">已翻譯的頁首</span><span class="sxs-lookup"><span data-stu-id="e0800-540">Translated header</span></span> |<span data-ttu-id="e0800-541">已套用參數及規則</span><span class="sxs-lookup"><span data-stu-id="e0800-541">Parameter and rule applied</span></span>  |
|---------|---------|---------|---------|
|<span data-ttu-id="e0800-542">RequestURI</span><span class="sxs-lookup"><span data-stu-id="e0800-542">RequestURI</span></span>  |<span data-ttu-id="e0800-543">邀請 sip:+14255550100@sbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="e0800-543">INVITE sip:+14255550100@sbc.contoso.com</span></span>          |<span data-ttu-id="e0800-544">邀請 sip:4255550100@sbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="e0800-544">INVITE sip:4255550100@sbc.contoso.com</span></span>       |<span data-ttu-id="e0800-545">OutboundPSTNNumberTranlationRulesList 'StripPlus1'</span><span class="sxs-lookup"><span data-stu-id="e0800-545">OutboundPSTNNumberTranlationRulesList ‘StripPlus1’</span></span>         |
|<span data-ttu-id="e0800-546">自</span><span class="sxs-lookup"><span data-stu-id="e0800-546">TO</span></span>    |<span data-ttu-id="e0800-547">至： \<sip:+14255550100@sbc.contoso.com></span><span class="sxs-lookup"><span data-stu-id="e0800-547">TO: \<sip:+14255550100@sbc.contoso.com></span></span>|<span data-ttu-id="e0800-548">至： \<sip:4255555555@sbc.contoso.com></span><span class="sxs-lookup"><span data-stu-id="e0800-548">TO: \<sip:4255555555@sbc.contoso.com></span></span>|<span data-ttu-id="e0800-549">OutboundPSTNNumberTranlationRulesList 'StripPlus1'</span><span class="sxs-lookup"><span data-stu-id="e0800-549">OutboundPSTNNumberTranlationRulesList ‘StripPlus1’</span></span>       |
|<span data-ttu-id="e0800-550">從</span><span class="sxs-lookup"><span data-stu-id="e0800-550">FROM</span></span>   |<span data-ttu-id="e0800-551">發件\<人： sip:+12065550100@sbc.contoso.com></span><span class="sxs-lookup"><span data-stu-id="e0800-551">FROM: \<sip:+12065550100@sbc.contoso.com></span></span>|<span data-ttu-id="e0800-552">發件\<人： sip:2065550100@sbc.contoso.com></span><span class="sxs-lookup"><span data-stu-id="e0800-552">FROM: \<sip:2065550100@sbc.contoso.com></span></span>|<span data-ttu-id="e0800-553">OutboundTeamsNumberTranlationRulesList 'StripPlus1'</span><span class="sxs-lookup"><span data-stu-id="e0800-553">OutboundTeamsNumberTranlationRulesList ‘StripPlus1’</span></span>         |

#### <a name="example-4-outbound-call-using-a-four-digit-non-e164-number"></a><span data-ttu-id="e0800-554">範例4：使用四位數的非 E. 164 號碼撥出通話</span><span class="sxs-lookup"><span data-stu-id="e0800-554">Example 4: Outbound call using a four-digit non-E.164 number</span></span>

<span data-ttu-id="e0800-555">劉愛琳會使用四位數的數位呼叫 Bob。</span><span class="sxs-lookup"><span data-stu-id="e0800-555">Alice calls Bob using a four-digit number.</span></span> <span data-ttu-id="e0800-556">Alice 使用0100來從來電到 Bob 或使用連絡人。</span><span class="sxs-lookup"><span data-stu-id="e0800-556">Alice uses 0100 to reach Bob from Calls or by using a contact.</span></span>
<span data-ttu-id="e0800-557">SBC 設定為使用非 E. 164 個4位數的團隊使用者，以及十位數的 PSTN 使用者數位。</span><span class="sxs-lookup"><span data-stu-id="e0800-557">SBC is configured to use non-E.164 four-digit numbers for Teams users and ten-digit numbers for PSTN users.</span></span> <span data-ttu-id="e0800-558">在這種情況下，不會套用撥號方案。</span><span class="sxs-lookup"><span data-stu-id="e0800-558">The dial plan isn't applied in this scenario.</span></span>

|<span data-ttu-id="e0800-559">資料</span><span class="sxs-lookup"><span data-stu-id="e0800-559">Header</span></span>  |<span data-ttu-id="e0800-560">來源語言</span><span class="sxs-lookup"><span data-stu-id="e0800-560">Original</span></span> |<span data-ttu-id="e0800-561">已翻譯的頁首</span><span class="sxs-lookup"><span data-stu-id="e0800-561">Translated header</span></span> |<span data-ttu-id="e0800-562">已套用參數及規則</span><span class="sxs-lookup"><span data-stu-id="e0800-562">Parameter and rule applied</span></span>  |
|---------|---------|---------|---------|
|<span data-ttu-id="e0800-563">RequestURI</span><span class="sxs-lookup"><span data-stu-id="e0800-563">RequestURI</span></span>  |<span data-ttu-id="e0800-564">邀請 sip:0100@sbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="e0800-564">INVITE sip:0100@sbc.contoso.com</span></span>           |<span data-ttu-id="e0800-565">邀請 sip:4255550100@sbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="e0800-565">INVITE sip:4255550100@sbc.contoso.com</span></span>       |<span data-ttu-id="e0800-566">InboundTeamsNumberTranlationRulesList 'AddSeattleAreaCode'</span><span class="sxs-lookup"><span data-stu-id="e0800-566">InboundTeamsNumberTranlationRulesList ‘AddSeattleAreaCode’</span></span>         |
|<span data-ttu-id="e0800-567">自</span><span class="sxs-lookup"><span data-stu-id="e0800-567">TO</span></span>    |<span data-ttu-id="e0800-568">至： \<sip:0100@sbc.contoso.com></span><span class="sxs-lookup"><span data-stu-id="e0800-568">TO: \<sip:0100@sbc.contoso.com></span></span>|<span data-ttu-id="e0800-569">至： \<sip:4255555555@sbc.contoso.com></span><span class="sxs-lookup"><span data-stu-id="e0800-569">TO: \<sip:4255555555@sbc.contoso.com></span></span>|<span data-ttu-id="e0800-570">InboundTeamsNumberTranlationRulesList 'AddSeattleAreaCode'</span><span class="sxs-lookup"><span data-stu-id="e0800-570">InboundTeamsNumberTranlationRulesList ‘AddSeattleAreaCode’</span></span>       |
|<span data-ttu-id="e0800-571">從</span><span class="sxs-lookup"><span data-stu-id="e0800-571">FROM</span></span>   |<span data-ttu-id="e0800-572">發件\<人： sip:+12065550100@sbc.contoso.com></span><span class="sxs-lookup"><span data-stu-id="e0800-572">FROM: \<sip:+12065550100@sbc.contoso.com></span></span>|<span data-ttu-id="e0800-573">發件\<人： sip:2065550100@sbc.contoso.com></span><span class="sxs-lookup"><span data-stu-id="e0800-573">FROM: \<sip:2065550100@sbc.contoso.com></span></span>| <span data-ttu-id="e0800-574">InboundPSTNNumberTranlationRulesList 'StripPlus1'</span><span class="sxs-lookup"><span data-stu-id="e0800-574">InboundPSTNNumberTranlationRulesList ‘StripPlus1’</span></span> |

## <a name="see-also"></a><span data-ttu-id="e0800-575">另請參閱</span><span class="sxs-lookup"><span data-stu-id="e0800-575">See also</span></span>

[<span data-ttu-id="e0800-576">規劃直接路由</span><span class="sxs-lookup"><span data-stu-id="e0800-576">Plan Direct Routing</span></span>](direct-routing-plan.md)
