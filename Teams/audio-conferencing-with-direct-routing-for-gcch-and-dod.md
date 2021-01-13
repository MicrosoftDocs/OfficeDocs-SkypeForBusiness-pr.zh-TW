---
title: 含直接路線、GCCH 和 DoD 的音訊會議
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
- M365-collaboration
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
f1.keywords:
- NOCSH
localization_priority: Normal
description: 系統管理員可以瞭解如何在 GCCH 和 DoD 環境中搭配直接路由使用音訊會議。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 818b36e379532e361fd3991b002bc899156af056
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812913"
---
# <a name="audio-conferencing-with-direct-routing-for-gcc-high-and-dod"></a>適用於 GCC High 和 DoD 的音訊會議搭配直接路由

使用適用于 GCC 高和 DoD 之直接路由的音訊會議，可讓參與者透過電話裝置在您的 GCC 高或 DoD 組織中加入團隊會議。 會議參與者可能想要在案例中使用電話裝置加入小組會議，例如，當網際網路連線受到限制或使用者在路上且無法存取小組時。 參與者可以選擇透過撥入您組織的撥入電話號碼，或將會議撥出到電話裝置，來加入會議。

透過使用具有直接路由的 GCC （適用于 GCC 高和 DoD），貴組織使用自己的號碼做為撥入電話號碼，而所有的會議撥出都是透過直接路由路由傳送給電話裝置。 若要啟用服務，組織必須設定直接路由，並設定可做為撥入電話號碼的電話號碼。 使用直接路由的需求與提供給非 GCC 的高和非 DoD 組織（由 Microsoft 提供電話撥入式電話號碼）的音訊會議服務是不一樣的。

## <a name="deploy-audio-conferencing-with-direct-routing-for-gcc-high-and-dod"></a>使用適用于 GCC 高和 DoD 的直接路由來部署音訊會議

### <a name="step-1-get-audio-conferencing-with-direct-routing-for-gcc-high-or-dod-licenses"></a>步驟1：使用適用于 GCC 高或 DoD 授權的直接路由取得音訊會議 

若要在 GCC 高或 DoD 中使用音訊會議，貴組織及貴組織中的使用者必須有指派直接傳送授權的音訊會議。 以下是可使用適用于 GCC 高或 DoD 直接路由的音訊會議所需的授權。

- GCC 高：適用于貴組織的音訊會議-GCC 高租使用者授權，以及音訊會議-適用于您的使用者的 GCC 高授權。

- DoD：貴組織的音訊會議-DoD 租使用者授權，以及適用于您的使用者的音訊會議-DoD 授權。

您必須擁有租使用者授權，且至少需要一個使用者授權，才能啟用服務。 您無法啟用只有租使用者授權或只有使用者授權的服務。 若要取得您的租使用者與您組織中的使用者服務授權，請與您的帳戶小組聯繫。

> [!IMPORTANT]
> 在設定撥入電話號碼前，不能使用直接傳送的音訊會議來啟用使用者。 我們建議您不要使用適用于 GCC 高或 DoD 授權給使用者的直接路由來指派音訊會議，直到您按照本文所述設定電話撥入式電話號碼。

### <a name="step-2-set-up-direct-routing"></a>步驟2：設定直接路由

若要設定直接路由，請參閱下列文章：

- [規劃直接路由](direct-routing-plan.md)

- [設定直接路由](direct-routing-configure.md)

> [!NOTE]
> 當您設定直接路由時，請記得使用這兩篇文章中所述的 GCC 高或 DoD 特定 Fqdn 和埠。

### <a name="step-3-set-up-dial-in-phone-numbers"></a>步驟3：設定撥入電話號碼

電話撥入式電話號碼是與您的音訊會議橋接器相關聯的電話號碼。 參與者會使用這些數位來加入組織中使用者排程的會議。 在您的組織中，以及在 [尋找當地電話號碼] 頁面上排程會議的使用者，這些號碼也會包含在會議邀請中。

#### <a name="define-service-phone-numbers-in-your-tenant"></a>在您的租使用者中定義服務電話號碼

您可以使用 csHybridTelephoneNumber PowerShell Cmdlet 來定義您租使用者中的服務電話號碼，以透過直接路由將呼叫路由至音訊會議服務。 

  ```PowerShell
  New-csHybridTelephoneNumber -TelephoneNumber <Phone number in E.164 format>
  ```

