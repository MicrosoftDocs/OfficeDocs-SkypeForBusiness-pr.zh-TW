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
ms.openlocfilehash: 848e52859be3b2339e1e1968631c6d55fc7a8df79dc3a691fd47e9613f7f583d
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54344312"
---
# <a name="dial-pad-configuration"></a>撥號鍵台組

在 Teams 用戶端中，撥號鍵台可讓使用者存取公用交換電話網絡 (PSTN) 功能。 撥號鍵台可供擁有電話系統的使用者使用，但必須正確配置。 撥號鍵台必須符合下列準則才能顯示：

- 使用者已啟用電話系統 ( MCOEV") 授權
- 使用者有 Microsoft 通話方案或已啟用直接路由
- 使用者已啟用企業語音功能
- 使用者位於線上，而不是商務用 Skype內部部署
- 使用者已Teams通話策略

下列各節說明如何使用 PowerShell 檢查準則。 在大多數的情況下，您需要查看 Cmdlet 輸出Get-CsOnlineUser屬性。 範例假設$user為使用者的 UPN 或 sip 位址。

## <a name="user-has-an-enabled-phone-system-mcoev-license"></a>使用者已啟用電話系統 ( MCOEV") 授權

您必須確定為使用者指派的計畫顯示 **設為啟用的 CapabilityStatus** 屬性，且功能計畫設為 **MCOEV** (電話系統授權) 。 您可能會看到 MCOEV、MCOEV1 等。 只要功能計畫以 MCOEV 開頭，所有專案都可接受。

若要檢查屬性是否正確設定，請使用下列命令：

```
Get-CsOnlineUser -Identity $user|select AssignedPlan|fl
```

輸出看起來會像這樣。 您只需要檢查 **功能Status** 和 **功能計畫** 屬性：

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


## <a name="user-has-microsoft-calling-plan-or-is-enabled-for-direct-routing"></a>使用者有 Microsoft 通話方案 OR 已啟用直接路由

**如果使用者有 Microsoft 通話方案**，您必須確定 **CapabilityStatus** 屬性設定為啟用，且功能方案已設定為 **MCOPSTN。** 您可能會看到 MCOPSTN1、MCOPSTN2 等。 只要功能計畫以 MCOPSTN 開始，所有功能都可接受。

若要檢查屬性，請使用下列命令：

```
Get-CsOnlineUser -Identity $user|select AssignedPlan|fl
```

輸出看起來會像這樣。 您只需要檢查 **功能Status** 和 **功能計畫** 屬性：

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

**如果使用者已啟用直接** 路由，則必須為 OnlineVoiceRoutingPolicy 指派非 Null 值。 若要檢查屬性，請使用下列命令：
  
```
Get-CsOnlineUser -Identity $user|Select OnlineVoiceRoutingPolicy 
```

輸出應具有非 Null 值，例如：

```
OnlineVoiceRoutingPolicy
------------------------
Test_Policy
```

## <a name="user-has-enterprise-voice-enabled"></a>使用者已啟用企業語音功能

若要檢查使用者是否已啟用企業語音，請使用下列命令：

```
Get-CsOnlineUser -Identity $user|Select EnterpriseVoiceEnabled
```

輸出看起來應該會像這樣：

```
EnterpriseVoiceEnabled
----------------------
                  True

```
 
## <a name="user-is-homed-online-and-not-in-skype-for-business-on-premises"></a>使用者位於線上，而不是商務用 Skype內部部署

若要確保使用者位於線上，而非內部商務用 Skype，RegistrarPool 不得為 Null，HostingProvider 必須包含以 「sipfed.online」開頭的值。  若要檢查值，請使用下列命令：

```
Get-CsOnlineUser -Identity $user|Select RegistrarPool, HostingProvider
```

輸出應該類似：

```
RegistrarPool                 HostingProvider
-------------                 ---------------
sippoolbn10M02.infra.lync.com sipfed.online.lync.com
```

## <a name="user-has-teams-calling-policy-enabled"></a>使用者已Teams通話策略

使用者的有效 TeamsCallingPolicy 必須設定為 True AllowPrivateCalling。  根據預設，使用者會繼承全域原則，根據預設，全域原則的 AllowPrivateCallingPolicy 設定為 true。

若要取得使用者的 TeamsCallingPolicy，並檢查 AllowPrivateCalling 設定為 true，請使用下列命令：

```
if (($p=(get-csonlineuser -Identity $user).TeamsCallingPolicy) -eq $null) {Get-CsTeamsCallingPolicy -Identity global} else {get-csteamscallingpolicy -Identity $p}
```

輸出看起來應該會像這樣：

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

## <a name="additional-notes"></a>其他筆記

-   進行上述任何一個Teams之後，您可能需要重新開機用戶端。

-   如果您最近更新了上述任何準則，您可能需要等候數小時，用戶端才能收到新的設定。

-   如果您仍然看不到撥號鍵台，請用下列命令檢查是否有置備錯誤：

  ```
  Get-CsOnlineUser -Identity $user|Select McoValidationError
  ```

-    如果超過 24 小時，但您仍然看到問題，請聯絡支援人員。


