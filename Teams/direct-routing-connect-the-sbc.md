---
title: 將您的會話邊界控制器（SBC）連線至直接路由
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
ms.openlocfilehash: e86b0397e4c00b892d99a0814579f20ba14e8b59
ms.sourcegitcommit: 0289062510f0791906dab2791c5db8acb1cf849a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/20/2020
ms.locfileid: "42157943"
---
# <a name="connect-your-session-border-controller-sbc-to-direct-routing"></a><span data-ttu-id="43eed-103">將您的會話邊界控制器（SBC）連線至直接路由</span><span class="sxs-lookup"><span data-stu-id="43eed-103">Connect your Session Border Controller (SBC) to Direct Routing</span></span> 

<span data-ttu-id="43eed-104">本文說明如何將您的會話邊界控制器（SBC）連線至手機系統直接路由。</span><span class="sxs-lookup"><span data-stu-id="43eed-104">This article describes how to connect your Session Border Controller (SBC) to Phone System Direct Routing.</span></span>  <span data-ttu-id="43eed-105">以下是設定直接路由的步驟1：</span><span class="sxs-lookup"><span data-stu-id="43eed-105">This is step 1 of the following steps for configuring Direct Routing:</span></span>

- <span data-ttu-id="43eed-106">**步驟1。將您的 SBC 與電話系統連接並驗證**連線（本文）</span><span class="sxs-lookup"><span data-stu-id="43eed-106">**Step 1. Connect your SBC with Phone System and validate the connection** (This article)</span></span>
- <span data-ttu-id="43eed-107">步驟2。</span><span class="sxs-lookup"><span data-stu-id="43eed-107">Step 2.</span></span> [<span data-ttu-id="43eed-108">允許使用者直接傳送</span><span class="sxs-lookup"><span data-stu-id="43eed-108">Enable users for Direct Routing</span></span>](direct-routing-enable-users.md)
- <span data-ttu-id="43eed-109">步驟3。</span><span class="sxs-lookup"><span data-stu-id="43eed-109">Step 3.</span></span> [<span data-ttu-id="43eed-110">設定通話路由</span><span class="sxs-lookup"><span data-stu-id="43eed-110">Configure call routing</span></span>](direct-routing-voice-routing.md)
- <span data-ttu-id="43eed-111">步驟4。</span><span class="sxs-lookup"><span data-stu-id="43eed-111">Step 4.</span></span> [<span data-ttu-id="43eed-112">將數位轉換成替換格式</span><span class="sxs-lookup"><span data-stu-id="43eed-112">Translate numbers to an alternate format</span></span>](direct-routing-translate-numbers.md) 

<span data-ttu-id="43eed-113">如需設定直接路由所需的所有步驟的詳細資訊，請參閱設定[直接路由](direct-routing-configure.md)。</span><span class="sxs-lookup"><span data-stu-id="43eed-113">For information on all the steps required for setting up Direct Routing, see [Configure Direct Routing](direct-routing-configure.md).</span></span>

<span data-ttu-id="43eed-114">若要將您的 SBC 連線至直接路由，您必須：</span><span class="sxs-lookup"><span data-stu-id="43eed-114">To connect your SBC to Direct Routing, you'll need to:</span></span> 

1. <span data-ttu-id="43eed-115">使用 PowerShell**連線到商務用 Skype Online**系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="43eed-115">Connect to **Skype for Business Online** admin center by using PowerShell.</span></span>            
2. <span data-ttu-id="43eed-116">將 SBC 連接至租使用者。</span><span class="sxs-lookup"><span data-stu-id="43eed-116">Connect the SBC to the tenant.</span></span>
3. <span data-ttu-id="43eed-117">驗證連線。</span><span class="sxs-lookup"><span data-stu-id="43eed-117">Validate the connection.</span></span> 

## <a name="connect-to-skype-for-business-online-by-using-powershell"></a><span data-ttu-id="43eed-118">使用 PowerShell 連線到商務用 Skype Online</span><span class="sxs-lookup"><span data-stu-id="43eed-118">Connect to Skype for Business Online by using PowerShell</span></span> 

