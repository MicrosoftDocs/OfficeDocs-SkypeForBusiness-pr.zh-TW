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
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: 下列描述音訊會議的 [在網路上開啟預覽] 功能。
ms.openlocfilehash: 3b33c67cc79f79d36cf2a11213dc934103b026fb
ms.sourcegitcommit: 19662d4bc4070f6031084d93e8794e0e02decd2b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/01/2020
ms.locfileid: "47321789"
---
# <a name="open-preview-of-on-network-conferencing-for-audio-conferencing"></a>開啟音訊會議的網路會議預覽

所有客戶都能使用網路會議的開啟預覽。 [網路會議] 可讓組織透過直接路由傳送入站和出站音訊會議呼叫至 Microsoft 撥入號碼。 此功能不是為了將音訊會議支援延伸到協力廠商撥入號碼。 如果使用網路會議，則無法透過協力廠商撥入電話號碼將來電傳送到音訊會議服務。

本文將說明針對您的組織啟用網路會議時所需的先決條件及設定步驟。

> [!IMPORTANT]
> 在印度的任何電話裝置上，都不能部署網路會議。
  
## <a name="prerequisites"></a>必要條件

在設定網路會議之前，請確定貴組織符合下列先決條件： 

- 確定您組織中已啟用或將要啟用音訊會議的所有使用者都只使用 [小組] 模式。 只有在小組會議中才支援透過網路會議傳送入站與 outboud 音訊會議通話。

- 將音訊會議授權指派給所有將使用網路會議的使用者。

- 設定音訊會議服務。 如需其他資訊，請參閱 [設定 Microsoft 團隊的音訊會議](set-up-audio-conferencing-in-teams.md)。

- 針對直接路由 (SBC) 設定您的會話邊界控制器。 如需其他資訊，請參閱 [規劃直接路由](direct-routing-plan.md) 及 [設定直接路由](direct-routing-configure.md)。 

  如果您只是為了進行音訊會議而設定直接傳送路線，則只需要完成「步驟1：將您的 SBC 連接到網路會議」。
  
## <a name="enable-the-routing-of-dial-in-calls-to-microsoft-audio-conferencing-through-direct-routing"></a>透過直接路由啟用電話撥入呼叫路由至 Microsoft 音訊會議 

若要透過直接路由將內部部署使用者所進行的撥入呼叫路由至音訊會議服務，您必須針對 SBCs 和私人分支 Exchange 設定適當的路由規則， (s)  (Pbx) ]。

您必須設定您的網站的電話語音裝置，以透過直接路由主幹將呼叫路由到貴組織的任何服務號碼。

