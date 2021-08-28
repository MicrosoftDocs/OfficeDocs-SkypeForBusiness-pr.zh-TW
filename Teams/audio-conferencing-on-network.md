---
title: 音訊會議的網路會議
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: oscarr
ms.topic: conceptual
ms.tgt.pltfrm: cloud
audience: admin
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
- m365initiative-meetings
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: 下列說明音訊會議的網路。
ms.openlocfilehash: 7d477826c79b1a1630616cc51130348bfb953fa7
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58620709"
---
# <a name="on-network-conferencing-for-audio-conferencing"></a>音訊會議的網路會議

網路會議可讓組織透過直接路由將輸入和輸出的音訊會議通話傳送至 Microsoft 撥入號碼。 此功能並不適合將音訊會議的支援延伸到協力廠商撥入號碼。 如果網路會議是用來透過協力廠商撥入電話號碼或從 Microsoft 音訊會議橋接器撥出電話路由到 PSTN，則不支援網路會議。 

本文將說明為貴組織啟用網路會議的先決條件和組組步驟。

> [!IMPORTANT]
> 網路會議不得與印度的任何電話設備一起部署。
  
## <a name="prerequisites"></a>必要條件

在設置網路會議之前，請確定貴組織符合下列先決條件： 

- 請確保貴組織中已啟用或將會啟用音訊會議的所有使用者，Teams所有會議。 透過網路會議撥打和輸出音訊會議通話的路由僅支援Teams會議。

- 指派音訊會議授權給將會使用網路會議的所有使用者。

- 設定音訊會議服務。 有關其他資訊，請參閱[設定音訊會議Microsoft Teams。](set-up-audio-conferencing-in-teams.md)

- 設定您的會話邊界控制器 (SBC) 直接路由。 有關其他資訊，請參閱 [規劃直接路由](direct-routing-plan.md) 和 [設定直接路由](direct-routing-configure.md)。 

  如果您只針對音訊會議的目的設定直接路由，則只需要完成「步驟 1：連線 SBC」的網內會議。
  
## <a name="enable-the-routing-of-dial-in-calls-to-microsoft-audio-conferencing-through-direct-routing"></a>啟用透過直接路由將撥入式通話路由至 Microsoft 音訊會議 

若要透過直接路由，將內部部署使用者撥打的電話撥入電話路由至音訊會議服務，您必須為 SBCs 和私人分支 Exchange (PBX)  (設定適當的路由) 。

您需要設定網站的電話設備，以透過直接路由主幹將通話路由到貴組織會議橋接器的任何服務號碼。

您可以在 Teams 系統管理中心會議 **-> 會議** 橋接器下，或使用 商務用 Skype Online PowerShell Cmdlet Get-CsOnlineDialInConferencingBridge 找到服務號碼。 有關其他資訊，請參閱 Microsoft Teams 中的[音訊會議號碼Microsoft Teams。](see-a-list-of-audio-conferencing-numbers-in-teams.md)

> [!NOTE]
> 此功能不適用於擁有每分鐘付費音訊會議授權的使用者。

## <a name="enable-the-routing-of-teams-meeting-dial-out-calls-through-direct-routing"></a>啟用透過直接路由Teams撥出電話的路由

Teams撥出電話會從您組織的會議內撥打 PSTN 號碼，包括電話-me-at 通話和電話，以將新參與者帶到會議。 

若要Teams直接路由傳送給網路使用者，您必須建立並指派稱為「OnlineAudioConferencingRoutingPolicy」的音訊會議路由策略。 

OnlineAudioConferencingRoutingPolicy 政策相當於透過直接路由撥打 1：1 PSTN 通話的 CsOnlineVoiceRoutingPolicy。 您可以使用下列 Cmdlet 管理 OnlineAudioConferencingRoutingPolicy 政策：

-   New-CsOnlineAudioConferencingRoutingPolicy
- Set-CsOnlineAudioConferencingRoutingPolicy
- Get-CsOnlineAudioConferencingRoutingPolicy
- Grant-CsOnlineAudioConferencingRoutingPolicy
- Remove-CsOnlineAudioConferencingRoutingPolicy

有關直接路由路由的路由詳細資訊，請參閱 [設定直接路由的語音路由](direct-routing-voice-routing.md)。


若要透過直接路由啟用會議撥出電話的路由，您必須： 

- 設定音訊會議路由策略
- 在貴組織的電話設備上設定路由
-  (選) 設定撥號方案

從會議撥出Teams電話來自會議橋接器上的預設服務號碼。 有關音訊會議橋接器預設服務號碼的其他資訊，請參閱變更音訊會議橋接器 [上的電話號碼](change-the-phone-numbers-on-your-audio-conferencing-bridge.md)。

