---
title: Teams撥號鍵台組
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: bjwhalen
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- NOCSH
description: 瞭解如何在用戶端中設定撥號鍵Teams，讓使用者能夠存取公用交換電話網絡 (PSTN) 功能。
ms.openlocfilehash: 44fcbb766cadaa4b31aa065fae80fdcd48c5453f
ms.sourcegitcommit: a94a267c421a78587b0dbbea5fa167aad2882e9b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/01/2020
ms.locfileid: "45012412"
---
# <a name="dial-pad-configuration"></a><span data-ttu-id="15a01-103">撥號鍵台組</span><span class="sxs-lookup"><span data-stu-id="15a01-103">Dial pad configuration</span></span>

<span data-ttu-id="15a01-104">在 Teams 用戶端中，撥號鍵台可讓使用者存取公用交換電話網絡 (PSTN) 功能。</span><span class="sxs-lookup"><span data-stu-id="15a01-104">In the Teams client, the dial pad enables users to access Public Switched Telephone Network (PSTN) functionality.</span></span> <span data-ttu-id="15a01-105">撥號鍵台可供擁有電話系統的使用者使用，但必須正確配置。</span><span class="sxs-lookup"><span data-stu-id="15a01-105">The dial pad is available for users with a Phone System license, provided they are configured properly.</span></span> <span data-ttu-id="15a01-106">撥號鍵台必須符合下列準則才能顯示：</span><span class="sxs-lookup"><span data-stu-id="15a01-106">The following criteria are all required for the dial pad to show:</span></span>