<span data-ttu-id="43eed-119">您可以使用連接至租使用者的 PowerShell 會話，將 SBC 與直接路由介面配對。</span><span class="sxs-lookup"><span data-stu-id="43eed-119">You can use a PowerShell session connected to the tenant to pair the SBC to the Direct Routing interface.</span></span> <span data-ttu-id="43eed-120">若要開啟 PowerShell 會話，請依照[設定您的 Windows PowerShell 電腦](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)中所述的步驟進行。</span><span class="sxs-lookup"><span data-stu-id="43eed-120">To open a PowerShell session, follow the steps outlined in [Set up your computer for Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span> 
 
<span data-ttu-id="43eed-121">建立遠端 PowerShell 會話之後，請確認您可以看到管理 SBC 的命令。</span><span class="sxs-lookup"><span data-stu-id="43eed-121">After you establish a remote PowerShell session, validate that you can see the commands to manage the SBC.</span></span> <span data-ttu-id="43eed-122">若要驗證命令，請在 PowerShell 會話中輸入或複製並貼上下列命令，然後按 Enter：</span><span class="sxs-lookup"><span data-stu-id="43eed-122">To validate the commands, type or copy and paste the following command in the PowerShell session and press Enter:</span></span> 

```PowerShell
Get-Command *onlinePSTNGateway*
```

<span data-ttu-id="43eed-123">這個命令會傳回這裡顯示的四個函數，讓您管理 SBC。</span><span class="sxs-lookup"><span data-stu-id="43eed-123">The command returns the four functions shown here that will let you manage the SBC.</span></span> 

<pre>
CommandType    Name                       Version    Source 
-----------    ----                       -------    ------ 
Function       Get-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt 
Function       New-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt 
Function       Remove-CsOnlinePSTNGateway 1.0        tmp_v5fiu1no.wxt 
Function       Set-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt
</pre>   


## <a name="connect-the-sbc-to-the-tenant"></a><span data-ttu-id="43eed-124">將 SBC 連接至租使用者</span><span class="sxs-lookup"><span data-stu-id="43eed-124">Connect the SBC to the tenant</span></span> 

<span data-ttu-id="43eed-125">若要將 SBC 連接至租使用者，請在 PowerShell 會話中輸入下列內容，然後按 Enter 鍵：</span><span class="sxs-lookup"><span data-stu-id="43eed-125">To connect the SBC to the tenant, in the PowerShell session type the following and press Enter:</span></span> 

```PowerShell
New-CsOnlinePSTNGateway -Fqdn <SBC FQDN> -SipSignalingPort <SBC SIP Port> -MaxConcurrentSessions <Max Concurrent Sessions the SBC can handle> -Enabled $true 
```
  > [!NOTE]
  > 1. <span data-ttu-id="43eed-126">Microsoft 建議您在 SBC 中設定最大通話限制，使用可在 SBC 檔中找到的資訊。</span><span class="sxs-lookup"><span data-stu-id="43eed-126">Microsoft recommends setting a maximum call limit in the SBC, using information that can be found in the SBC documentation.</span></span> <span data-ttu-id="43eed-127">如果 SBC 是容量等級，則限制會觸發通知。</span><span class="sxs-lookup"><span data-stu-id="43eed-127">The limit will trigger a notification if the SBC is at the capacity level.</span></span>
  > 2. <span data-ttu-id="43eed-128">您只能將 SBC 的網域部分與您在租使用者中註冊的其中一個網域相符（除了\*onmicrosoft.com），才能將它配對。</span><span class="sxs-lookup"><span data-stu-id="43eed-128">You can only pair the SBC if the domain portion of its FQDN matches one of the domains registered in your tenant, except \*.onmicrosoft.com.</span></span> <span data-ttu-id="43eed-129">SBC \*FQDN 名稱不支援使用 onmicrosoft.com 功能變數名稱。</span><span class="sxs-lookup"><span data-stu-id="43eed-129">Using \*.onmicrosoft.com domain names is not supported for the SBC FQDN name.</span></span> <span data-ttu-id="43eed-130">例如，如果您有兩個功能變數名稱：</span><span class="sxs-lookup"><span data-stu-id="43eed-130">For example, if you have two domain names:</span></span><br/><br/>
  > <span data-ttu-id="43eed-131">**contoso**</span><span class="sxs-lookup"><span data-stu-id="43eed-131">**contoso**.com</span></span><br/><span data-ttu-id="43eed-132">**contoso**. onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="43eed-132">**contoso**.onmicrosoft.com</span></span><br/><br/>
  > <span data-ttu-id="43eed-133">針對 SBC 名稱，您可以使用名稱 sbc.contoso.com。</span><span class="sxs-lookup"><span data-stu-id="43eed-133">For the SBC name, you can use the name sbc.contoso.com.</span></span> <span data-ttu-id="43eed-134">如果您嘗試將 SBC 與 name （contoso..）結合使用，系統將不會讓您，因為該域不是由這個租使用者所擁有。</span><span class="sxs-lookup"><span data-stu-id="43eed-134">If you try to pair the SBC with a name sbc.contoso.abc, the system will not let you, as the domain is not owned by this tenant.</span></span><br/>
  > <span data-ttu-id="43eed-135">除了在您的租使用者中註冊的網域外，請務必先擁有該網域的使用者以及指派的 E3 或 E5 授權。</span><span class="sxs-lookup"><span data-stu-id="43eed-135">In addition to the domain registered in your tenant, it is important that there is a user with that domain and an assigned E3 or E5 license.</span></span> <span data-ttu-id="43eed-136">如果不是，您會收到下列錯誤：</span><span class="sxs-lookup"><span data-stu-id="43eed-136">If not, you will receive the following error:</span></span><br/>
  <span data-ttu-id="43eed-137">`Can not use the “sbc.contoso.com” domain as it was not configured for this tenant`.</span><span class="sxs-lookup"><span data-stu-id="43eed-137">`Can not use the “sbc.contoso.com” domain as it was not configured for this tenant`.</span></span>

```PowerShell
New-CsOnlinePSTNGateway -Identity sbc.contoso.com -Enabled $true -SipSignalingPort 5067 -MaxConcurrentSessions 100 
```
<span data-ttu-id="43eed-138">回報</span><span class="sxs-lookup"><span data-stu-id="43eed-138">Returns:</span></span>
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
<span data-ttu-id="43eed-139">您可以在連線程式期間設定其他選項。</span><span class="sxs-lookup"><span data-stu-id="43eed-139">There are additional options that can be set during the connection process.</span></span> <span data-ttu-id="43eed-140">不過，在前面的範例中，只會顯示所需的最低參數。</span><span class="sxs-lookup"><span data-stu-id="43eed-140">In the previous example, however, only the minimum required parameters are shown.</span></span> 
 
<span data-ttu-id="43eed-141">下表列出您可以在設定參數時使用的其他參數```New-CsOnlinePstnGateway```。</span><span class="sxs-lookup"><span data-stu-id="43eed-141">The following table lists the additional parameters that you can use in setting parameters for ```New-CsOnlinePstnGateway```.</span></span>

|<span data-ttu-id="43eed-142">必填？</span><span class="sxs-lookup"><span data-stu-id="43eed-142">Required?</span></span>|<span data-ttu-id="43eed-143">名稱</span><span class="sxs-lookup"><span data-stu-id="43eed-143">Name</span></span>|<span data-ttu-id="43eed-144">描述</span><span class="sxs-lookup"><span data-stu-id="43eed-144">Description</span></span>|<span data-ttu-id="43eed-145">設置</span><span class="sxs-lookup"><span data-stu-id="43eed-145">Default</span></span>|<span data-ttu-id="43eed-146">可能值</span><span class="sxs-lookup"><span data-stu-id="43eed-146">Possible values</span></span>|<span data-ttu-id="43eed-147">類型與限制</span><span class="sxs-lookup"><span data-stu-id="43eed-147">Type and restrictions</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="43eed-148">是</span><span class="sxs-lookup"><span data-stu-id="43eed-148">Yes</span></span>|<span data-ttu-id="43eed-149">稱</span><span class="sxs-lookup"><span data-stu-id="43eed-149">FQDN</span></span>|<span data-ttu-id="43eed-150">SBC 的 FQDN 名稱</span><span class="sxs-lookup"><span data-stu-id="43eed-150">The FQDN name of the SBC</span></span> |<span data-ttu-id="43eed-151">無</span><span class="sxs-lookup"><span data-stu-id="43eed-151">None</span></span>|<span data-ttu-id="43eed-152">NoneFQDN name，限制63字元</span><span class="sxs-lookup"><span data-stu-id="43eed-152">NoneFQDN name, limit 63 characters</span></span>|<span data-ttu-id="43eed-153">在[Active Directory 中針對電腦、網域、網站和組織單位命名慣例](https://support.microsoft.com/help/909264)的允許和禁止字元清單</span><span class="sxs-lookup"><span data-stu-id="43eed-153">String, list of allowed and disallowed characters on [Naming conventions in Active Directory for computers, domains, sites, and OUs](https://support.microsoft.com/help/909264)</span></span>|
|<span data-ttu-id="43eed-154">否</span><span class="sxs-lookup"><span data-stu-id="43eed-154">No</span></span>|<span data-ttu-id="43eed-155">MediaBypass</span><span class="sxs-lookup"><span data-stu-id="43eed-155">MediaBypass</span></span> |<span data-ttu-id="43eed-156">指示 SBC 的參數支援「媒體旁路」，且系統管理員想要使用它。</span><span class="sxs-lookup"><span data-stu-id="43eed-156">Parameter indicated of the SBC supports Media Bypass and the administrator wants to use it.</span></span>|<span data-ttu-id="43eed-157">無</span><span class="sxs-lookup"><span data-stu-id="43eed-157">None</span></span>|<span data-ttu-id="43eed-158">滿足</span><span class="sxs-lookup"><span data-stu-id="43eed-158">True</span></span><br/><span data-ttu-id="43eed-159">虛假</span><span class="sxs-lookup"><span data-stu-id="43eed-159">False</span></span>|<span data-ttu-id="43eed-160">Boolean</span><span class="sxs-lookup"><span data-stu-id="43eed-160">Boolean</span></span>|
|<span data-ttu-id="43eed-161">是</span><span class="sxs-lookup"><span data-stu-id="43eed-161">Yes</span></span>|<span data-ttu-id="43eed-162">SipSignalingPort</span><span class="sxs-lookup"><span data-stu-id="43eed-162">SipSignalingPort</span></span> |<span data-ttu-id="43eed-163">使用傳輸層安全性（TLS）通訊協定，與直接路由服務通訊時所使用的偵聽埠。</span><span class="sxs-lookup"><span data-stu-id="43eed-163">Listening port used for communicating with Direct Routing services by using the Transport Layer Security (TLS) protocol.</span></span>|<span data-ttu-id="43eed-164">無</span><span class="sxs-lookup"><span data-stu-id="43eed-164">None</span></span>|<span data-ttu-id="43eed-165">任何埠</span><span class="sxs-lookup"><span data-stu-id="43eed-165">Any port</span></span>|<span data-ttu-id="43eed-166">0到65535</span><span class="sxs-lookup"><span data-stu-id="43eed-166">0 to 65535</span></span> |
|<span data-ttu-id="43eed-167">否</span><span class="sxs-lookup"><span data-stu-id="43eed-167">No</span></span>|<span data-ttu-id="43eed-168">FailoverTimeSeconds</span><span class="sxs-lookup"><span data-stu-id="43eed-168">FailoverTimeSeconds</span></span> |<span data-ttu-id="43eed-169">當設定為10（預設值）時，閘道不會在10秒內應答的輸出呼叫會路由至下一個可用的幹線;如果沒有其他 trunks，就會自動中斷通話。</span><span class="sxs-lookup"><span data-stu-id="43eed-169">When set to 10 (default value), outbound calls that are not answered by the gateway within 10 seconds are routed to the next available trunk; if there are no additional trunks, then the call is automatically dropped.</span></span> <span data-ttu-id="43eed-170">組織的網路速度與閘道回應速度若是很慢，可能會造成來電不必要地遭到掛斷。</span><span class="sxs-lookup"><span data-stu-id="43eed-170">In an organization with slow networks and gateway responses, that could potentially result in calls being dropped unnecessarily.</span></span> <span data-ttu-id="43eed-171">預設值為10。</span><span class="sxs-lookup"><span data-stu-id="43eed-171">The default value is 10.</span></span>|<span data-ttu-id="43eed-172">第</span><span class="sxs-lookup"><span data-stu-id="43eed-172">10</span></span>|<span data-ttu-id="43eed-173">電話</span><span class="sxs-lookup"><span data-stu-id="43eed-173">Number</span></span>|<span data-ttu-id="43eed-174">Int</span><span class="sxs-lookup"><span data-stu-id="43eed-174">Int</span></span>|
|<span data-ttu-id="43eed-175">否</span><span class="sxs-lookup"><span data-stu-id="43eed-175">No</span></span>|<span data-ttu-id="43eed-176">ForwardCallHistory</span><span class="sxs-lookup"><span data-stu-id="43eed-176">ForwardCallHistory</span></span> |<span data-ttu-id="43eed-177">指出是否透過主幹轉送通話記錄資訊。</span><span class="sxs-lookup"><span data-stu-id="43eed-177">Indicates whether call history information will be forwarded through the trunk.</span></span> <span data-ttu-id="43eed-178">如果啟用，Office 365 PSTN Proxy 會傳送兩個標頭： [歷程記錄] 資訊和 [參照者]。</span><span class="sxs-lookup"><span data-stu-id="43eed-178">If enabled, the Office 365 PSTN Proxy sends two headers: History-info and Referred-By.</span></span> <span data-ttu-id="43eed-179">預設值為**False** （$False）。</span><span class="sxs-lookup"><span data-stu-id="43eed-179">The default value is **False** ($False).</span></span> |<span data-ttu-id="43eed-180">虛假</span><span class="sxs-lookup"><span data-stu-id="43eed-180">False</span></span>|<span data-ttu-id="43eed-181">滿足</span><span class="sxs-lookup"><span data-stu-id="43eed-181">True</span></span><br/><span data-ttu-id="43eed-182">虛假</span><span class="sxs-lookup"><span data-stu-id="43eed-182">False</span></span>|<span data-ttu-id="43eed-183">Boolean</span><span class="sxs-lookup"><span data-stu-id="43eed-183">Boolean</span></span>|
|<span data-ttu-id="43eed-184">否</span><span class="sxs-lookup"><span data-stu-id="43eed-184">No</span></span>|<span data-ttu-id="43eed-185">ForwardPAI</span><span class="sxs-lookup"><span data-stu-id="43eed-185">ForwardPAI</span></span>|<span data-ttu-id="43eed-186">指出 P-Asserted-Identity (PAI) 標頭是否要隨通話轉接。</span><span class="sxs-lookup"><span data-stu-id="43eed-186">Indicates whether the P-Asserted-Identity (PAI) header will be forwarded along with the call.</span></span> <span data-ttu-id="43eed-187">PAI 標頭可用於驗證來電者的身分識別。</span><span class="sxs-lookup"><span data-stu-id="43eed-187">The PAI header provides a way to verify the identity of the caller.</span></span> <span data-ttu-id="43eed-188">如果啟用，則也會傳送隱私權： ID 標頭。</span><span class="sxs-lookup"><span data-stu-id="43eed-188">If enabled the Privacy:ID header will also be sent.</span></span> <span data-ttu-id="43eed-189">預設值為**False** （$False）。</span><span class="sxs-lookup"><span data-stu-id="43eed-189">The default value is **False** ($False).</span></span>|<span data-ttu-id="43eed-190">虛假</span><span class="sxs-lookup"><span data-stu-id="43eed-190">False</span></span>|<span data-ttu-id="43eed-191">滿足</span><span class="sxs-lookup"><span data-stu-id="43eed-191">True</span></span><br/><span data-ttu-id="43eed-192">虛假</span><span class="sxs-lookup"><span data-stu-id="43eed-192">False</span></span>|<span data-ttu-id="43eed-193">Boolean</span><span class="sxs-lookup"><span data-stu-id="43eed-193">Boolean</span></span>|
|<span data-ttu-id="43eed-194">否</span><span class="sxs-lookup"><span data-stu-id="43eed-194">No</span></span>|<span data-ttu-id="43eed-195">SendSIPOptions</span><span class="sxs-lookup"><span data-stu-id="43eed-195">SendSIPOptions</span></span> |<span data-ttu-id="43eed-196">定義 SBC 是否將傳送 SIP 選項。</span><span class="sxs-lookup"><span data-stu-id="43eed-196">Defines if an SBC will or will not send the SIP options.</span></span> <span data-ttu-id="43eed-197">如果停用，則會將 SBC 排除在監視及觸發系統中。</span><span class="sxs-lookup"><span data-stu-id="43eed-197">If disabled, the SBC will be excluded from Monitoring and Alerting system.</span></span> <span data-ttu-id="43eed-198">我們強烈建議您啟用 SIP 選項。</span><span class="sxs-lookup"><span data-stu-id="43eed-198">We highly recommend that you enable SIP options.</span></span> <span data-ttu-id="43eed-199">預設值為**True**。</span><span class="sxs-lookup"><span data-stu-id="43eed-199">Default value is **True**.</span></span> |<span data-ttu-id="43eed-200">滿足</span><span class="sxs-lookup"><span data-stu-id="43eed-200">True</span></span>|<span data-ttu-id="43eed-201">滿足</span><span class="sxs-lookup"><span data-stu-id="43eed-201">True</span></span><br/><span data-ttu-id="43eed-202">虛假</span><span class="sxs-lookup"><span data-stu-id="43eed-202">False</span></span>|<span data-ttu-id="43eed-203">Boolean</span><span class="sxs-lookup"><span data-stu-id="43eed-203">Boolean</span></span>|
|<span data-ttu-id="43eed-204">否</span><span class="sxs-lookup"><span data-stu-id="43eed-204">No</span></span>|<span data-ttu-id="43eed-205">MaxConcurrentSessions</span><span class="sxs-lookup"><span data-stu-id="43eed-205">MaxConcurrentSessions</span></span> |<span data-ttu-id="43eed-206">由觸發系統所使用。</span><span class="sxs-lookup"><span data-stu-id="43eed-206">Used by alerting system.</span></span> <span data-ttu-id="43eed-207">設定任何值後，當併發會話數量為90% 或高於此值時，警示系統會為租使用者管理員產生警示。</span><span class="sxs-lookup"><span data-stu-id="43eed-207">When any value is set, the alerting system will generate an alert to the tenant administrator when the number of concurrent sessions is 90% or higher than this value.</span></span> <span data-ttu-id="43eed-208">如果未設定參數，就不會產生預警。</span><span class="sxs-lookup"><span data-stu-id="43eed-208">If the parameter is not set, the alerts are not generated.</span></span> <span data-ttu-id="43eed-209">不過，監視系統會在每24小時報告併發會話數目。</span><span class="sxs-lookup"><span data-stu-id="43eed-209">However, the monitoring system will report number of concurrent sessions every 24 hours.</span></span> |<span data-ttu-id="43eed-210">非</span><span class="sxs-lookup"><span data-stu-id="43eed-210">Null</span></span>|<span data-ttu-id="43eed-211">非</span><span class="sxs-lookup"><span data-stu-id="43eed-211">Null</span></span><br/><span data-ttu-id="43eed-212">1到100000</span><span class="sxs-lookup"><span data-stu-id="43eed-212">1 to 100,000</span></span> ||
|<span data-ttu-id="43eed-213">否</span><span class="sxs-lookup"><span data-stu-id="43eed-213">No</span></span>|<span data-ttu-id="43eed-214">MediaRelayRoutingLocationOverride</span><span class="sxs-lookup"><span data-stu-id="43eed-214">MediaRelayRoutingLocationOverride</span></span> |<span data-ttu-id="43eed-215">允許手動選取媒體路徑。</span><span class="sxs-lookup"><span data-stu-id="43eed-215">Allows selecting path for media manually.</span></span> <span data-ttu-id="43eed-216">[直接傳送] 會根據 SBC 的公用 IP，指派媒體路徑的資料中心。</span><span class="sxs-lookup"><span data-stu-id="43eed-216">Direct Routing assigns a datacenter for media path based on the public IP of the SBC.</span></span> <span data-ttu-id="43eed-217">我們總是選取最接近 SBC 資料中心的資料。</span><span class="sxs-lookup"><span data-stu-id="43eed-217">We always select closest to the SBC datacenter.</span></span> <span data-ttu-id="43eed-218">不過，在某些情況下，例如，美國範圍的公用 IP 可指派給位於歐洲的 SBC。</span><span class="sxs-lookup"><span data-stu-id="43eed-218">However, in some cases a public IP from, for example, a US range can be assigned to an SBC located in Europe.</span></span> <span data-ttu-id="43eed-219">在此情況下，我們會使用不是最佳的媒體路徑。</span><span class="sxs-lookup"><span data-stu-id="43eed-219">In this case, we will be using not optimal media path.</span></span> <span data-ttu-id="43eed-220">這個參數可讓您手動設定媒體流量的首選區域。</span><span class="sxs-lookup"><span data-stu-id="43eed-220">This parameter allows manually set the preferred region for media traffic.</span></span> <span data-ttu-id="43eed-221">只有在通話記錄清楚指出自動指派媒體路徑的資料中心無法指派最接近 SBC 資料中心的情況下，Microsoft 才建議您設定此參數。</span><span class="sxs-lookup"><span data-stu-id="43eed-221">Microsoft only recommends setting this parameter if the call logs clearly indicate that automatic assignment of the datacenter for media path does not assign the closest to the SBC datacenter.</span></span> |<span data-ttu-id="43eed-222">無</span><span class="sxs-lookup"><span data-stu-id="43eed-222">None</span></span>|<span data-ttu-id="43eed-223">ISO 格式的國家/地區代碼</span><span class="sxs-lookup"><span data-stu-id="43eed-223">Country codes in ISO format</span></span>||
|<span data-ttu-id="43eed-224">否</span><span class="sxs-lookup"><span data-stu-id="43eed-224">No</span></span>|<span data-ttu-id="43eed-225">後</span><span class="sxs-lookup"><span data-stu-id="43eed-225">Enabled</span></span>|<span data-ttu-id="43eed-226">用來針對撥出通話啟用這個 SBC。</span><span class="sxs-lookup"><span data-stu-id="43eed-226">Used to enable this SBC for outbound calls.</span></span> <span data-ttu-id="43eed-227">可用於在 SBC 更新期間或在維護期間暫時移除它。</span><span class="sxs-lookup"><span data-stu-id="43eed-227">Can be used to temporarily remove the SBC while it is being updated or during maintenance.</span></span> |<span data-ttu-id="43eed-228">虛假</span><span class="sxs-lookup"><span data-stu-id="43eed-228">False</span></span>|<span data-ttu-id="43eed-229">滿足</span><span class="sxs-lookup"><span data-stu-id="43eed-229">True</span></span><br/><span data-ttu-id="43eed-230">虛假</span><span class="sxs-lookup"><span data-stu-id="43eed-230">False</span></span>|<span data-ttu-id="43eed-231">Boolean</span><span class="sxs-lookup"><span data-stu-id="43eed-231">Boolean</span></span>|
 
## <a name="verify-the-sbc-connection"></a><span data-ttu-id="43eed-232">驗證 SBC 連接</span><span class="sxs-lookup"><span data-stu-id="43eed-232">Verify the SBC connection</span></span> 

<span data-ttu-id="43eed-233">若要驗證連接：</span><span class="sxs-lookup"><span data-stu-id="43eed-233">To verify the connection:</span></span> 
- <span data-ttu-id="43eed-234">檢查 SBC 是否在成對的 SBCs 清單中。</span><span class="sxs-lookup"><span data-stu-id="43eed-234">Check if the SBC is on the list of paired SBCs.</span></span> 
- <span data-ttu-id="43eed-235">驗證 SIP 選項。</span><span class="sxs-lookup"><span data-stu-id="43eed-235">Validate SIP Options.</span></span> 
 
### <a name="check-if-the-sbc-is-on-the-list-of-paired-sbcs"></a><span data-ttu-id="43eed-236">檢查 SBC 是否在成對的 SBCs 清單中</span><span class="sxs-lookup"><span data-stu-id="43eed-236">Check if the SBC is on the list of paired SBCs</span></span> 

<span data-ttu-id="43eed-237">在您連接 SBC 之後，請在遠端 PowerShell 會話中執行下列命令，以驗證 SBC 是否出現在成對的 SBCs 清單中：</span><span class="sxs-lookup"><span data-stu-id="43eed-237">After you connect the SBC, validate that the SBC is present in the list of paired SBCs by running the following command in a remote PowerShell session:</span></span> 

```PowerShell
Get-CsOnlinePSTNGateway -Identity sbc.contoso.com  
```

<span data-ttu-id="43eed-238">成對閘道應該會出現在清單中，如下列範例所示，且**Enabled**參數應該顯示**True**值。</span><span class="sxs-lookup"><span data-stu-id="43eed-238">The paired gateway should appear in the list as shown in the example below, and the **Enabled** parameter should display a value of **True**.</span></span> 


<span data-ttu-id="43eed-239">返回：</span><span class="sxs-lookup"><span data-stu-id="43eed-239">Which returns:</span></span>
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

### <a name="validate-sip-options-flow"></a><span data-ttu-id="43eed-240">驗證 SIP 選項流程</span><span class="sxs-lookup"><span data-stu-id="43eed-240">Validate SIP Options flow</span></span> 

<span data-ttu-id="43eed-241">若要使用外寄 SIP 選項驗證配對，請使用 SBC 管理介面，並確認 SBC 是否收到其外寄選項訊息的 200 OK 回應。</span><span class="sxs-lookup"><span data-stu-id="43eed-241">To validate the pairing using outgoing SIP Options, use the SBC management interface and confirm that the SBC receives 200 OK responses to its outgoing OPTIONS messages.</span></span>

<span data-ttu-id="43eed-242">當直接路由查看內送的選項時，它會開始將傳出的 SIP 選項訊息傳送到 [傳入選項] 訊息中的 [連絡人頭] 欄位中設定的 SBC FQDN。</span><span class="sxs-lookup"><span data-stu-id="43eed-242">When Direct Routing sees incoming OPTIONS, it will start sending outgoing SIP Options messages to the SBC FQDN configured in the Contact header field in the incoming OPTIONS message.</span></span> 

<span data-ttu-id="43eed-243">若要使用傳入的 SIP 選項驗證配對，請使用 SBC 管理介面，並查看 SBC 會傳送回復給來自直接路由的選項訊息，且其傳送的回應代碼為 200 OK。</span><span class="sxs-lookup"><span data-stu-id="43eed-243">To validate the pairing using incoming SIP Options, use the SBC management interface and see that the SBC sends a reply to the OPTIONS messages coming in from Direct Routing and that the response code it sends is 200 OK.</span></span>


## <a name="see-also"></a><span data-ttu-id="43eed-244">另請參閱</span><span class="sxs-lookup"><span data-stu-id="43eed-244">See also</span></span>

[<span data-ttu-id="43eed-245">規劃直接路由</span><span class="sxs-lookup"><span data-stu-id="43eed-245">Plan Direct Routing</span></span>](direct-routing-plan.md)

[<span data-ttu-id="43eed-246">設定直接路由</span><span class="sxs-lookup"><span data-stu-id="43eed-246">Configure Direct Routing</span></span>](direct-routing-configure.md)
