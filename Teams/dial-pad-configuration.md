---
title: 團隊撥號鍵台設定
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
description: 瞭解如何在團隊用戶端設定撥號鍵台，讓使用者可以存取公用的交換式電話網絡（PSTN）功能。
ms.openlocfilehash: 44fcbb766cadaa4b31aa065fae80fdcd48c5453f
ms.sourcegitcommit: a94a267c421a78587b0dbbea5fa167aad2882e9b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/01/2020
ms.locfileid: "45012412"
---
# <a name="dial-pad-configuration"></a><span data-ttu-id="94415-103">撥號鍵台設定</span><span class="sxs-lookup"><span data-stu-id="94415-103">Dial pad configuration</span></span>

<span data-ttu-id="94415-104">在 [團隊用戶端] 中，使用撥號鍵台可以讓使用者存取公用的交換式電話網絡（PSTN）功能。</span><span class="sxs-lookup"><span data-stu-id="94415-104">In the Teams client, the dial pad enables users to access Public Switched Telephone Network (PSTN) functionality.</span></span> <span data-ttu-id="94415-105">如果使用者設定正確，就可以使用撥號鍵台來供具備電話系統授權的使用者使用。</span><span class="sxs-lookup"><span data-stu-id="94415-105">The dial pad is available for users with a Phone System license, provided they are configured properly.</span></span> <span data-ttu-id="94415-106">若要顯示撥號鍵台，必須具備下列準則：</span><span class="sxs-lookup"><span data-stu-id="94415-106">The following criteria are all required for the dial pad to show:</span></span>

- <span data-ttu-id="94415-107">使用者有已啟用的電話系統（"MCOEV"）授權</span><span class="sxs-lookup"><span data-stu-id="94415-107">User has an enabled Phone System (“MCOEV”) license</span></span>
- <span data-ttu-id="94415-108">使用者擁有 Microsoft 通話方案，或已啟用直接路由</span><span class="sxs-lookup"><span data-stu-id="94415-108">User has Microsoft Calling Plan or is enabled for Direct Routing</span></span>
- <span data-ttu-id="94415-109">使用者已啟用企業語音</span><span class="sxs-lookup"><span data-stu-id="94415-109">User has Enterprise Voice enabled</span></span>
- <span data-ttu-id="94415-110">使用者是在線上且不在商務用 Skype 內部部署中</span><span class="sxs-lookup"><span data-stu-id="94415-110">User is homed online and not in Skype for Business on premises</span></span>
- <span data-ttu-id="94415-111">使用者已啟用團隊通話原則</span><span class="sxs-lookup"><span data-stu-id="94415-111">User has Teams Calling Policy enabled</span></span>

<span data-ttu-id="94415-112">下列各節說明如何使用 PowerShell 來檢查準則。</span><span class="sxs-lookup"><span data-stu-id="94415-112">The following sections describe how to use PowerShell to check the criteria.</span></span> <span data-ttu-id="94415-113">在大多數情況下，您必須在 CsOnlineUser Cmdlet 的輸出中查看各種屬性。</span><span class="sxs-lookup"><span data-stu-id="94415-113">In most cases, you need to look at various properties in the output of the Get-CsOnlineUser cmdlet.</span></span> <span data-ttu-id="94415-114">範例假設 $user 是使用者的 UPN 或 sip 位址。</span><span class="sxs-lookup"><span data-stu-id="94415-114">Examples assume $user is either the UPN or sip address of the user.</span></span>

## <a name="user-has-an-enabled-phone-system-mcoev-license"></a><span data-ttu-id="94415-115">使用者有已啟用的電話系統（"MCOEV"）授權</span><span class="sxs-lookup"><span data-stu-id="94415-115">User has an enabled Phone System (“MCOEV”) license</span></span>

<span data-ttu-id="94415-116">您必須確保指派給使用者的方案顯示**已將 CapabilityStatus 屬性設定為 [已啟用**]，而**功能方案則設定為 MCOEV** （[電話系統授權]）。</span><span class="sxs-lookup"><span data-stu-id="94415-116">You must ensure that the assigned plan for the user shows the **CapabilityStatus attribute set to Enabled** and the **Capability Plan set to MCOEV** (Phone System license).</span></span> <span data-ttu-id="94415-117">您可能會看到 [MCOEV]、[MCOEV1] 等等。</span><span class="sxs-lookup"><span data-stu-id="94415-117">You might see MCOEV, MCOEV1, and so on.</span></span> <span data-ttu-id="94415-118">全部都可接受-只要功能計畫以 MCOEV 開始。</span><span class="sxs-lookup"><span data-stu-id="94415-118">All are acceptable--as long as the Capability Plan starts with MCOEV.</span></span>

