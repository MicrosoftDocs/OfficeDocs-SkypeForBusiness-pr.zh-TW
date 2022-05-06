---
title: Teams撥號鍵台設定
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
ms.localizationpriority: medium
f1.keywords:
- NOCSH
description: 瞭解如何在Teams用戶端中設定撥號鍵台，讓使用者可以存取公用交換電話網路 (PSTN) 功能。
ms.openlocfilehash: 7fc2622ce0fda97ce608e13d67ff786431a30aa5
ms.sourcegitcommit: 140c34f20f9cd48d7180ff03fddd60f5d1d3459f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/06/2022
ms.locfileid: "65248925"
---
# <a name="dial-pad-configuration"></a>撥號鍵台設定

在Teams用戶端中，撥號鍵台可讓使用者存取公用交換電話網路 (PSTN) 功能。 只要使用者已正確設定電話系統授權，即可使用撥號鍵台。 要顯示撥號鍵台，必須符合下列準則：

- 使用者已啟用電話系統 (「MCOEV」) 授權
- 使用者已啟用 Microsoft 通話方案、電信業者連線或已啟用直接路由
- 使用者已啟用企業語音
- 使用者在線上且不在內部部署商務用 Skype
- 使用者已啟用Teams通話原則

下列各節說明如何使用 PowerShell 來檢查準則。 在大多數的情況下，您需要查看Get-CsOnlineUser Cmdlet 輸出中的各種屬性。 範例假設$user是使用者的 UPN 或 sip 位址。

## <a name="user-has-an-enabled-phone-system-mcoev-license"></a>使用者已啟用電話系統 (「MCOEV」) 授權

請確定使用者的指派方案顯示已 **啟用的 CapabilityStatus 屬性，** 以及已 **設定為 MCOEV** 的功能 (電話系統授權) 。 您可能會看到 MCOEV、MCOEV1 等等。 只要功能是從 MCOEV 開始，就能接受。

若要檢查屬性是否正確設定，請使用下列命令：

```
(Get-CsOnlineUser -Identity $user).AssignedPlan
```

輸出看起來會如下所示。 您只需要檢查 **CapabilityStatus** 和 **功能** 屬性：

```
AssignedTimestamp   Capability      CapabilityStatus ServiceInstance                          ServicePlanId
-----------------   ----------      ---------------- ---------------                          -------------
07-02-2020 12:28:48 MCOEV           Enabled          MicrosoftCommunicationsOnline/NOAM-4A-S7 4828c8ec-dc2e-4779-b502-…
07-02-2020 12:28:48 Teams           Enabled          TeamspaceAPI/NA001                       57ff2da0-773e-42df-b2af-…
```


## <a name="user-has-microsoft-calling-plan-operator-connect-or-is-enabled-for-direct-routing"></a>使用者已啟用 Microsoft 通話方案，電信業者連線 OR 已啟用直接路由

**如果使用者有 Microsoft 通話方案**，請確定 **CapabilityStatus 屬性已設定為 [已啟用**]，且功能 **已設定為 MCOPSTN**。 您可能會看到 MCOPSTN1、MCOPSTN2 等。 只要功能從 MCOPSTN 開始，就能接受所有功能。

若要檢查屬性，請使用下列命令：

```
(Get-CsOnlineUser -Identity $user).AssignedPlan
```

輸出看起來會如下所示。 您只需要檢查 **CapabilityStatus** 和 **功能** 屬性：

```  
AssignedTimestamp   Capability      CapabilityStatus ServiceInstance                          ServicePlanId
-----------------   ----------      ---------------- ---------------                          -------------
07-02-2020 12:28:48 MCOEV           Enabled          MicrosoftCommunicationsOnline/NOAM-4A-S7 4828c8ec-dc2e-4779-b502-…
07-02-2020 12:28:48 MCOPSTN2        Enabled          MicrosoftCommunicationsOnline/NOAM-4A-S7 5a10155d-f5c1-411a-a8ec-…
07-02-2020 12:28:48 Teams           Enabled          TeamspaceAPI/NA001                       57ff2da0-773e-42df-b2af-…
```
**如果使用者已啟用 電信業者連線**，則使用者必須具有 TeamsCarrierEmergencyCallRoutingPolicy 的非 Null 值。 若要檢查屬性，請使用下列命令：
  
```
Get-CsOnlineUser -Identity $user|Select TeamsCarrierEmergencyCallRoutingPolicy
```

輸出應該會有非 Null 的值，例如：

```
TeamsCarrierEmergencyCallRoutingPolicy
--------------------------------------
Synergy_98d1a5cb-d3e6-4306-885e-69a95f2da5c3
```

**如果使用者已啟用直接路由**，則必須為使用者指派 OnlineVoiceRoutingPolicy 的非 Null 值。 若要檢查屬性，請使用下列命令：
  
```
Get-CsOnlineUser -Identity $user|Select OnlineVoiceRoutingPolicy 
```

輸出應該會有非 Null 的值，例如：

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

輸出看起來應該像這樣：

```
EnterpriseVoiceEnabled
----------------------
                  True

```
 
## <a name="user-is-homed-online-and-not-in-skype-for-business-on-premises"></a>使用者在線上且不在內部部署商務用 Skype

為確保使用者在線上且不在內部部署商務用 Skype，註冊機構Pool 不能為 Null，且 HostingProvider 必須包含以「sipfed.online」開頭的值。  若要檢查值，請使用下列命令：

```
Get-CsOnlineUser -Identity $user|Select RegistrarPool, HostingProvider
```

輸出結果應該類似：

```
RegistrarPool                 HostingProvider
-------------                 ---------------
sippoolbn10M02.infra.lync.com sipfed.online.lync.com
```

## <a name="user-has-teams-calling-policy-enabled"></a>使用者已啟用Teams通話原則

使用者的有效 TeamsCallingPolicy 必須將 AllowPrivateCalling 設為 True。  根據預設，使用者會繼承全域原則，其中 AllowPrivateCallingPolicy 預設為 True。

若要取得使用者的 TeamsCallingPolicy，並檢查 AllowPrivateCalling 是否設為 True，請使用下列命令：

```
if (($p=Get-CsUserPolicyAssignment -Identity $user -PolicyType TeamsCallingPolicy) -eq $null) {Get-CsTeamsCallingPolicy -Identity Global} else {Get-CsTeamsCallingPolicy -Identity $p.PolicyName}
```

輸出看起來應該像這樣：

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

-   進行任何這些設定變更之後，您可能需要重新開機Teams用戶端。

-   如果您最近更新了上述任何準則，您可能需要等候數小時，用戶端才能收到新的設定。

-   如果您仍然看不到撥號鍵台，請使用下列命令檢查是否有布建錯誤：

  ```
  Get-CsOnlineUser -Identity $user|Select UserValidationErrors
  ```

-    如果已超過 24 小時，而您仍然看到問題，請連絡支援服務。