例如：
  ```PowerShell
  New-csHybridTelephoneNumber -TelephoneNumber "+14250000000"
  ```

#### <a name="assign-the-service-phone-numbers-to-the-audio-conferencing-bridge-of-your-organization"></a>將服務電話號碼指派給貴組織的音訊會議橋

您可以使用 csOnlineDialInConferencingServiceNumber PowerShell Cmdlet，將服務電話號碼指派給您組織的音訊會議橋。

  ```PowerShell
  Register-csOnlineDialInConferencingServiceNumber -identity <Telephone number in E.164 format> -BridgeId <Identity of the audio conferencing bridge>
  ```

您可以使用 CsOnlineDialInConferencingBridge 來查看音訊會議橋接器的 ID。 例如：

  ```PowerShell
  $b= Get-CsOnlineDialInConferencingBridge
  Register-csOnlineDialInConferencingServiceNumber -identity 14257048060 -BridgeId $b.identity
  ```


### <a name="step-4-define-a-global-voice-routing-policy-to-enable-the-routing-of-outbound-calls-from-meetings"></a>步驟4：定義全域語音路由策略以啟用從會議傳送傳出通話的功能

由貴組織中的使用者組織的會議對 PSTN 所做的撥出通話路由，是由貴組織的全域語音路由策略所定義。 如果您的組織已定義全域語音路由策略，請確認 [全域語音路由原則] 允許從組織中的使用者所組織的會議開始，對預期啟動的 PSTN 進行撥出通話。 如果您的組織沒有定義全域語音路由策略，您將需要定義一個，才能從組織中的使用者組織的會議中，將撥出電話路由至 PSTN。 請注意，貴組織的全域語音路由策略也適用于您組織中的使用者對 PSTN 所做的一對一通話。 如果針對您組織中的使用者啟用對 PSTN 的一對一呼叫，請確定全域語音路由策略符合您組織的兩種通話類型的需求。 

> [!NOTE]
> 在 Microsoft 365 政府社區 (雲端) 高或 DoD 部署中，無法使用 Location-Based 路由。 啟用音訊會議時，請確認未在 GCC 高或 DoD 環境中啟用任何音訊會議使用者 Location-Based 路由。

#### <a name="defining-a-global-voice-routing-policy"></a>定義全域語音路由策略

您可以透過定義 PSTN 使用量、語音路線、語音路由策略，以及將新的語音路由策略指派為貴組織的全域語音路由策略，來定義全域語音路由策略。

下列步驟說明如何為組織定義新的全域語音路由策略（無人）。 如果您的組織已定義 [語音路由策略]，請確認下列設定沒有與貴組織的現有語音路由策略發生衝突。

若要在商務用 Skype Online 的遠端 PowerShell 會話中建立新的 PSTN 使用量，請使用下列命令：

  ```PowerShell
  Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="International"}
  ```

如需其他資訊，請參閱 [設定 CsOnlinePstnUsage](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstnusage)。

若要建立新的語音路線，請使用下列命令：

  ```PowerShell
  New-CsOnlineVoiceRoute -Identity "International" -NumberPattern ".*" -OnlinePstnGatewayList sbc1.contoso.biz -OnlinePstnUsages "International"
  ```

為您的組織定義新的語音路線時，請指定直接路由設定期間，為您的組織定義的一或多個 PSTN 線上 PSTN 閘道。 

數位模式指定哪些通話會透過指定的閘道清單來傳送，這些呼叫是依據通話的目的地電話號碼。 在上述範例中，對世界上的任何目的地的呼叫都會與語音路線相符。 如果您想要限制可從組織中的使用者的會議撥打電話的電話號碼，您可以變更 [數位] 模式，讓語音路線只符合所允許的目的地數位模式。 請注意，如果沒有符合指定通話目的地電話號碼之數位模式的語音路由，該通話就不會傳送。

如需其他資訊，請參閱 [新 CsOnlineVoiceRoute](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroute)。

若要建立新的語音路由策略，請使用下列命令：

  ```PowerShell
  New-CsOnlineVoiceRoutingPolicy "InternationalVoiceRoutingPolicy" -OnlinePstnUsages "International"
  ```