### <a name="configure-audio-conferencing-routing-policies"></a>設定音訊會議路由策略

音訊會議路由策略 OnlineAudioConferencingRoutingPolicy 會決定哪些會議撥出電話會路由至直接路由主幹。 如果您熟悉 CsOnlineVoiceRoutingPolicy 政策，此政策運作方式非常類似。

設定音訊會議路由策略需要下列步驟：
1.  建立 PSTN 使用狀況
2.  設定語音路由
3.  建立音訊會議語音路由策略
4.  指派策略給使用者


#### <a name="create-pstn-usages"></a>建立 PSTN 使用狀況

PSTN 使用量是語音路由的集合。 當從特定召集人的會議啟動撥出通話時，語音路由會根據透過使用者的語音路由策略與使用者相關聯的 PSTN 使用方式，來判斷通話的路由路徑。

您可以使用 「Set-CsOnlinePstnUsage」 Cmdlet 建立 PSTN 使用量。 例如：

```powershell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="US and Canada"}
```

#### <a name="configure-voice-routes"></a>設定語音路由

語音路由會決定 PSTN 閘道，該閘道應該用來根據從會議撥打的電話號碼來路由Teams號碼。 語音路由會決定 PSTN 閘道，該閘道應用來路由給定通話，方法為使用 RegEx 模式Teams會議撥打的電話號碼。 建立語音路由時，路由必須與一或多個 PSTN 使用方式相關聯。

您可以使用 「New-CsOnlineVoiceRoute」Cmdlet 建立語音路由，並定義要與語音路由相關聯的 RegEx 和閘道。 例如：

```powershell
New-CsOnlineVoiceRoute -Identity "Redmond 1" -NumberPattern "^\+1(425|206)(\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```

#### <a name="create-audio-conferencing-voice-routing-policies"></a>建立音訊會議語音路由策略

音訊會議語音路由策略會根據會議撥出通話的目標電話號碼，決定可用來路由來自會議召集人會議之通話的可能路由。 音訊會議語音路由策略與一或多個 PSTN 使用方式相關聯，進而決定將嘗試用於與該策略相關聯的會議撥出通話的可能路由。

您可以使用 「New- CsOnlineAudioConferencingRoutingPolicy」 Cmdlet 來建立音訊會議語音路由策略。 例如：

```powershell
New-CsOnlineAudioConferencingRoutingPolicy "Policy 1" -OnlinePstnUsages "US and Canada"
```

將策略指派給使用者後，以及當從其中一個使用者的會議啟動會議撥出通話時，會評估透過使用者的語音路由策略與召集人相關聯的 PSTN 使用方式中的語音路由。 如果會議撥出通話目的地與與召集人相關聯的其中一個語音路由中的 RegEx 符合，會議撥出電話會路由至語音路由中定義的 PSTN 閘道。 如果會議撥出通話目的地不符合任何與召集人相關聯的語音路由，會議撥出電話會由 Microsoft 路由。

#### <a name="assign-a-policy-to-your-users"></a>指派策略給使用者

定義音訊會議路由策略之後，現在您可以將這些路由策略指派給使用者。 將策略指派給他們之後，會議撥出電話會根據它進行評估，以決定其路由路徑。 音訊會議路由策略一定根據會議的召集人進行評估，與啟動會議撥出電話的會議使用者無關。

您可以使用 「Grant-CsOnlineAudioConferencingRoutingPolicy」Cmdlet 將音訊會議語音路由策略指派給使用者。 例如：

```powershell
Grant-CsOnlineAudioConferencingRoutingPolicy -Identity "<User Identity>" -PolicyName "Policy 1”
```


### <a name="configure-routing-on-the-telephony-equipment-of-your-organization"></a>在貴組織的電話設備上設定路由

在貴組織的電話設備上，您必須確保透過直接路由的會議撥出電話會路由至預定的網路目的地。


### <a name="optional-configure-a-dial-plan"></a> (選) 設定撥號方案

撥號方案是一組標準化規則，將個別使用者撥打的電話號碼轉換成替代格式 (通常是 E.164) ，用於通話授權和呼叫路由。

根據預設，Teams以 E.164 格式撥入 PSTN 號碼，即 + \<country code\> \<number\> 。 不過，撥號方案可用來讓使用者以其他格式撥打電話號碼，例如 4 位數的分機號碼。

如果您想要透過網路會議啟用分機式撥號，您可以設定撥號方案，以將分機撥號模式與貴組織電話號碼的電話號碼範圍相符。 若要設定撥號方案，請參閱 [建立和管理撥號方案](create-and-manage-dial-plans.md)。

## <a name="related-topics"></a>相關主題