您可以在 [ **會議-> 會議橋** 接或使用商務用 Skype Online PowerShell Cmdlet CsOnlineDialInConferencingBridge，找到 [團隊系統管理中心] 中的服務號碼。 如需其他資訊，請參閱 [Microsoft 團隊中的音訊會議號碼](see-a-list-of-audio-conferencing-numbers-in-teams.md)清單。


## <a name="enable-the-routing-of-teams-meeting-dial-out-calls-through-direct-routing"></a>透過直接路由啟用團隊會議撥出通話的路由

團隊會議撥出通話是從貴組織中的會議開始，到 PSTN 號碼，包括呼叫我接聽電話和通話，讓新參與者加入會議。 

若要讓團隊透過直接路由來會議撥出路由，您需要建立並指派音訊會議路由策略，名為「OnlineAudioConferencingRoutingPolicy」。 

OnlineAudioConferencingRoutingPolicy 原則相當於經由直接路由的 1:1 PSTN 呼叫 CsOnlineVoiceRoutingPolicy。 您可以使用下列 Cmdlet 來管理 OnlineAudioConferencingRoutingPolicy 原則：

-   新-CsOnlineAudioConferencingRoutingPolicy
- Set-CsOnlineAudioConferencingRoutingPolicy
- CsOnlineAudioConferencingRoutingPolicy
- 授與 CsOnlineAudioConferencingRoutingPolicy
- 移除-CsOnlineAudioConferencingRoutingPolicy

如需直接路由路由的詳細資訊，請參閱 [設定直接路由的語音路由](direct-routing-voice-routing.md)。


若要啟用透過直接路由傳送會議撥出通話的功能，您需要： 

- 設定音訊會議路由策略
- 在組織的電話裝置上設定路由
-  (選用) 設定撥號方案

來自團隊會議的撥出通話是來自于會議橋接器上的預設服務號碼。 如需音訊會議橋接器預設服務號碼的其他資訊，請參閱在 [音訊會議橋中變更電話號碼](change-the-phone-numbers-on-your-audio-conferencing-bridge.md)。

### <a name="configure-audio-conferencing-routing-policies"></a>設定音訊會議路由策略

[音訊會議路由原則] OnlineAudioConferencingRoutingPolicy 會判斷哪個會議撥出通話是路由至直接路由 trunks。 如果您熟悉 CsOnlineVoiceRoutingPolicy 原則，此原則的運作方式會非常類似。

若要設定音訊會議路由策略，您需要執行下列步驟：
1.  建立 PSTN 用法
2.  設定語音路由
3.  建立音訊會議語音路由策略
4.  指派原則給您的使用者


#### <a name="create-pstn-usages"></a>建立 PSTN 用法

PSTN 用法是語音路由的集合。 從指定召集人的會議啟動撥出通話時，語音路由會根據使用者的語音路由策略，根據與使用者相關聯的 PSTN 使用量來判斷通話的路由路徑。

您可以使用「CsOnlinePstnUsage」 Cmdlet 來建立 PSTN 使用量。 例如：

```
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="US and Canada"}
```

#### <a name="configure-voice-routes"></a>設定語音路由

語音路由依據從團隊會議撥打的電話號碼，決定應該用來傳送通話的 PSTN 閘道。 語音路由決定應該用來傳送指定通話的 PSTN 閘道，方法是將從使用 RegEx 模式的小組會議所撥的電話號碼相較。 建立語音路線時，必須將路由與一或多個 PSTN 用途產生關聯。

您可以使用「新-CsOnlineVoiceRoute」 Cmdlet，建立語音路由並定義要與語音路由相關聯的 RegEx 和閘道。 例如：

```
New-CsOnlineVoiceRoute -Identity "Redmond 1" -NumberPattern "^\+1(425|206)(\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```

#### <a name="create-audio-conferencing-voice-routing-policies"></a>建立音訊會議語音路由策略

音訊會議語音路由策略會根據會議撥出通話通話的目標電話號碼，決定您可以用來傳送來自召集人會議之通話的可能路線。 音訊會議語音路由策略會與一或多個 PSTN 用途相關聯，然後，決定將嘗試用於會議撥出呼叫（與原則相關的召集人）的可能路由。

您可以使用「新-CsOnlineAudioConferencingRoutingPolicy」 Cmdlet 來建立音訊會議語音路由原則。 例如：

```
New-CsOnlineAudioConferencingRoutingPolicy "Policy 1" -OnlinePstnUsages "US and Canada"
```

在將原則指派給使用者，並從使用者的其中一個會議啟動會議撥出通話時，系統會評估 PSTN 用法中與召集人相關聯的語音路由（透過使用者的語音路由策略）。 如果會議撥出通話目的地與與召集人相關的其中一個語音路由中的 RegEx 相符，會議撥出呼叫將會路由到語音路由中定義的 PSTN 閘道。 如果會議撥出通話目的地不符合任何與召集人相關的語音路由，會議撥出呼叫將由 Microsoft 傳送。

#### <a name="assign-a-policy-to-your-users"></a>指派原則給您的使用者

在定義音訊會議路由策略之後，您現在可以將它們指派給使用者。 將原則指派給它們之後，就會針對會議撥出通話進行評估，以判斷其路由路徑。 音訊會議路由策略總是根據會議召集人的評估，與會議中啟動會議撥出通話的使用者無關。

您可以使用「授與 CsOnlineAudioConferencingRoutingPolicy」 Cmdlet，將音訊會議語音路由原則指派給使用者。 例如：

```
Grant-CsOnlineAudioConferencingRoutingPolicy -Identity "<User Identity>" -PolicyName "Policy 1”
```


### <a name="configure-routing-on-the-telephony-equipment-of-your-organization"></a>在組織的電話語音裝置上設定路由

在貴組織的電話裝置上，您必須確認透過直接路由路由的會議撥出電話會傳送到預定的目的地。


### <a name="optional-configure-a-dial-plan"></a> (選用) 設定撥號方案

撥號方案是一組正常化規則，其中個別使用者將撥打的電話號碼轉換成替代格式 (通常是) 的 E. 164，以進行呼叫授權及呼叫路由。

根據預設，團隊使用者可以使用164格式的 PSTN 號碼撥出（即 +） \<country code\> \<number\> 。 不過，您可以使用撥號方案，讓使用者以其他格式撥打電話號碼（例如4位數延伸）。

如果您想要透過網路會議啟用延伸式撥號，您可以設定撥號方案，讓 [擴充撥號模式] 符合您組織之電話號碼的電話號碼範圍。 若要設定撥號方案，請參閱 [建立及管理撥號方案](create-and-manage-dial-plans.md)。


## <a name="known-issues-in-open-preview"></a>開啟預覽中的已知問題

下列是目前在「網路會議」開啟預覽版中的已知問題清單。 Microsoft 正在努力解決這些問題。

| 問題 | 避免 |
| :--- | :--- |
| 透過網路會議路由的匿名/隱藏呼叫者 Id 的撥入呼叫無法連線至會議。 | 如果可能的話，請在您的 PBX 或 SBC 中設定一個配置，以隨時透過網路會議傳送來電 ID 以進行路由。|
| 在某些情況下，當使用者撥入服務 ( 「歡迎使用音訊會議服務 ) ...」時，會向使用者播放的歡迎訊息會被截斷，且使用者不會聽到「歡迎」 word。| 目前沒有此問題的解決方法。 |




## <a name="related-topics"></a>相關主題