如果在 [語音路由原則] 中定義了多個 PSTN 用法，就會按照定義的順序來評估它們。 根據與 PSTN 使用相關的語音路由的數位模式，建議 PSTN 使用的順序是從最具體到更一般的順序來定義。 例如，如果 PSTN 使用量已定義為將呼叫路由至美國，而另一個 PSTN 使用量已定義為將呼叫路由至世界上的任何其他位置，則撥打至美國的 PSTN 使用量應列在全球的語音路由原則中，以將呼叫路由至世界上的任何其他位置。

如需其他資訊，請參閱 [新 CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroutingpolicy)。

若要將新的語音路由指派給貴組織的全域語音路由策略，請使用下列命令：

  ```PowerShell
  Grant-CsOnlineVoiceRoutingPolicy -PolicyName "InternationalVoiceRoutingPolicy" -Global
  ```

如需其他資訊，請參閱 [授與 CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csonlinevoiceroutingpolicy)。

在已定義全域語音路由策略之後，您組織中的使用者所做的任何出站通話，都將會針對與全域語音路由策略的 PSTN 使用相關的語音路由進行評估。 [撥出電話] 會根據與撥打的電話號碼之數位模式相符的第一個語音路線來傳送。

### <a name="step-5-assign-audio-conferencing-with-direct-routing-for-gcc-high-or-dod-licenses-to-your-users"></a>步驟5：使用適用于 GCC 的直接路由或 DoD 授權向使用者指派音訊會議

若要為您的使用者指派可直接傳送給 GCC 高或 DoD 授權的音訊會議，請參閱 [指派授權給使用者](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)。

### <a name="step-6-optional-see-a-list-of-audio-conferencing-numbers-in-teams"></a>步驟6： (選用) 在團隊中查看音訊會議號碼清單

若要查看貴組織的音訊會議號碼清單，請移至 [在 Microsoft 團隊中查看音訊會議號碼清單](see-a-list-of-audio-conferencing-numbers-in-teams.md)。

### <a name="step-7-optional-set-auto-attendant-languages-for-the-audio-conferencing-dial-in-numbers-of-you-organization"></a>步驟7： (選用) 設定您組織之音訊會議撥入號碼的自動助理語言

若要變更貴組織之音訊會議撥入號碼的語言，請參閱 [在 Microsoft 團隊中設定音訊會議的自動助理語言](set-auto-attendant-languages-for-audio-conferencing-in-teams.md)。

### <a name="step-8-optional-change-the-settings-of-the-audio-conferencing-bridge-of-your-organization"></a>步驟8： (選用) 變更貴組織的音訊會議橋接設定

若要變更貴組織的音訊會議橋設定，請參閱 [變更音訊會議橋接器的設定](change-the-settings-for-an-audio-conferencing-bridge.md)。

### <a name="step-9-optional-set-the-phone-numbers-included-in-the-meeting-invites-of-the-users-in-your-organization"></a>步驟9： (選用) 設定您組織中的使用者在會議邀請中所包含的電話號碼

若要變更您的組織在會議邀請中所包含的一組電話號碼，請參閱 [在 Microsoft 團隊中設定邀請中包含的電話號碼](set-the-phone-numbers-included-on-invites-in-teams.md)。

## <a name="audio-conferencing-capabilities-not-supported-in-audio-conferencing-with-direct-routing-for-gcc-high-and-dod"></a>在適用于 GCC 高和 DoD 的直接佈線中，音訊會議不支援音訊會議功能

下列是在使用 GCC 高和 DoD 直接路由的音訊會議中不支援的音訊會議功能：

- 使用名稱錄製進入及結束通知。 對於有直接傳送的音訊會議，進入和結束通知會在會議中以鈴聲的方式播放。

- 音訊會議的出站通話限制原則。 限制輸出呼叫的使用者層級控制措施不適用於透過直接路由路由的會議撥出通話。

- 停用會議特定召集人的免付費電話號碼使用量。 限制使用免付費電話號碼以加入組織會議的使用者層級控制項，不適用於透過直接佈線進行路由的通話。

- 當使用者的設定變更時，傳送通知電子郵件給使用者。 使用適用于 GCC 高和 DoD 之直接路由的音訊會議，不支援音訊會議通知電子郵件。
