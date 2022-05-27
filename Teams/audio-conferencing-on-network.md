---
title: 音訊會議 的網路會議
ms.author: heidip
author: MicrosoftHeidi
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
description: 下列說明 音訊會議 的網路上。
ms.openlocfilehash: 9b986bb8cd4d432c563e60f03e2dcdf496749f36
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/25/2022
ms.locfileid: "65675955"
---
# <a name="on-network-conferencing-for-audio-conferencing"></a>音訊會議 的網路會議

網路會議可讓組織透過直接路由，將輸入和撥出音訊會議電話傳送至 Microsoft 撥入號碼。 這項功能並非要將音訊會議的支援延伸到協力廠商撥入號碼。 如果網路上會議是用來透過協力廠商撥入電話號碼或從 Microsoft 音訊會議橋接器撥出電話到 PSTN，則不支援將撥入電話路由至音訊會議服務。

本文將說明為貴組織啟用網路會議所需的必要必要條件和設定步驟。

> [!IMPORTANT]
> 網路會議不得與印度的任何電話語音設備一起部署。

## <a name="prerequisites"></a>必要條件

設定網路上會議之前，請確定您的組織符合下列先決條件：

- 請確定貴組織中已啟用或將啟用音訊會議的所有使用者，都使用Teams所有會議。 只有Teams會議才支援透過網路會議傳送和輸出音訊會議通話的路由。

- 指派音訊會議授權給所有將使用網路會議的使用者。

- 設定音訊會議服務。 如需詳細資訊，請參閱[設定Microsoft Teams音訊會議](set-up-audio-conferencing-in-teams.md)。

- 設定會話框線控制器 (SBC) 以進行直接路由。 如需詳細資訊，請參閱 [規劃直接路由](direct-routing-plan.md) 和 [設定直接路由](direct-routing-configure.md)。

  如果您設定直接路由僅供音訊會議之用，則您只需要完成網路會議的「步驟 1：連線您的 SBC」。

## <a name="enable-the-routing-of-dial-in-calls-to-microsoft-audio-conferencing-through-direct-routing"></a>透過直接路由將撥入電話轉接至 Microsoft 音訊會議

若要透過直接路由將內部部署使用者撥打的電話撥入式電話路由至音訊會議服務，您必須為 SBC 和私人分支Exchange (的)  (PBX) 設定適當的路由規則。

您必須設定網站的電話語音設備，透過直接路由主幹將通話路由到貴組織會議橋接器的任何服務號碼。

您可以在會議 **->會議橋接器** 下Teams系統管理中心找到服務號碼，或使用 商務用 Skype Online PowerShell Cmdlet Get-CsOnlineDialInConferencingBridge。 如需詳細資訊，請參閱[Microsoft Teams中的音訊會議數位](see-a-list-of-audio-conferencing-numbers-in-teams.md)清單。

> [!NOTE]
> 擁有每分鐘付費音訊會議授權的使用者無法使用此功能。

## <a name="enable-the-routing-of-teams-meeting-dial-out-calls-through-direct-routing"></a>透過直接路由啟用Teams會議撥出電話的路由

Teams會議撥出電話是從貴組織的會議內啟動到 PSTN 號碼，包括撥號給我的電話和電話，以便讓新的參與者加入會議。

若要透過直接路由將Teams會議撥出路由傳送給網路上的使用者，您必須建立並指派名為「OnlineAudioConferencingRoutingPolicy」的音訊會議路由原則。

OnlineAudioConferencingRoutingPolicy 原則相當於透過直接路由進行 1 對 1 PSTN 通話的 CsOnlineVoiceRoutingPolicy。 OnlineAudioConferencingRoutingPolicy 原則可以使用下列 Cmdlet 來管理：

- New-CsOnlineAudioConferencingRoutingPolicy
- Set-CsOnlineAudioConferencingRoutingPolicy
- Get-CsOnlineAudioConferencingRoutingPolicy
- Grant-CsOnlineAudioConferencingRoutingPolicy
- Remove-CsOnlineAudioConferencingRoutingPolicy

如需直接路由路由的詳細資訊，請參閱設定 [直接路由的語音路由](direct-routing-voice-routing.md)。

若要透過直接路由啟用會議撥出電話的路由，您必須：

- 設定音訊會議路由原則
- 設定貴組織電話語音設備的路由
-  (選擇性) 設定撥號對應表

Teams會議的撥出電話來自會議橋接器上的預設服務號碼。 如需音訊會議橋接器預設服務號碼的其他資訊，請參閱[變更音訊會議橋接器上的電話號碼](change-the-phone-numbers-on-your-audio-conferencing-bridge.md)。