<span data-ttu-id="94415-119">若要檢查屬性是否設定正確，請使用下列命令：</span><span class="sxs-lookup"><span data-stu-id="94415-119">To check that the attributes are set correctly, use the following command:</span></span>

```
Get-CsOnlineUser -Identity $user|select AssignedPlan|fl
```

<span data-ttu-id="94415-120">輸出看起來會如下所示。</span><span class="sxs-lookup"><span data-stu-id="94415-120">The output will look like the following.</span></span> <span data-ttu-id="94415-121">您只需要檢查**CapabilityStatus**及**功能方案**的屬性：</span><span class="sxs-lookup"><span data-stu-id="94415-121">You only need to check the **CapabilityStatus** and the **Capability Plan** attributes:</span></span>

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


## <a name="user-has-microsoft-calling-plan-or-is-enabled-for-direct-routing"></a><span data-ttu-id="94415-122">使用者擁有 Microsoft 通話方案，或已啟用直接路由</span><span class="sxs-lookup"><span data-stu-id="94415-122">User has Microsoft Calling Plan OR is enabled for Direct Routing</span></span>

<span data-ttu-id="94415-123">**如果使用者有 Microsoft 通話方案**，您必須確保**CapabilityStatus 屬性已設定為 [啟用**]，且**功能方案已設定為 MCOPSTN**。</span><span class="sxs-lookup"><span data-stu-id="94415-123">**If the user has Microsoft Calling Plan**, you must ensure that the **CapabilityStatus attribute is set to Enabled**, and that the **Capability Plan is set to MCOPSTN**.</span></span> <span data-ttu-id="94415-124">您可能會看到 [MCOPSTN1]、[MCOPSTN2] 等等。</span><span class="sxs-lookup"><span data-stu-id="94415-124">You might see MCOPSTN1, MCOPSTN2, and so on.</span></span> <span data-ttu-id="94415-125">全部都可接受-只要功能計畫以 MCOPSTN 開始。</span><span class="sxs-lookup"><span data-stu-id="94415-125">All are acceptable--as long as the Capability Plan starts with MCOPSTN.</span></span>

<span data-ttu-id="94415-126">若要檢查屬性，請使用下列命令：</span><span class="sxs-lookup"><span data-stu-id="94415-126">To check the attributes, use the following command:</span></span>

```
Get-CsOnlineUser -Identity $user|select AssignedPlan|fl
```

<span data-ttu-id="94415-127">輸出看起來會如下所示。</span><span class="sxs-lookup"><span data-stu-id="94415-127">The output will look like the following.</span></span> <span data-ttu-id="94415-128">您只需要檢查**CapabilityStatus**及**功能方案**的屬性：</span><span class="sxs-lookup"><span data-stu-id="94415-128">You only need to check the **CapabilityStatus** and the **Capability Plan** attributes:</span></span>

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

<span data-ttu-id="94415-129">**如果使用者已啟用直接路由**，則使用者必須為 OnlineVoiceRoutingPolicy 指派非 null 值。</span><span class="sxs-lookup"><span data-stu-id="94415-129">**If the user is enabled for Direct Routing**, the user must be assigned a non-null value for OnlineVoiceRoutingPolicy.</span></span> <span data-ttu-id="94415-130">若要檢查屬性，請使用下列命令：</span><span class="sxs-lookup"><span data-stu-id="94415-130">To check the attribute, use the following command:</span></span>
  
```
Get-CsOnlineUser -Identity $user|Select OnlineVoiceRoutingPolicy 
```

<span data-ttu-id="94415-131">輸出應具有非 null 值，例如：</span><span class="sxs-lookup"><span data-stu-id="94415-131">The output should have a non-null value, for example:</span></span>

```
OnlineVoiceRoutingPolicy
------------------------
Test_Policy
```

## <a name="user-has-enterprise-voice-enabled"></a><span data-ttu-id="94415-132">使用者已啟用企業語音</span><span class="sxs-lookup"><span data-stu-id="94415-132">User has Enterprise Voice enabled</span></span>

<span data-ttu-id="94415-133">若要檢查使用者是否已啟用企業語音，請使用下列命令：</span><span class="sxs-lookup"><span data-stu-id="94415-133">To check if the user has Enterprise Voice enabled, use the following command:</span></span>

```
Get-CsOnlineUser -Identity $user|Select EnterpriseVoiceEnabled
```