- <span data-ttu-id="15a01-107">使用者已啟用電話系統 ( MCOEV") 授權</span><span class="sxs-lookup"><span data-stu-id="15a01-107">User has an enabled Phone System (“MCOEV”) license</span></span>
- <span data-ttu-id="15a01-108">使用者有 Microsoft 通話方案或已啟用直接路由</span><span class="sxs-lookup"><span data-stu-id="15a01-108">User has Microsoft Calling Plan or is enabled for Direct Routing</span></span>
- <span data-ttu-id="15a01-109">使用者已啟用企業語音功能</span><span class="sxs-lookup"><span data-stu-id="15a01-109">User has Enterprise Voice enabled</span></span>
- <span data-ttu-id="15a01-110">使用者位於線上，而不是商務用 Skype內部部署</span><span class="sxs-lookup"><span data-stu-id="15a01-110">User is homed online and not in Skype for Business on premises</span></span>
- <span data-ttu-id="15a01-111">使用者已Teams通話策略</span><span class="sxs-lookup"><span data-stu-id="15a01-111">User has Teams Calling Policy enabled</span></span>

<span data-ttu-id="15a01-112">下列各節說明如何使用 PowerShell 檢查準則。</span><span class="sxs-lookup"><span data-stu-id="15a01-112">The following sections describe how to use PowerShell to check the criteria.</span></span> <span data-ttu-id="15a01-113">在大多數的情況下，您需要查看 Cmdlet 輸出Get-CsOnlineUser屬性。</span><span class="sxs-lookup"><span data-stu-id="15a01-113">In most cases, you need to look at various properties in the output of the Get-CsOnlineUser cmdlet.</span></span> <span data-ttu-id="15a01-114">範例假設$user為使用者的 UPN 或 sip 位址。</span><span class="sxs-lookup"><span data-stu-id="15a01-114">Examples assume $user is either the UPN or sip address of the user.</span></span>

## <a name="user-has-an-enabled-phone-system-mcoev-license"></a><span data-ttu-id="15a01-115">使用者已啟用電話系統 ( MCOEV") 授權</span><span class="sxs-lookup"><span data-stu-id="15a01-115">User has an enabled Phone System (“MCOEV”) license</span></span>

<span data-ttu-id="15a01-116">您必須確定為使用者指派的計畫顯示 **設為啟用的 CapabilityStatus** 屬性，且功能計畫設為 **MCOEV** (電話系統授權) 。</span><span class="sxs-lookup"><span data-stu-id="15a01-116">You must ensure that the assigned plan for the user shows the **CapabilityStatus attribute set to Enabled** and the **Capability Plan set to MCOEV** (Phone System license).</span></span> <span data-ttu-id="15a01-117">您可能會看到 MCOEV、MCOEV1 等。</span><span class="sxs-lookup"><span data-stu-id="15a01-117">You might see MCOEV, MCOEV1, and so on.</span></span> <span data-ttu-id="15a01-118">只要功能計畫以 MCOEV 開頭，所有專案都可接受。</span><span class="sxs-lookup"><span data-stu-id="15a01-118">All are acceptable--as long as the Capability Plan starts with MCOEV.</span></span>

<span data-ttu-id="15a01-119">若要檢查屬性是否正確設定，請使用下列命令：</span><span class="sxs-lookup"><span data-stu-id="15a01-119">To check that the attributes are set correctly, use the following command:</span></span>

```
Get-CsOnlineUser -Identity $user|select AssignedPlan|fl
```

<span data-ttu-id="15a01-120">輸出看起來會像這樣。</span><span class="sxs-lookup"><span data-stu-id="15a01-120">The output will look like the following.</span></span> <span data-ttu-id="15a01-121">您只需要檢查 **功能Status** 和 **功能計畫** 屬性：</span><span class="sxs-lookup"><span data-stu-id="15a01-121">You only need to check the **CapabilityStatus** and the **Capability Plan** attributes:</span></span>

```
<Plan SubscribedPlanId="2f9eda01-4630-4a5c-bdb3-cf195f22d240"  
   ServiceInstance="MicrosoftCommunicationsOnline/NOAM-0M-DMT" 
   CapabilityStatus="Enabled"  
   AssignedTimestamp="2020-04-21T18:31:13Z" 
   ServicePlanId="4828c8ec-dc2e-4779-b502-87ac9ce28ab7" 
   xmlns="http://schemas.microsoft.com/online/directoryservices/change/2008/11"> 
  <Capability> 
     <Capability Plan="MCOEV" 
     xmlns="http://schemas.microsoft.com/online/MCO/2009/01"/> 
  </Capability>
</Plan>
```


## <a name="user-has-microsoft-calling-plan-or-is-enabled-for-direct-routing"></a><span data-ttu-id="15a01-122">使用者已啟用 Microsoft 通話方案或已啟用直接路由</span><span class="sxs-lookup"><span data-stu-id="15a01-122">User has Microsoft Calling Plan OR is enabled for Direct Routing</span></span>

<span data-ttu-id="15a01-123">**如果使用者有 Microsoft 通話方案**，您必須確定 **CapabilityStatus** 屬性設定為啟用，且功能方案已設定為 **MCOPSTN。**</span><span class="sxs-lookup"><span data-stu-id="15a01-123">**If the user has Microsoft Calling Plan**, you must ensure that the **CapabilityStatus attribute is set to Enabled**, and that the **Capability Plan is set to MCOPSTN**.</span></span> <span data-ttu-id="15a01-124">您可能會看到 MCOPSTN1、MCOPSTN2 等。</span><span class="sxs-lookup"><span data-stu-id="15a01-124">You might see MCOPSTN1, MCOPSTN2, and so on.</span></span> <span data-ttu-id="15a01-125">只要功能計畫以 MCOPSTN 開頭，所有專案都可接受。</span><span class="sxs-lookup"><span data-stu-id="15a01-125">All are acceptable--as long as the Capability Plan starts with MCOPSTN.</span></span>

<span data-ttu-id="15a01-126">若要檢查屬性，請使用下列命令：</span><span class="sxs-lookup"><span data-stu-id="15a01-126">To check the attributes, use the following command:</span></span>

```
Get-CsOnlineUser -Identity $user|select AssignedPlan|fl
```

<span data-ttu-id="15a01-127">輸出看起來會像這樣。</span><span class="sxs-lookup"><span data-stu-id="15a01-127">The output will look like the following.</span></span> <span data-ttu-id="15a01-128">您只需要檢查 **功能Status** 和 **功能計畫** 屬性：</span><span class="sxs-lookup"><span data-stu-id="15a01-128">You only need to check the **CapabilityStatus** and the **Capability Plan** attributes:</span></span>

```  
<Plan SubscribedPlanId="71d1258e-a4e6-443f-884e-0f3d6f644bb1" 
ServiceInstance="MicrosoftCommunicationsOnline/NOAM-0M-DMT" 
CapabilityStatus="Enabled"    
AssignedTimestamp="2018-09-18T18:41:42Z" 
ServicePlanId="5a10155d-f5c1-411a-a8ec-e99aae125390" 
xmlns="http://schemas.microsoft.com/online/directoryservices/change/2008/11">
 <Capability>
    <Capability Plan="MCOPSTN2" 
    xmlns="http://schemas.microsoft.com/online/MCO/2009/01" />
 </Capability>
</Plan>
  ```

<span data-ttu-id="15a01-129">**如果使用者已啟用直接** 路由，則必須為 OnlineVoiceRoutingPolicy 指派非 Null 值。</span><span class="sxs-lookup"><span data-stu-id="15a01-129">**If the user is enabled for Direct Routing**, the user must be assigned a non-null value for OnlineVoiceRoutingPolicy.</span></span> <span data-ttu-id="15a01-130">若要檢查屬性，請使用下列命令：</span><span class="sxs-lookup"><span data-stu-id="15a01-130">To check the attribute, use the following command:</span></span>
  
```
Get-CsOnlineUser -Identity $user|Select OnlineVoiceRoutingPolicy 
```

<span data-ttu-id="15a01-131">輸出應具有非 Null 值，例如：</span><span class="sxs-lookup"><span data-stu-id="15a01-131">The output should have a non-null value, for example:</span></span>

```
OnlineVoiceRoutingPolicy
------------------------
Test_Policy
```

## <a name="user-has-enterprise-voice-enabled"></a><span data-ttu-id="15a01-132">使用者已啟用企業語音功能</span><span class="sxs-lookup"><span data-stu-id="15a01-132">User has Enterprise Voice enabled</span></span>

<span data-ttu-id="15a01-133">若要檢查使用者是否已啟用企業語音，請使用下列命令：</span><span class="sxs-lookup"><span data-stu-id="15a01-133">To check if the user has Enterprise Voice enabled, use the following command:</span></span>

```
Get-CsOnlineUser -Identity $user|Select EnterpriseVoiceEnabled
```

<span data-ttu-id="15a01-134">輸出看起來應該會像這樣：</span><span class="sxs-lookup"><span data-stu-id="15a01-134">The output should look like:</span></span>

```
EnterpriseVoiceEnabled
----------------------
                  True

```
 
## <a name="user-is-homed-online-and-not-in-skype-for-business-on-premises"></a><span data-ttu-id="15a01-135">使用者位於線上，而不是商務用 Skype內部部署</span><span class="sxs-lookup"><span data-stu-id="15a01-135">User is homed online and not in Skype for Business on premises</span></span>

<span data-ttu-id="15a01-136">若要確保使用者位於線上，而非內部商務用 Skype，RegistrarPool 不得為 Null，HostingProvider 必須包含以「sipfed.online」開頭的值。</span><span class="sxs-lookup"><span data-stu-id="15a01-136">To ensure the user is homed online and not in Skype for Business on premises, the RegistrarPool must not be null and the HostingProvider must contain a value that starts with “sipfed.online.”</span></span>  <span data-ttu-id="15a01-137">若要檢查值，請使用下列命令：</span><span class="sxs-lookup"><span data-stu-id="15a01-137">To check the values, use the following command:</span></span>

```
Get-CsOnlineUser -Identity $user|Select RegistrarPool, HostingProvider
```

<span data-ttu-id="15a01-138">輸出應該類似：</span><span class="sxs-lookup"><span data-stu-id="15a01-138">The output should be similar to:</span></span>

```
RegistrarPool                 HostingProvider
-------------                 ---------------
sippoolbn10M02.infra.lync.com sipfed.online.lync.com
```

## <a name="user-has-teams-calling-policy-enabled"></a><span data-ttu-id="15a01-139">使用者已Teams通話策略</span><span class="sxs-lookup"><span data-stu-id="15a01-139">User has Teams Calling Policy enabled</span></span>

<span data-ttu-id="15a01-140">使用者的有效 TeamsCallingPolicy 必須設定為 True AllowPrivateCalling。</span><span class="sxs-lookup"><span data-stu-id="15a01-140">The user’s effective TeamsCallingPolicy must have AllowPrivateCalling set to true.</span></span>  <span data-ttu-id="15a01-141">根據預設，使用者會繼承全域原則，根據預設，全域原則的 AllowPrivateCallingPolicy 設定為 true。</span><span class="sxs-lookup"><span data-stu-id="15a01-141">By default, users inherit the global policy, which has AllowPrivateCallingPolicy set to true by default.</span></span>

<span data-ttu-id="15a01-142">若要取得使用者的 TeamsCallingPolicy，並檢查 AllowPrivateCalling 設定為 true，請使用下列命令：</span><span class="sxs-lookup"><span data-stu-id="15a01-142">To get the TeamsCallingPolicy for a user and to check that AllowPrivateCalling is set to true, use the following command:</span></span>

```
if (($p=(get-csonlineuser -Identity $user).TeamsCallingPolicy) -eq $null) {Get-CsTeamsCallingPolicy -Identity global} else {get-csteamscallingpolicy -Identity $p}
```

<span data-ttu-id="15a01-143">輸出看起來應該會像這樣：</span><span class="sxs-lookup"><span data-stu-id="15a01-143">The output should look like:</span></span>

```
Identity                   : Global
Description                :
AllowPrivateCalling        : True
AllowWebPSTNCalling        : True
AllowVoicemail             : UserOverride
AllowCallGroups            : True
AllowDelegation            : True
AllowCallForwardingToUser  : True
AllowCallForwardingToPhone : True
PreventTollBypass          : False
BusyOnBusyEnabledType      : Disabled
MusicOnHoldEnabledType     : Enabled
``` 

## <a name="additional-notes"></a><span data-ttu-id="15a01-144">其他筆記</span><span class="sxs-lookup"><span data-stu-id="15a01-144">Additional notes</span></span>

-   <span data-ttu-id="15a01-145">進行上述任何一個Teams之後，您可能需要重新開機用戶端。</span><span class="sxs-lookup"><span data-stu-id="15a01-145">You may need to restart the Teams client after making any of these configuration changes.</span></span>

-   <span data-ttu-id="15a01-146">如果您最近更新了上述任何準則，您可能需要等候數小時，用戶端才能收到新的設定。</span><span class="sxs-lookup"><span data-stu-id="15a01-146">If you recently updated any of the above criteria, you may need to wait a few hours for the client to receive the new settings.</span></span>

-   <span data-ttu-id="15a01-147">如果您仍然看不到撥號鍵台，請用下列命令檢查是否有置備錯誤：</span><span class="sxs-lookup"><span data-stu-id="15a01-147">If you still don’t see the dial pad, check if there is a provisioning error by using the following command:</span></span>

  ```
  Get-CsOnlineUser -Identity $user|Select McoValidationError
  ```

-    <span data-ttu-id="15a01-148">如果超過 24 小時，但您仍然看到問題，請聯絡支援人員。</span><span class="sxs-lookup"><span data-stu-id="15a01-148">If it has been more than 24 hours and you are still seeing problems, contact Support.</span></span>