### <a name="configure-audio-conferencing-routing-policies"></a>設定音訊會議路由原則

音訊會議路由原則 OnlineAudioConferencingRoutingPolicy 會決定哪些會議撥出電話會路由至直接路由主幹。 如果您熟悉 CsOnlineVoiceRoutingPolicy 原則，此原則的運作方式非常類似。

設定音訊會議路由原則需要下列步驟：

1. 建立 PSTN 使用量
1. 設定語音路由
1. 建立音訊會議語音路由原則
1. 指派原則給使用者

#### <a name="create-pstn-usages"></a>建立 PSTN 使用量

PSTN 使用量是語音路由的集合。 當撥出電話是從指定召集人的會議中啟動時，語音路由會根據使用者透過語音路由原則與使用者相關聯的 PSTN 使用方式，使用語音路由來判斷通話的路由路徑。

您可以使用 「Set-CsOnlinePstnUsage」 Cmdlet 來建立 PSTN 使用量。 例如：

```powershell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="US and Canada"}
```

#### <a name="configure-voice-routes"></a>設定語音路由

語音路由決定應該用來根據從Teams會議撥打的電話號碼來路由通話的 PSTN 閘道。 語音路由決定應用來路由指定通話的 PSTN 閘道，方法是比對從Teams會議撥打的電話號碼與 RegEx 模式。 建立語音路由時，路由必須與一或多個 PSTN 使用量相關聯。

您可以使用 「New-CsOnlineVoiceRoute」 Cmdlet 來建立語音路由，並定義要與語音路由相關聯的 RegEx 和閘道。 例如：

```powershell
New-CsOnlineVoiceRoute -Identity "Redmond 1" -NumberPattern "^\+1(425|206)(\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```

#### <a name="create-audio-conferencing-voice-routing-policies"></a>建立音訊會議語音路由原則

音訊會議語音路由原則會根據會議撥出電話的目標電話號碼，決定可用來路由來自召集人會議之通話的可能路由。 音訊會議語音路由原則與一或多個 PSTN 使用情形相關聯，進而決定將嘗試用於原則相關召集人之會議撥出電話的可能路由。

您可以使用 「New- CsOnlineAudioConferencingRoutingPolicy」 Cmdlet 來建立音訊會議語音路由原則。 例如：

```powershell
New-CsOnlineAudioConferencingRoutingPolicy "Policy 1" -OnlinePstnUsages "US and Canada"
```

將原則指派給使用者後，當會議撥出電話從使用者的其中一個會議啟動時，系統會評估透過使用者的語音路由原則與召集人相關聯的 PSTN 使用量中的語音路由。 如果會議撥出電話目的地與其中一個與召集人相關聯的語音路由中的 RegEx 相符，會議撥出電話將會路由至語音路由中定義的 PSTN 閘道。 如果會議撥出電話目的地與任何與召集人相關聯的語音路由不符，則會議撥出通話將由 Microsoft 路由。

#### <a name="assign-a-policy-to-your-users"></a>指派原則給使用者

定義音訊會議路由原則之後，您現在可以將它們指派給使用者。 將原則指派給他們之後，系統會根據會議撥出電話評估會議撥出電話，以判斷其路由路徑。 音訊會議路由原則一律會根據會議召集人進行評估，與會議中啟動會議撥出電話的使用者無關。

您可以使用 「Grant-CsOnlineAudioConferencingRoutingPolicy」 Cmdlet 來指派音訊會議語音路由原則給使用者。 例如：

```powershell
Grant-CsOnlineAudioConferencingRoutingPolicy -Identity "<User Identity>" -PolicyName "Policy 1"
```

### <a name="configure-routing-on-the-telephony-equipment-of-your-organization"></a>設定貴組織電話語音設備的路由

在貴組織的電話語音設備上，您必須確保透過直接路由傳送的會議撥出電話路由到預定的網路上目的地。

### <a name="optional-configure-a-dial-plan"></a> (選擇性) 設定撥號對應表

撥號對應表是一組正規化規則，將個別使用者撥打的電話號碼轉換為替代格式， (通常是 E.164) ，用於通話授權和通話路由。

根據預設，Teams使用者可以撥出 E.164 格式的 PSTN 號碼，也就是 + \<country code\> \<number\> 。 不過，撥號對應表可用來允許使用者以其他格式撥打電話號碼，例如 4 位數的分機。

如果您想要透過網路會議啟用以擴充功能為基礎的撥號功能，可以設定與組織電話號碼相符的分機撥號模式。 若要設定撥號對應表，請參閱 [建立及管理撥號對應表](create-and-manage-dial-plans.md)。

## <a name="related-topics"></a>相關主題