<span data-ttu-id="94415-134">輸出應如下所示：</span><span class="sxs-lookup"><span data-stu-id="94415-134">The output should look like:</span></span>

```
EnterpriseVoiceEnabled
----------------------
                  True

```
 
## <a name="user-is-homed-online-and-not-in-skype-for-business-on-premises"></a><span data-ttu-id="94415-135">使用者是在線上且不在商務用 Skype 內部部署中</span><span class="sxs-lookup"><span data-stu-id="94415-135">User is homed online and not in Skype for Business on premises</span></span>

<span data-ttu-id="94415-136">若要確保使用者在線上且不是在內部部署商務用 Skype 中，RegistrarPool 不得為 null，且 HostingProvider 必須包含以 "sipfed." 開頭的值。</span><span class="sxs-lookup"><span data-stu-id="94415-136">To ensure the user is homed online and not in Skype for Business on premises, the RegistrarPool must not be null and the HostingProvider must contain a value that starts with “sipfed.online.”</span></span>  <span data-ttu-id="94415-137">若要檢查值，請使用下列命令：</span><span class="sxs-lookup"><span data-stu-id="94415-137">To check the values, use the following command:</span></span>

```
Get-CsOnlineUser -Identity $user|Select RegistrarPool, HostingProvider
```

<span data-ttu-id="94415-138">輸出應該類似以下所示：</span><span class="sxs-lookup"><span data-stu-id="94415-138">The output should be similar to:</span></span>

```
RegistrarPool                 HostingProvider
-------------                 ---------------
sippoolbn10M02.infra.lync.com sipfed.online.lync.com
```

## <a name="user-has-teams-calling-policy-enabled"></a><span data-ttu-id="94415-139">使用者已啟用團隊通話原則</span><span class="sxs-lookup"><span data-stu-id="94415-139">User has Teams Calling Policy enabled</span></span>

<span data-ttu-id="94415-140">使用者的 [有效 TeamsCallingPolicy] 必須已將 AllowPrivateCalling 設定為 true。</span><span class="sxs-lookup"><span data-stu-id="94415-140">The user’s effective TeamsCallingPolicy must have AllowPrivateCalling set to true.</span></span>  <span data-ttu-id="94415-141">根據預設，使用者會繼承全域原則，預設會將 AllowPrivateCallingPolicy 設定為 true。</span><span class="sxs-lookup"><span data-stu-id="94415-141">By default, users inherit the global policy, which has AllowPrivateCallingPolicy set to true by default.</span></span>

<span data-ttu-id="94415-142">若要取得使用者的 TeamsCallingPolicy，並檢查 AllowPrivateCalling 是否設定為 true，請使用下列命令：</span><span class="sxs-lookup"><span data-stu-id="94415-142">To get the TeamsCallingPolicy for a user and to check that AllowPrivateCalling is set to true, use the following command:</span></span>

```
if (($p=(get-csonlineuser -Identity $user).TeamsCallingPolicy) -eq $null) {Get-CsTeamsCallingPolicy -Identity global} else {get-csteamscallingpolicy -Identity $p}
```

<span data-ttu-id="94415-143">輸出應如下所示：</span><span class="sxs-lookup"><span data-stu-id="94415-143">The output should look like:</span></span>

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

## <a name="additional-notes"></a><span data-ttu-id="94415-144">其他筆記</span><span class="sxs-lookup"><span data-stu-id="94415-144">Additional notes</span></span>

-   <span data-ttu-id="94415-145">在變更任何設定之後，您可能需要重新開機團隊用戶端。</span><span class="sxs-lookup"><span data-stu-id="94415-145">You may need to restart the Teams client after making any of these configuration changes.</span></span>

-   <span data-ttu-id="94415-146">如果您最近更新了上述任何一個準則，您可能需要等候幾個小時，用戶端才能收到新設定。</span><span class="sxs-lookup"><span data-stu-id="94415-146">If you recently updated any of the above criteria, you may need to wait a few hours for the client to receive the new settings.</span></span>

-   <span data-ttu-id="94415-147">如果您仍然看不到撥號鍵台，請使用下列命令檢查是否有提供錯誤：</span><span class="sxs-lookup"><span data-stu-id="94415-147">If you still don’t see the dial pad, check if there is a provisioning error by using the following command:</span></span>

  ```
  Get-CsOnlineUser -Identity $user|Select McoValidationError
  ```

-    <span data-ttu-id="94415-148">如果有超過24小時的時間，但仍有問題，請聯絡支援人員。</span><span class="sxs-lookup"><span data-stu-id="94415-148">If it has been more than 24 hours and you are still seeing problems, contact Support.</span></span>


