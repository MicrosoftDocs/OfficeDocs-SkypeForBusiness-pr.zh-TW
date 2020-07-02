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
# <a name="dial-pad-configuration"></a>撥號鍵台設定

在 [團隊用戶端] 中，使用撥號鍵台可以讓使用者存取公用的交換式電話網絡（PSTN）功能。 如果使用者設定正確，就可以使用撥號鍵台來供具備電話系統授權的使用者使用。 若要顯示撥號鍵台，必須具備下列準則：

- 使用者有已啟用的電話系統（"MCOEV"）授權
- 使用者擁有 Microsoft 通話方案，或已啟用直接路由
- 使用者已啟用企業語音
- 使用者是在線上且不在商務用 Skype 內部部署中
- 使用者已啟用團隊通話原則

下列各節說明如何使用 PowerShell 來檢查準則。 在大多數情況下，您必須在 CsOnlineUser Cmdlet 的輸出中查看各種屬性。 範例假設 $user 是使用者的 UPN 或 sip 位址。

## <a name="user-has-an-enabled-phone-system-mcoev-license"></a>使用者有已啟用的電話系統（"MCOEV"）授權

您必須確保指派給使用者的方案顯示**已將 CapabilityStatus 屬性設定為 [已啟用**]，而**功能方案則設定為 MCOEV** （[電話系統授權]）。 您可能會看到 [MCOEV]、[MCOEV1] 等等。 全部都可接受-只要功能計畫以 MCOEV 開始。

若要檢查屬性是否設定正確，請使用下列命令：

```
Get-CsOnlineUser -Identity $user|select AssignedPlan|fl
```

輸出看起來會如下所示。 您只需要檢查**CapabilityStatus**及**功能方案**的屬性：

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


## <a name="user-has-microsoft-calling-plan-or-is-enabled-for-direct-routing"></a>使用者擁有 Microsoft 通話方案，或已啟用直接路由

**如果使用者有 Microsoft 通話方案**，您必須確保**CapabilityStatus 屬性已設定為 [啟用**]，且**功能方案已設定為 MCOPSTN**。 您可能會看到 [MCOPSTN1]、[MCOPSTN2] 等等。 全部都可接受-只要功能計畫以 MCOPSTN 開始。

若要檢查屬性，請使用下列命令：

```
Get-CsOnlineUser -Identity $user|select AssignedPlan|fl
```

輸出看起來會如下所示。 您只需要檢查**CapabilityStatus**及**功能方案**的屬性：

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

**如果使用者已啟用直接路由**，則使用者必須為 OnlineVoiceRoutingPolicy 指派非 null 值。 若要檢查屬性，請使用下列命令：
  
```
Get-CsOnlineUser -Identity $user|Select OnlineVoiceRoutingPolicy 
```

輸出應具有非 null 值，例如：

```
OnlineVoiceRoutingPolicy
------------------------
Test_Policy
```

## <a name="user-has-enterprise-voice-enabled"></a>使用者已啟用企業語音

若要檢查使用者是否已啟用企業語音，請使用下列命令：

```
Get-CsOnlineUser -Identity $user|Select EnterpriseVoiceEnabled
```

輸出應如下所示：

```
EnterpriseVoiceEnabled
----------------------
                  True

```
 
## <a name="user-is-homed-online-and-not-in-skype-for-business-on-premises"></a>使用者是在線上且不在商務用 Skype 內部部署中

若要確保使用者在線上且不是在內部部署商務用 Skype 中，RegistrarPool 不得為 null，且 HostingProvider 必須包含以 "sipfed." 開頭的值。  若要檢查值，請使用下列命令：

```
Get-CsOnlineUser -Identity $user|Select RegistrarPool, HostingProvider
```

輸出應該類似以下所示：

```
RegistrarPool                 HostingProvider
-------------                 ---------------
sippoolbn10M02.infra.lync.com sipfed.online.lync.com
```

## <a name="user-has-teams-calling-policy-enabled"></a>使用者已啟用團隊通話原則

使用者的 [有效 TeamsCallingPolicy] 必須已將 AllowPrivateCalling 設定為 true。  根據預設，使用者會繼承全域原則，預設會將 AllowPrivateCallingPolicy 設定為 true。

若要取得使用者的 TeamsCallingPolicy，並檢查 AllowPrivateCalling 是否設定為 true，請使用下列命令：

```
if (($p=(get-csonlineuser -Identity $user).TeamsCallingPolicy) -eq $null) {Get-CsTeamsCallingPolicy -Identity global} else {get-csteamscallingpolicy -Identity $p}
```

輸出應如下所示：

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

-   在變更任何設定之後，您可能需要重新開機團隊用戶端。

-   如果您最近更新了上述任何一個準則，您可能需要等候幾個小時，用戶端才能收到新設定。

-   如果您仍然看不到撥號鍵台，請使用下列命令檢查是否有提供錯誤：

  ```
  Get-CsOnlineUser -Identity $user|Select McoValidationError
  ```

-    如果有超過24小時的時間，但仍有問題，請聯絡支援人員。


